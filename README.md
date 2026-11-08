# Patches used on LineageOS 18.1 from R-ASB
Here's a list of patches used and what they're for.  
  
## build/make
[0001-release-Bump-Security-String-to-2026-11-01.patch](https://raw.githubusercontent.com/exynos7885-dev/r-asb-patches/refs/heads/master/build/make/0001-release-Bump-Security-String-to-2026-11-01.patch): bump the PLATFORM_SECURIY_PATCH string to corresponding backported security patches.  
  
## external/sqlite
[0001-Revert-BACKPORT-Update-sqlite-to-3.42.1.patch](https://raw.githubusercontent.com/exynos7885-dev/r-asb-patches/refs/heads/master/external/sqlite/0001-Revert-BACKPORT-Update-sqlite-to-3.42.1.patch):  
[0002-Revert-Update-sqlite-to-3.32.4.patch](https://raw.githubusercontent.com/exynos7885-dev/r-asb-patches/refs/heads/master/external/sqlite/0002-Revert-Update-sqlite-to-3.32.4.patch):  
Both patches revert the backported sqlite updates, which breaks the cli tool.  
When trying to open a db with `sqlite3` binary it throws the following error: `register_localized_collators() failed`. This happens on both updated Versions.  
  
## frameworks/base
[0001-PhoneWindowManager-Fix-wakeup-and-long-press-actions-of.patch](https://raw.githubusercontent.com/exynos7885-dev/r-asb-patches/refs/heads/master/frameworks/base/0001-PhoneWindowManager-Fix-wakeup-and-long-press-actions-of.patch): [This fix](https://review.lineageos.org/c/LineageOS/android_frameworks_base/+/349283) from LOS 20 backported to LOS 18.1.  
[0002-PhoneWindowManager-dont-disable-assist-button-when-using.patch](https://raw.githubusercontent.com/exynos7885-dev/r-asb-patches/refs/heads/master/frameworks/base/0002-PhoneWindowManager-dont-disable-assist-button-when-using.patch): This is a fix for devices with an "Assist key" and with hardware navigation buttons that use KeyDisabler in touch hal.  
KeyDisabler would usually disable the Assist Button as well, which is not what we want.  
[0003-frameworks-base-Add-support-for-app-signature-spoofing.patch](https://raw.githubusercontent.com/exynos7885-dev/r-asb-patches/refs/heads/master/frameworks/base/0003-frameworks-base-Add-support-for-app-signature-spoofing.patch): adds microG signature spoofing support  
  
## packages/apps/LineageParts
[0001-LineageParts-ButtonSettings-don-t-disable-Assistant-.patch](https://raw.githubusercontent.com/exynos7885-dev/r-asb-patches/refs/heads/master/packages/apps/LineageParts/0001-LineageParts-ButtonSettings-don-t-disable-Assistant-.patch): same purpose as 0002-PhoneWindowManager-dont-disable-assist-button-when-using.patch  
  
## packages/apps/Settings
[0001-Settings-DeviceInfo-Provide-patch-level-explanation-.patch](https://raw.githubusercontent.com/exynos7885-dev/r-asb-patches/refs/heads/master/packages/apps/Settings/0001-Settings-DeviceInfo-Provide-patch-level-explanation-.patch): Show the user that these security patches are not official and are backported from newer Android versions.  
[0002-Settings-DeviceInfo-Translations-for-patch-level-dis.patch](https://raw.githubusercontent.com/exynos7885-dev/r-asb-patches/refs/heads/master/packages/apps/Settings/0002-Settings-DeviceInfo-Translations-for-patch-level-dis.patch): Some translations for this dialog.  
[0003-Settings-DeviceInfo-improve-disclaimer-dialog.patch](https://raw.githubusercontent.com/exynos7885-dev/r-asb-patches/refs/heads/master/packages/apps/Settings/0003-Settings-DeviceInfo-improve-disclaimer-dialog.patch): Some improvements for the dialog shown.  
