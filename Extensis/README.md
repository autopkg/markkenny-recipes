# NOTES

# Connect Fonts EOL?
The [URL](http://bin.extensis.com/sf-26.0.5-m-all.dmg) to download Connect Fonts 26.0.5 is now failing. I think it's been EOL'd and Extensis Connect is the main product, but I'm waiting on Extensis to confirm.


# Sparkle!
Using https://sparkle.extensis.com/u/ST/EN/suitcase25en.xml to download.
I think this changes when version changes.

# 2024 10 15
Flagged by adamlazar1 SpakrURL now updated for Sequoia support.
https://sparkle.extensis.com/u/ST/EN/suitcase26en.xml

# 2024 12 09
Application renamed "Extensis Connect".
https://help.extensis.com/hc/en-us/articles/26706224465691-The-new-Extensis-Connect-desktop-application

SparkleFeed has two DMG links, both same version, for two different applications.

[Sparklefeed](https://sparkle.extensis.com/u/ST/EN/suitcase26en.xml)

[Connect Fonts, used to be Suitcase Fusion 26.0.3, 63Mb](http://bin.extensis.com/sf-26.0.3-m-all.dmg)
[Extensis Connect, 252Mb](http://bin.extensis.com/ec-26.0.3-m-all.dmg)

# 2026 04 23 - Happy St Georges Day!
Back in 2024 [Monotype bought Extensis](https://www.monotype.com/company/press-release/monotype-announces-acquisition-extensis), so we could guess changes were coming. A few weeks ago, (April 2026) [Extensis announced Monotype Connect](https://help.extensis.com/hc/en-us/articles/26706224465691-Monotype-Connect-Installing-and-Key-Improvements). Luckily the [Sparkle feed](https://sparkle.extensis.com/u/ST/EN/suitcase28en.xml) has not changed since v28, (that's still Suitcase). Just the name of the application in the DMG.

[Installing the plugins](https://help.extensis.com/hc/en-us/articles/27521871405339-Installing-and-uninstalling-plug-ins-for-Monotype-Connect-from-the-command-line) remains the same, just the path has changed (don't use the brackets, choose your install/uninstall option)...

```
sudo "/Applications/Monotype Connect.app/Contents/Resources/plugin-installer" [--install-all | --uninstall-all|--uninstall-obsolete|--list]
```
And disabling automatic updates can be done through a deployment of a conf' file with a single key:  manual.update = true
```
#!/bin/bash
connectUpdate="/Library/Preferences/com.extensis.SuitcaseFusion.conf"
touch "$connectUpdate"
chmod 644 "$connectUpdate"
grep -q "^manual.update = true" "$connectUpdate" || (sed -i '' '/^manual.update/d' "$connectUpdate"; echo "manual.update = true" >> "$connectUpdate")
```
Needs to be before launching the application (or restart the computer if the application is in use)