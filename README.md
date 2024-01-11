# roothide Bootstrap FAQ

If you want something added/revised here, make a pull request or message me on Discord (@dleovl).

DO NOT UPDATE YOUR PHONE NO MATTER WHAT!
SpringBoard tweaks *DO NOT WORK* currently by any *OFFICIAL* means. This also includes tweaks that rely on daemons.

Always remember, **DO NOT INSTALL `.tipa` BUILDS FROM OTHER PEOPLE.** You risk installing malicious code since the code used to build the official `.tipa` is open source (meaning anyone could've modified the code to be malicious) and you're potentially installing outdated Bootstrap versions which may not function properly nor will they recieve support.
Don't run `rm -rf /var/`, it doesn't give you SpringBoard injection.

[Join the roothide Discord server](https://discord.com/invite/scqCkumAYp)!
If you have an issue that isn't listed here, check the [issues](https://github.com/roothide/Bootstrap/issues). If it's still not there, ask in the [roothide Discord server](https://discord.com/invite/scqCkumAYp).
This FAQ `README.md` will be consistently updated along with the [Bootstrap README fork](https://github.com/dleovl/Bootstrap/blob/readme/README.md).

## Table of Contents
- [Bootstrap](#bootstrap)
- [Tweaks](#tweaks)
- [Technical](#technical)
- [Other](#other)
- [Credits](#credits)

## Bootstrap
- [Back to Table of Contents](#table-of-contents)
#### Do I need TrollStore for this bootstrap?
YES! No TrollStore = Unsupported. No ifs, ands, or buts.
If you are on a supported version to install TrollStore, use [this guide](https://ios.cfw.guide/installing-trollstore/) to install TrollStore.

### How do I build the roothide Bootstrap? (No PC/Mac required)
Check [here](https://discord.com/channels/1130859165942829106/1130859166488076331/1190488974528106607) for instructions on building with GitHub actions (must be in the [roothide Discord server](https://discord.com/invite/scqCkumAYp), this is also good for getting really crucial information). This `.yml` doesn't automatically update to the latest commit when a new one comes out, so you'll need to sync your fork every time a commit is made (it'll automatically build within 5 minutes). **DO NOT** rely on other peoples `.tipa` files as they can be outdated or malicious. Automatic building repositories are **not** a requirement and only bloat up wherever you send them. 'Error: Process completed with exit code 8.' means Theos failed to install, manually dispatch the workflow again.

Got a Mac and wanna use Xcode? [Use this README](https://github.com/dleovl/Bootstrap/blob/readme/README.md).

### Why does the bootstrap say wait for fix? (test UI)
You are using an outdated leaked build. Please refer to this FAQ for proper instructions on how to update your bootstrap.

### Why shouldn't I use Zebra?
It doesn't work well with rootless, please stick to Sileo. You can use whatever package manager you want, but if you have issues with installing packages in Zebra, it's because you're using Zebra. Switch to Sileo.

### How do I update the Bootstrap?
For updating between major beta versions, you may have to uninstall your bootstrap before updating. This isn't alwaya a requirement for minor version revisions, but ensure you decrypt Bootstrap with [TrollDecryptor](https://github.com/wh1te4ever/TrollDecryptor) if you want to backup your build without cloning a commit.

You can export sources and tweaks in Sileo, preferences will be saved through uninstallation. ([@exact](https://github.com/exact))

Disable everything in AppEnabler, reboot, uninstall the bootstrap in the app, install your new `.tipa`, and bootstrap.

If you updated the Bootstrap before reading this, uninstall from within the app, but make sure to Bootstrap **immediately after**. Refer to this FAQ for proper uninstallation instructions, you'll need to enable (if nothing is enabled) then disable every application you had injected and do a *proper* uninstall. Your injected applications may cease to function if you update the bootstrap while a major revision was made behind the scenes without first disabling them.

### Why are notifications broken / apps always asking for permissions?
Check out [issue #2](https://github.com/roothide/Bootstrap/issues/2), this issue is already known. Disable and enable tweak injection to temporarily fix issue until next reboot.

### How do I uninstall the Bootstrap?
If you're uninstalling because of any bugs, let us know in the [GitHub issues](https://github.com/roothide/Bootstrap/issues). This will revert any SpringBoard injection tools.

You may want to backup your sources and tweaks. You can do this in Sileo by clicking the share button in the top-left corner of both the Sources and Installed tabs. You can copy and paste this list into your Notes app for safe-keeping.
1. Disable EVERYTHING in AppEnabler.
2. `(Optional, *please read in its entirety*)` If you're forever leaving the Bootstrap, open the roothide application (`com.roothide.manager` in Sileo if it isn't installed, must be bootstrapped), click varClean from the bottom tabs, press 'Select All', and press 'Clean'. This will remove ALL jailbreak related files from `/var`. **You may experience issues with jailbreak detection in the future if you do not remove these files. Unfortunately, this may also remove files utilized by other TrollStore applications. Ensure not to remove these if you want to continue using them where they were left off.**
4. Reboot your phone.
5. Open Bootstrap and press uninstall.

Thank you for staying with us.

## Tweaks
- [Back to Table of Contents](#table-of-contents)
### How do I get SpringBoard tweaks to work?
Currently, only one unofficial method for SpringBoard injection is available:
- [Serotonin](https://github.com/mineek/Serotonin): A semi-non-ish-jailbreak tool that works on top of roothide Bootstrap to provide partial support for SpringBoard tweaks

Refer to this FAQ for proper uninstallation instructions (reverting Serotonin / switching from kfdmineek).

### How do I convert tweaks?
[Check my fork of the README](https://github.com/dleovl/Bootstrap/blob/main/README.md).

### 'Not a rootless package' in roothide Patcher
By default, 'Using Rootless Compat Layer' is selected in the roothide Patcher. To convert rootless tweaks, you can use this option (though you will need to install rootless-compat as a dependancy). Rootful tweaks can use 'Directly Convert Simple Tweaks' instead.

### Cask 3 doesn't save settings!
Install [this fixed .deb](https://cdn.discordapp.com/attachments/1153426136802529280/1190903773606973470/com.ryannair05.cask3_1.0.2_iphoneos-arm64e.deb) with Sileo (pre-converted) (you may need to be in the [roothide Discord server](https://discord.com/invite/scqCkumAYp) for it to load)

### Cask 3 doesn't work in Discord / other apps
These apps will need to be decrypted and have an unsandbox entitlement like `get-task-allow` to allow the tweaks like Cask 3 to work. If this is too technical, ask in the [roothide Discord](https://discord.com/invite/scqCkumAYp).

### '**tweakname** tweak doesn't work, why?'
Some tweaks are currently not supported. This can either be due to lack of SpringBoard or daemon support, or a poorly written tweak that has manual paths.
These are some examples of incompatible tweaks:
- iCleaner (Pro): Support for daemons is required.
- Crane (Lite): Support for daemons is required, though you can manage through Preferences if you are **100%** sure you know what you're doing. Follow [this guide](https://github.com/roothide/Bootstrap/issues/11#issuecomment-1873340249) for instructions on how to use it within Preferences.
- Aemulo: Support for daemons is required.
- SnowBoard: Support for SpringBoard is required, though you can use SnowBoard UI extensions in applications.
- Flex 3 Beta: This application breaks `com.apple.Preferences` when injected if you have it alongside PreferenceLoader. Use the [updated version](https://twitter.com/Dxcool223x/status/1741169030340243520).
- iGameGod: Installing this tweak as an application (through Sileo) doesn't work because iGameGod only supports injection into 'User' applications. Use tweaks from [iOSGods](https://iosgods.com/) instead.

Any tweaks that modify or depend on daemons, the homescreen, lockscreen, control center, statusbar, or [anything else SpringBoard related](https://iphonedev.wiki/SpringBoard) will currently not function by *any* official means.

### How do I change tweak settings?
You have two solutions:
1. Enable injection into com.apple.Preferences (please be wary that you are injecting into a system application, do this at your own risk) and install PreferenceLoader along with a tweak that has a preference bundle.
2. Use TweakSettings by CreatureSurvive on the [CreatureSurvive repository](https://creaturecoding.com/repo/) and respring for it to show up. **This is the safest alternative to people who DO NOT want to inject into system applications.**

## Technical
- [Back to Table of Contents](#table-of-contents)
### Why do applications claim I'm still jailbroken?
Coming from a previous jailbreak, refer to #2 in the uninstallation guide in this FAQ to remove all jailbreak related files in `/var`.

**Do not install Filza from roothide's repository in Sileo.** If you installed Filza through TrollStore, replace it with the [no URL scheme version](https://tigisoftware.com/download/Filza_NoURLScheme_4.0.0.ipa).

If your application still persists, attempt to uninstall it completely (disable injection first) and reinstall from the App Store.

You can report bad applications in [issue #48](https://github.com/roothide/Bootstrap/issues/48), please comment the link to the App Store landing page and how to reproduce the jailbreak detection warning (do you need to login?)

### Can I use JIT?
JIT by default works with applications specifically made to support JIT provided by TrollStore, but you can enable JIT for outdated applications by using the bootstrap if you don't want to inject with [TrollStoreJitEnabler](https://github.com/Rednick16/TrollStoreJitEnabler). Enabling injection into applications that require JIT with AppEnabler will allow JIT to be utilized.

## Other
- [Back to Table of Contents](#table-of-contents)
### Why don't my apps say 'Open' in the App Store?
Applications injected in AppEnabler will not show up in the App Store. **DO NOT** click the cloud download button unless you **100%** know what you're doing.
To get it to say 'Open' again, disable injection in AppEnabler, and refresh icon cache in TrollStore.

### How do I disable OTA updates?
Turn off automatic updates in Settings, both iOS updates (installing and downloading) and security responses & system files.

Download the [Cowabunga IPA](https://github.com/leminlimez/Cowabunga/releases/download/v10.3.2/Cowabunga.ipa) and install with TrollStore.
Open and go to Tools > Miscellaneous and turn Supervised *ON*. Open Settings app and change the phones date to December 1st 2023.
Install the tvOS profile with [this .mobileconfig](https://betaprofiles.dev/dl/block-ota/BlockOTA_17.mobileconfig) and reboot. Disable Supervision from Cowabunga and set the date back to normal.

### Why don't my package managers have any URL schemes?
URL schemes are currently **disabled** to mitigate jailbreak detection. You will need to manually copy repository URLs and paste them into the package managers yourself.

### How do I enable developer mode?

You can enable developer mode by sideloading any application. You can use [Sideloadly](https://sideloadly.io/), [AltStore](https://altstore.io/), or Xcode to sideload an application.

### Why are my apps gone / not opening?
Because of how the bootstrap works, your injected applications may stop working or disappear.

For injected applications, you can either:
1. Disable injection and respring
2. Rebuild apps in Bootstrap

For TrollStore apps, you can either:
1. Refresh app registrations form your persistence helper
2. Refresh icon cache in TrollStore

Refreshing icon cache in TrollStore will make injected/Sileo installed applications disappear. Rebuild apps from within the Bootstrap app to make them appear again.

No `u/iPhone_modder`, you do not need to wipe your phone.

## Credits
- [Back to Table of Contents](#table-of-contents)
Thanks to everyone in the [roothide Discord server](https://discord.com/invite/scqCkumAYp) for making this possible!

♡ dleovl
