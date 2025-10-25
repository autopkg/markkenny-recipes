
# URL
https://www.aja.com/products/io-4k-plus#support

# SEcond option
- Processor: URLTextSearcher
  Arguments:
    url: 'https://www.aja.com/products/io-4k-plus#support'
    re_pattern: '<a[^>]+data-file="([0-9]+)"[^>]+data-lang="([a-z]+)"[^>]+data-path="(AJA-Software-Installer_macOS_[^"]+_Release\.zip)"'
    result_output_var_name: FILE_INFO

- Processor: Python
  Arguments:
    input_variables: [FILE_INFO]
    output_variables: [MIRROR_URL]
    script: |
      file_number, language, filename = FILE_INFO[0]
      MIRROR_URL = f"https://static.aja.com/assets/support/files/{file_number}/{language}/{filename}?mirror"

- Processor: URLTextSearcher
  Arguments:
    url: "%MIRROR_URL%"
    re_pattern: 'href="(https://[^"]+AJA-Software-Installer_macOS_[^"]+_Release\.zip)"'
    result_output_var_name: MIRROR_LINKS

- Processor: Python
  Arguments:
    input_variables: [MIRROR_LINKS]
    output_variables: [DOWNLOAD_URL]
    script: |
      # Just pick the first mirror link, or implement logic to choose
      DOWNLOAD_URL = MIRROR_LINKS[0] if MIRROR_LINKS else None

- Processor: URLDownloader
  Arguments:
    filename: '%NAME%.zip'
    url: '%DOWNLOAD_URL%'