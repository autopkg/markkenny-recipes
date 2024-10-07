# MyNotes

https://experienceleague.adobe.com/docs/workfront/using/review-and-approve-work/proofing/use-the-desktop-proofing-viewer/installing-desktop-proofing-viewer.html?lang=en

https://app.proofhq.com/desktopviewer/mac

https://assets.preview.proofhq.com/nativeviewer/desktop_viewer/Workfront+Proof+Preview-2.1.39.pkg

https://experienceleague.adobe.com/

https://assets.proofhq.com/nativeviewer/desktop_viewer/Workfront+Proof-2.1.40.pkg


https://assets.proofhq.com/nativeviewer/desktop_viewer/Workfront+Proof-2.1.32.pkg

(https://assets\.proofhq\.com/nativeviewer/desktop_viewer/Workfront\+Proof-.*?\.pkg)

# 2024 10 06
Download errors. 

URL to download has changed. Moving to a curl download.

https://github.com/autopkg/autopkg/blob/master/Code/autopkglib/CURLDownloader.py
https://derflounder.wordpress.com/2022/02/03/querying-an-api-for-autopkg-download-urls/

Thanks to NickETH, using their LyX-Win64 for tothe the curl_opts correct

Input:
  NAME: Workfront Proof
  DOWNLOAD_URL: https://app.proofhq.com/desktopviewer/mac
  USER_AGENT: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_8_3) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/18.0 Safari/605.1.15

Process:
- Processor: URLDownloader
  Arguments:
    curl_opts:
      - --location
    filename: '%NAME%.pkg'
    request_headers:
      user-agent: '%USER_AGENT%'
    url: '%DOWNLOAD_URL%'