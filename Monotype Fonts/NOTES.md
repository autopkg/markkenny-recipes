# NOTES
[The URL](https://support.monotype.com/en/articles/7859096-syncing-and-installing-fonts-with-the-monotype-app)

As of v 7.7.0 Monotype are now making seperate ARM and INTEL versions. Two weeks away from 2027 and there's a new Intel!



OLD
<key>SEARCH_PATTERN</key>
<string>https://monotypeapp.monotype.com/release/\d+/mac/system/DTAppInstaller.pkg.zip</string>

NEW
<key>SEARCH_PATTERN</key>
<string>https://monotypeapp.monotype.com/release/\d+/mac/MTFInstaller.zip</string>

https://monotypeapp.monotype.com/release/710/mac/MTFInstaller.zip


# SILENT UNINSTALL IF NEEDED
sudo /Applications/Monotype\ Fonts/.Components/Services/CoreServices/MonotypeFontsService --uninstaller
