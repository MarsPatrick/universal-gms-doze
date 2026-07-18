# Universal GMS Doze

> **Note:** This is an unofficial fork of [gloeyisk/universal-gms-doze](https://github.com/gloeyisk/universal-gms-doze).
> The original project appears to be unmaintained. This fork only attempts to adapt compatibility
> for newer Android versions (15+) and KernelSU. No new features are intended.

## Overview
- Patches Google Play services app and certain processes/services to be able to use battery optimization
- Support API 23 or later
- Support Magisk, KernelSU, and APatch root implementations
- WebUI available

> **KernelSU 3.x (32302+) users:** KernelSU 3.x introduced a new [Metamodule](https://kernelsu.org/guide/metamodule.html) system. Without a metamodule installed, **modules will NOT be mounted**. Before installing this module, you must first install [meta-overlayfs](https://github.com/KernelSU-Modules-Repo/meta-overlayfs/releases) or another compatible metamodule.
>
> **KernelSU legacy (22091 and below):** Works out of the box, no metamodule required.
>
> **OnePlus OxygenOS 16 users:** it appears that com.google.android.gms cannot be modified because the system won't allow it; ~~investigation in progress~~ (If this module won't work, try [Frosty](https://github.com/xizt159/Frosty))
## WebUI
The module includes a built-in WebUI accessible from the KernelSU module page.

Features:
- GMS optimization status indicator
- Fix delayed notifications (clears GMS cache)
- Find My Device toggle (enable/disable)
- Force re-apply optimization

## Download Links
- [GitHub Releases](https://github.com/MarsPatrick/universal-gms-doze/releases)

## Troubleshooting

> All actions below can also be performed from the built-in WebUI without needing a terminal.

- Command-line for check optimization (with module installed):
```
> su
> gmsc
```
- Command-line for check optimization (in general):   
There's a line written `Whitelist (except idle) system apps:` and if `com.google.android.gms` line does not exist it means Google Play services is optimized.
```
> su
> dumpsys deviceidle
```
- Command-line for fix delayed incoming messages issue:   
If the issue still persists, move the app to Not Optimized battery usage.
```
> su
> cd /data/data
> find . -type f -name '*gms*' -delete
```
- Command-line for disable Find My Device (optional):
```
> su
> pm disable com.google.android.gms/com.google.android.gms.mdm.receivers.MdmDeviceAdminReceiver
```

## Tested Devices

| Device | Codename | ROM | Android | Kernel | KernelSU |
|--------|----------|-----|---------|--------|----------|
| Pixel 7 Pro | cheetah | crDroid 11.6 | 15 | blu_spark 256 | KernelSU 3.1.0 GKI |
| Pixel 7 Pro | cheetah | crDroid 12.9 | 16 | blu_spark 263 | KernelSU 3.2.4 GKI |
| Xiaomi Mi 10 | umi | PixelOS 16.2 | 16 | N0Kernel v16.4.9 v2 | KernelSU Next 1.1.1 hotfix |

## Credits
- [gloeyisk](https://github.com/gloeyisk/universal-gms-doze) / Original author
- topjohnwu / Magisk - Magisk Module Template
- JumbomanXDA, MrCarb0n / Script fixer and helper

## Extras (From Original Author)
- Donations: [PayPal](https://paypal.me/gloeyisk) - [LiberaPay](https://liberapay.com/gloeyisk) - [Ko-fi](https://ko-fi.com/gloeyisk)
- Support Thread: [XDA Developers](https://forum.xda-developers.com/apps/magisk/module-universal-gms-doze-t3853710)
