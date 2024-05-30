# NOTES


Full PKG, but errors on path deleter not find the TMP folder.


    <string>com.github.markkenny.autopkg.download.OnyX13</string>
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
	<key>Description</key>
	<string>Downloads the latest Onyx client for macOS 13 and builds a .pkg</string>
	<key>Identifier</key>
	<string>com.github.darkomen78.pkg.Onyx13</string>
	<key>Input</key>
	<dict>
		<key>NAME</key>
		<string>Onyx</string>
	</dict>
	<key>MinimumVersion</key>
	<string>1.0.1</string>
	<key>ParentRecipe</key>
    <string>com.github.markkenny.autopkg.download.OnyX13</string>
	<key>Process</key>
	<array>
		<dict>
			<key>Processor</key>
			<string>AppPkgCreator</string>
		</dict>
		<dict>
			<key>Arguments</key>
			<dict>
				<key>path_list</key>
				<array>
					<string>%RECIPE_CACHE_DIR%/payload</string>
				</array>
			</dict>
			<key>Processor</key>
			<string>PathDeleter</string>
		</dict>
	</array>
</dict>
</plist>