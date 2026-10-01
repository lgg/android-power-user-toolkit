# Android Power User Toolkit

[Русская версия](README-ru.md)

A curated collection of Android tools, apps, fixes, workarounds, and practical step-by-step guides for power users.

The goal is simple: document useful Android software that solves real, often oddly specific problems — especially the kind of tools that can take hours of forum, GitHub, Reddit, and search-engine digging to discover.

This repository contains both:

- **a catalog** of useful apps with short, problem-oriented descriptions and trusted download/source links;
- **detailed guides** for setups that need several apps, special permissions, or non-obvious workarounds.

> **Principle:** whenever possible, links point to the original source repository or the developer's official website, and installs point to Google Play or the project's official release channel.

## Guides

| Guide | What it solves |
| --- | --- |
| [Use another Android device as a real wireless secondary display](guides/android-wireless-secondary-display.md) | Creates an independent Android virtual display, streams it to another phone/tablet with touch input, and can keep working alongside vendor desktop/PC modes. Includes the Lenovo PC Mode workaround and the Shizuku/MediaTek issue we hit in testing. |

## Display, remote desktop & multi-screen

| Tool | What it is useful for | Source / official site | Install |
| --- | --- | --- | --- |
| **spacedesk** | Turns an Android phone/tablet into an extra monitor for a Windows PC over Wi-Fi, LAN or USB, with touch/input support. Great when the **host is Windows**. | [Official site](https://www.spacedesk.net/) | [Google Play](https://play.google.com/store/apps/details?id=ph.spacedesk.beta) |
| **Mirror — Screen Mirroring Manager** | Creates Android virtual displays and can stream them through its built-in Sunshine server to Moonlight clients. This is the display/streaming core of our Android-to-Android multi-display setup. | [GitHub](https://github.com/jqssun/android-display-mirror) | [Google Play](https://play.google.com/store/apps/details?id=io.github.jqssun.displaymirror) · [GitHub Releases](https://github.com/jqssun/android-display-mirror/releases/latest) |
| **Extend — Display Manager for Android** | Manages physical and virtual Android displays, launches apps on a selected display, adjusts display behavior, and provides touch/input tools. Useful companion to Mirror. | [GitHub](https://github.com/jqssun/android-display-extend) | [Google Play](https://play.google.com/store/apps/details?id=io.github.jqssun.displayextend) · [GitHub Releases](https://github.com/jqssun/android-display-extend/releases/latest) |
| **Moonlight** | Open-source Sunshine/GameStream client. In this toolkit it is used on the **receiver Android device** to view and control the virtual display created on the host Android device. | [GitHub](https://github.com/moonlight-stream/moonlight-android) | [Google Play](https://play.google.com/store/apps/details?id=com.limelight) · [GitHub Releases](https://github.com/moonlight-stream/moonlight-android/releases) |
| **MagicDesk** | Android workstation and multi-display manager. Crucially, it can **move already-running Android tasks between displays**, which can work around vendor desktop modes that intercept ordinary app launches. | [GitHub](https://github.com/mekhontsev/magicdesk) | [GitHub Releases](https://github.com/mekhontsev/magicdesk/releases/latest) |
| **Shizuku** | Gives supported apps access to privileged Android system APIs through ADB/root without granting the apps full root. Required for the full feature set of several tools in this repository. | [GitHub](https://github.com/RikkaApps/Shizuku) · [Official docs](https://shizuku.rikka.app/) | [Google Play](https://play.google.com/store/apps/details?id=moe.shizuku.privileged.api) · [GitHub Releases](https://github.com/RikkaApps/Shizuku/releases) |

See the [full Android-to-Android wireless secondary display guide](guides/android-wireless-secondary-display.md).

## File transfer & device-to-device utilities

| Tool | What it is useful for | Source / official site | Install |
| --- | --- | --- | --- |
| **LocalSend** | Fast encrypted local file/message transfer between Android, iOS, Windows, macOS and Linux. No cloud account or internet connection is required when devices are on the same LAN. Excellent AirDrop-style utility across mixed platforms. | [GitHub](https://github.com/localsend/localsend) · [Official site](https://localsend.org/) | [Google Play](https://play.google.com/store/apps/details?id=org.localsend.localsend_app) |

## System settings & power-user access

| Tool | What it is useful for | Source / official site | Install |
| --- | --- | --- | --- |
| **Hidden Settings** | Opens Android settings screens, activities, diagnostics and manufacturer-specific pages that are difficult or impossible to reach through the normal Settings UI. Also supports shortcuts and some Shizuku/root-assisted actions. | [Official site](https://www.ceyhanapps.com/) | [Google Play](https://play.google.com/store/apps/details?id=com.ceyhan.sets) |
| **Shizuku** | Privileged API bridge used by many advanced Android utilities without requiring each app to run as root. | [GitHub](https://github.com/RikkaApps/Shizuku) · [Official docs](https://shizuku.rikka.app/) | [Google Play](https://play.google.com/store/apps/details?id=moe.shizuku.privileged.api) · [GitHub Releases](https://github.com/RikkaApps/Shizuku/releases) |

## Network, VPN & privacy diagnostics

| Tool | What it is useful for | Source / official site | Install |
| --- | --- | --- | --- |
| **RKNHardering** | Audits an Android device for VPN/proxy detection signals: interfaces, routes, DNS, public-IP mismatches, local proxies, installed VPN apps and other indicators. Useful for understanding what another app may be able to infer about your VPN/proxy setup. | [GitHub](https://github.com/xtclovver/RKNHardering) | [GitHub Releases](https://github.com/xtclovver/RKNHardering/releases/latest) · [F-Droid](https://f-droid.org/packages/com.notcvnt.rknhardering/) |

> RKNHardering is a **diagnostic tool**, not a VPN and not a guarantee that a setup is undetectable. The project documents both confirmed checks and community/research findings, so read its confidence labels and upstream documentation before treating a result as definitive.

## Android Auto & car head units

| Tool | What it is useful for | Source / official site | Install |
| --- | --- | --- | --- |
| **Fermata Auto / Fermata Media Player** | Open-source media player with audio, video, IPTV, playlists and Android Auto support. Useful when you need a much more capable media experience than the stock Android Auto media apps provide. | [GitHub](https://github.com/AndreyPavlenko/Fermata) | [GitHub Releases](https://github.com/AndreyPavlenko/Fermata/releases/latest) |
| **Headunit Reloaded (HUR)** | Turns an Android tablet/head unit into an **Android Auto receiver/emulator**. Useful for DIY head units and tablets mounted in a car. Current connection behavior depends on the Android Auto version and device; check the Play listing/release notes for current USB/wireless limitations. | [Historical GPL source](https://github.com/borconi/headunit) *(legacy code; do not assume it matches the current Play build)* · [official support thread](https://forum.xda-developers.com/t/android-4-1-headunit-reloaded-for-android-auto-with-wifi.3432348/) | [Google Play](https://play.google.com/store/apps/details?id=gb.xxy.hr) |

### Fermata Auto note

Modern Android Auto versions heavily restrict sideloaded apps. The Fermata project documents additional requirements/workarounds for recent Android versions, including root-based methods or compatible wireless adapters. Check the project's current documentation before assuming the Android Auto component will appear automatically.

## Media, audio & streaming

| Tool | What it is useful for | Source / official site | Install |
| --- | --- | --- | --- |
| **YouTube ReVanced / ReVanced Manager** | Open-source patching platform for Android apps. Commonly used to build a customized YouTube client with selected patches. Use the official Manager and patch your own supported APK rather than downloading random pre-patched APKs. | [GitHub](https://github.com/ReVanced/revanced-manager) · [Official site](https://revanced.app/) | [Official download](https://revanced.app/download) · [GitHub Releases](https://github.com/ReVanced/revanced-manager/releases/latest) |
| **ReVanced GmsCore** | ReVanced's microG fork for **non-root patched Google apps**. It is designed to coexist with normal Google Play Services and is the relevant GmsCore package when a ReVanced patch explicitly requires “GmsCore support”. | [GitHub](https://github.com/ReVanced/GmsCore) | [GitHub Releases](https://github.com/ReVanced/GmsCore/releases/latest) |
| **microG Services (upstream)** | Free/open-source replacement implementation of Google Play Services APIs, mainly for ROMs/devices where regular Google Play Services are unavailable or intentionally not used. **Different purpose from ReVanced GmsCore.** | [GitHub](https://github.com/microg/GmsCore) · [Official site](https://microg.org/) | [Official download docs](https://github.com/microg/GmsCore/wiki/Downloads) · [GitHub Releases](https://github.com/microg/GmsCore/releases/latest) |
| **AirMusic** | Streams audio from almost any Android app to AirPlay/AirPlay 2, Sonos, Chromecast, DLNA, HEOS, Roku, Fire TV and other receivers over the local network. Handy when Android cannot natively output to the speaker ecosystem you use. The Android app itself is not published as open source; an official Magisk module exists for optional root-based audio capture. | [Official site](https://www.airmusic.app/) · [official Magisk module](https://github.com/Magisk-Modules-Repo/airmusic) | [Google Play — Pro](https://play.google.com/store/apps/details?id=app.airmusic.pro) |
| **AudioRelay** | Streams PC audio to Android, uses an Android phone as a PC microphone, or sends Android audio to another device. Supports Wi-Fi and USB and is useful for low-latency improvised audio routing. | [Official site](https://audiorelay.net/) | [Google Play](https://play.google.com/store/apps/details?id=com.azefsw.audioconnect) · [Desktop downloads](https://audiorelay.net/downloads) |

## NFC & RFID

Only use RFID/NFC read/write tools on cards, tags and systems you own or are explicitly authorized to test.

| Tool | What it is useful for | Source / official site | Install |
| --- | --- | --- | --- |
| **MIFARE Classic Tool (MCT)** | Low-level Android NFC utility for reading, writing, analyzing and managing keys/dumps for **MIFARE Classic** tags. Very useful for inspecting compatible cards and tags. | [GitHub](https://github.com/ikarus23/MifareClassicTool) | [Google Play](https://play.google.com/store/apps/details?id=de.syss.MifareClassicTool) · [F-Droid](https://f-droid.org/packages/de.syss.MifareClassicTool/) · [official APK](https://www.icaria.de/mct/releases/) |
| **RFID Tools (RRG)** | Android frontend/toolkit for external RFID/NFC hardware including Proxmark3 RDV4, ACR122U, Chameleon Mini and PN532-class devices. | [GitHub](https://github.com/RfidResearchGroup/RFIDtools) | [Google Play](https://play.google.com/store/apps/details?id=com.rfidresearchgroup.rfidtools) · [GitHub Releases](https://github.com/RfidResearchGroup/RFIDtools/releases) |
| **NFC Tools** | Friendly general-purpose NFC reader/writer for NDEF tags and NFC-triggered automations. Better suited to everyday NFC tags than low-level MIFARE research. | [Official site](https://www.wakdev.com/en/apps/nfc-tools-android.html) | [Google Play](https://play.google.com/store/apps/details?id=com.wakdev.wdnfc) |
| **NFC TagInfo by NXP** | Diagnostic tool from NXP for identifying NFC/RFID tag technology and inspecting supported card/tag information. Excellent first step when you do not yet know what type of tag you are dealing with. | [NXP](https://www.nxp.com/) | [Google Play](https://play.google.com/store/apps/details?id=com.nxp.taginfolite) |

> Hardware matters: Android NFC capabilities depend on the phone's NFC controller and firmware. For example, not every phone can perform every MIFARE Classic operation even if the app itself supports it.

## Games & free alternatives

| Tool | What it is useful for | Source / official site | Install |
| --- | --- | --- | --- |
| **Lichess** | Fully free/libre open-source chess platform with online play, puzzles, analysis, studies, tournaments and Stockfish. A strong no-subscription alternative for people who do not need Chess.com's paid ecosystem. | [GitHub](https://github.com/lichess-org/mobile) · [Official site](https://lichess.org/) | [Google Play](https://play.google.com/store/apps/details?id=org.lichess.mobileV2) |

## How entries are selected

This is not intended to be a dump of every Android app. A tool belongs here when it does at least one of these well:

- solves a specific problem that Android or an OEM does not solve cleanly;
- replaces a paid/cloud-locked workflow with a strong free or open alternative;
- exposes useful system functionality normally hidden from users;
- bridges Android with PCs, cars, audio systems, displays, NFC/RFID hardware or other devices;
- is unusually useful but difficult to discover without knowing its exact name.

## Version-sensitive notes

- **Shizuku:** some devices/ROMs have reported UserService regressions with 13.6.0. Our MediaTek test device could run Shizuku itself and use Mirror/Extend, while MagicDesk UserService binding timed out; 13.5.4 fixed it. See the [secondary-display guide](guides/android-wireless-secondary-display.md#shizuku-1360--mediatek-userservice-problem) for exact symptoms and upstream issues.
- **Android Auto:** Google can change what sideloaded apps are allowed to do or how third-party head-unit software connects. Treat Fermata Auto and HUR behavior as version-dependent and check their current upstream notes.
- **Secondary displays:** Android/OEM firmware can override standard multi-display behavior. A tool supporting a feature does not guarantee every OEM ROM will allow it.

## Safety & trust

- Prefer the developer's **official repository, official website, Google Play, F-Droid, or official GitHub Releases**.
- Avoid random APK mirrors and pre-patched packages when the original project provides a trusted distribution channel.
- Privileged tools such as Shizuku, root utilities, Android Auto workarounds and RFID writers can change system behavior or data. Read the upstream documentation first.
- Some techniques are firmware- and Android-version-dependent. Guides in this repository state the hardware/OS on which they were actually tested.

## Contributing

PRs and issues are welcome. A useful contribution should ideally explain **the problem the tool solves**, not just the app name.

Suggested entry format:

```text
Tool:
Problem it solves:
Why it is useful:
Source / official site:
Official install:
Requirements / caveats:
Tested on (optional):
```

---

If a tool saved you hours because it solved a weird Android problem nobody documents well, it probably belongs here.
