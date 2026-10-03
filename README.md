# Android Power User Toolkit

[Русская версия](README-ru.md)

A curated collection of Android tools, apps, fixes, workarounds, and practical step-by-step guides for power users.

> Last manually audited: **2026-10-01**

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
| **SuperDisplay** | Turns an Android tablet/phone into a high-performance second display or graphics tablet for Windows, with USB/Wi-Fi connectivity and stylus/pressure support on compatible hardware. | [Official site](https://superdisplay.app/) | [Google Play](https://play.google.com/store/apps/details?id=com.kelocube.mirrorclient) |
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

## App stores & package management

| Tool | What it is useful for | Source / official site | Install |
| --- | --- | --- | --- |
| **F-Droid** | Free/open-source Android app repository and client. Useful for installing FOSS apps that are unavailable on Google Play and for getting reproducible/community-built packages. | [Official site](https://f-droid.org/) · [client source](https://gitlab.com/fdroid/fdroidclient) | [Official download](https://f-droid.org/) |
| **SAI (Split APKs Installer)** | Installs and exports split APK bundles (`.apks`) produced from Android App Bundles, with rooted and rootless install methods. Upstream is maintenance-only, so treat it as a useful legacy/special-purpose tool rather than an actively expanding project. | [GitHub](https://github.com/Aefyr/SAI) | [F-Droid](https://f-droid.org/packages/com.aefyr.sai.fdroid/) · [Google Play](https://play.google.com/store/apps/details?id=com.aefyr.sai) |
| **App Manager** | Deep package/app inspection and management: components, permissions, trackers, manifests, APK/APKS/APKM/XAPK install, backups, debloating, logcat and many ADB/root-assisted operations. | [GitHub](https://github.com/MuntashirAkon/AppManager) · [Docs](https://muntashirakon.github.io/AppManager/) | [F-Droid](https://f-droid.org/packages/io.github.muntashirakon.AppManager/) · [GitHub Releases](https://github.com/MuntashirAkon/AppManager/releases) |

## System settings & power-user access

| Tool | What it is useful for | Source / official site | Install |
| --- | --- | --- | --- |
| **CPU X** | Detailed device/system information and diagnostics: SoC/CPU, RAM, cameras, sensors, battery/current/temperature, network-speed monitoring and basic hardware tests. | [Developer site](https://adalve.com/) | [Google Play](https://play.google.com/store/apps/details?id=com.abs.cpu_z_advance) |
| **Hidden Settings** | Opens Android settings screens, activities, diagnostics and manufacturer-specific pages that are difficult or impossible to reach through the normal Settings UI. Also supports shortcuts and some Shizuku/root-assisted actions. | [Official site](https://www.ceyhanapps.com/) | [Google Play](https://play.google.com/store/apps/details?id=com.ceyhan.sets) |
| **SetEdit (Settings Database Editor)** | Direct editor for Android Settings database tables. Useful for exposing/tweaking values OEM UIs do not surface. **Use carefully:** bad values can break device behavior; SECURE/GLOBAL writes may require ADB-granted permissions or root depending on Android/ROM. | Closed source / official distribution is Google Play | [Google Play](https://play.google.com/store/apps/details?id=by4a.setedit22) |
| **Shizuku** | Privileged API bridge used by many advanced Android utilities without requiring each app to run as root. | [GitHub](https://github.com/RikkaApps/Shizuku) · [Official docs](https://shizuku.rikka.app/) | [Google Play](https://play.google.com/store/apps/details?id=moe.shizuku.privileged.api) · [GitHub Releases](https://github.com/RikkaApps/Shizuku/releases) |

## Keyboard, input & remapping

| Tool | What it is useful for | Source / official site | Install |
| --- | --- | --- | --- |
| **Key Mapper** | Open-source Android key/button remapper and automation tool for physical keyboards, mouse buttons, gamepads, volume/side buttons, headsets and on-screen buttons. Supports custom triggers, multi-step actions/macros, constraints and app-specific mappings; Expert Mode can use privileged/system-level access for deeper input handling. | [GitHub](https://github.com/keymapperorg/KeyMapper) · [Official site / docs](https://keymapper.app/) | [Google Play](https://play.google.com/store/apps/details?id=io.github.sds100.keymapper) · [F-Droid](https://f-droid.org/packages/io.github.sds100.keymapper/) · [GitHub Releases](https://github.com/keymapperorg/KeyMapper/releases) |
| **Pastiera** | Modern GPLv3 Android IME focused on physical keyboards. Supports configurable layouts, Cyrillic/translit layouts, JSON import/export, hardware-key shortcuts, layout switching and a capable on-screen keyboard. Useful when you want one IME to handle both physical and soft-keyboard input. Pastiera 0.86 is the final feature release; active development continues as Plektra. | [GitHub](https://github.com/palsoftware/pastiera) · [Official site](https://pastiera.eu/) | [GitHub Releases](https://github.com/palsoftware/pastiera/releases) |
| **Plektra** | GPLv3 successor to Pastiera where active development is moving. Worth tracking for modern physical-keyboard IME work; currently much earlier-stage than Pastiera. | [GitHub](https://github.com/pkb-rocks/plektra) | Source / project releases when available |
| **TypeQ25** | GPLv3 physical-keyboard IME aimed at QWERTY Android devices such as Unihertz/Zinwa hardware-keyboard phones. Includes modifier/navigation modes, shortcuts, layout editing and multi-language input. | [GitHub](https://github.com/sriharshaKanukuntla/TypeQ25) | [GitHub Releases](https://github.com/sriharshaKanukuntla/TypeQ25/releases) |
| **KeymapKit** | System-level physical keyboard layout provider: adds Android hardware-keyboard layouts via KCM without becoming an IME, requiring root, Accessibility or a background service. Good when Android is simply missing the layout you need. | [GitHub](https://github.com/mahmutaunal/KeymapKit) | [Google Play](https://play.google.com/store/apps/details?id=com.alpware.keymapkit) · [GitHub Releases](https://github.com/mahmutaunal/KeymapKit/releases) |
| **ExKeyMo** | Open-source generator for custom Android external-keyboard layouts without root. The current static-web version builds a signed layout-provider APK entirely in the browser from a KCM/layout definition. | [GitHub](https://github.com/ris58h/exkeymo) · [Web builder](https://ris58h.github.io/exkeymo/) | Generate the APK in the web builder |
| **External Keyboard Helper Pro (EKH)** | Legacy but still useful hardware-keyboard IME for Bluetooth/USB keyboards. Supports custom layouts and in-IME language switching, which can work around apps that consume Android's normal physical-layout shortcut. **Closed-source/old target SDK:** modern Android may block Play installation and require sideloading. | [Official docs](https://www.apedroid.com/android-applications/external-keyboard-helper/documentation) | [Google Play](https://play.google.com/store/apps/details?id=com.apedroid.hwkeyboardhelper) |

## Automation, terminal & file utilities

| Tool | What it is useful for | Source / official site | Install |
| --- | --- | --- | --- |
| **MacroDroid** | No-code/low-code Android automation based on triggers, actions and constraints. Great for device routines, connectivity changes, notifications, scheduled actions and custom automation flows. | [Official site](https://macrodroid.com/) | [Google Play](https://play.google.com/store/apps/details?id=com.arlosoft.macrodroid) |
| **Automate (LlamaLab)** | Powerful visual automation built from flowcharts/blocks. Especially useful for system-state workflows; it exposes blocks such as hardware-keyboard visibility and input-method switching, and can use privileged/ADB-assisted capabilities for deeper Android automation. Free tier supports flows up to its block limit. | [Official site / docs](https://llamalab.com/automate/) | [Google Play](https://play.google.com/store/apps/details?id=com.llamalab.automate) |
| **OpenTasker** | Modern local-first FOSS Tasker-style automation engine with profiles, contexts, tasks, flow control and a growing set of built-in actions. No account or cloud runtime; designed around explicit permission/capability gates. | [GitHub](https://github.com/SysAdminDoc/OpenTasker) | [GitHub Releases](https://github.com/SysAdminDoc/OpenTasker/releases) |
| **Automation (Jens Schröder)** | Long-running open-source rule-based Android automation app with triggers/actions for time, charging, USB, Wi-Fi, Bluetooth, apps, NFC and other device state. Useful lightweight FOSS alternative to commercial automation suites. | [Source / official Gitea](https://git.server47.de/jens/Automation) | [F-Droid](https://f-droid.org/packages/com.jens.automation2/) · [Google Play](https://play.google.com/store/apps/details?id=com.jens.automation2) |
| **Easer** | GPLv3 user-defined Android automation based on events, conditions and operations, with plugin-style extensibility. Mature architecture but slower-moving than newer automation projects. | [GitHub](https://github.com/renyuneyun/Easer) · [Project site](https://renyuneyun.github.io/Easer/) | [F-Droid](https://f-droid.org/packages/ryey.easer/) |
| **ShizukuAutoTask** | Open-source automation assistant that can execute tasks through either Shizuku/UiAutomation or AccessibilityService. Supports persistent and one-shot tasks, gesture recording and UI-tree inspection. | [GitHub](https://github.com/ITAnt/ShizukuAutoTask) | [Project download link](https://fir.xcxwo.com/tasker) |
| **Termius** | Polished cross-platform SSH/Mosh/Telnet/SFTP client for remote hosts, with saved hosts/keys, port forwarding, built-in SFTP, multitabs and a mobile keyboard addon. A strong SSH-first option when you want server sessions without maintaining a local Linux environment on Android. | [Official site](https://termius.com/) · [Android feature page](https://www.termius.com/free-ssh-client-for-android) | [Google Play](https://play.google.com/store/apps/details?id=com.server.auditor.ssh.client) · [Android download page](https://termius.com/download/android) |
| **Termux** | Full terminal and Linux package environment on Android. Useful for SSH, scripting, Git, Python, local services and command-line tooling without a traditional Linux installation. | [GitHub](https://github.com/termux/termux-app) | [F-Droid](https://f-droid.org/packages/com.termux/) · [GitHub Releases](https://github.com/termux/termux-app/releases) |
| **Termux Launcher (PickleHik3)** | Independent Termux-based terminal-first Android launcher/fork with native sessions/windows, recursive split and floating panes, layouts, workspace restore, TUI-tuned touch/mouse behavior, scrollback copy mode and keyboard-first shortcuts. Especially interesting for tablets and desktop-like terminal workflows. **Experimental/personal project:** its README says it is vibe-coded and explicitly asks for security review. The `com.termux` edition replaces official Termux; the Nix and VAJ editions can install side-by-side. | [GitHub](https://github.com/PickleHik3/termux-launcher) · [Docs](https://picklehik3.github.io/termux-launcher-site/) | [GitHub Releases](https://github.com/PickleHik3/termux-launcher/releases) |
| **ZArchiver** | Powerful archive/file utility supporting 7z, ZIP, RAR and many other formats, including creation/extraction and archive browsing. | [Official site](https://zdevs.ru/en/) | [Google Play](https://play.google.com/store/apps/details?id=ru.zdevs.zarchiver) |

> **Termius vs Termux Launcher:** Termius is primarily a remote-server client; Termux Launcher gives you a local Termux/Linux environment plus native panes/layouts. For SSH-only server administration, Termius is simpler; for local CLI tools and a desktop-like multi-pane terminal on Android, Termux Launcher is the more relevant experiment.

## Network, VPN, proxy & censorship tools

### Recommended picks

- **⭐ v2RayTun** — recommended general-purpose Android client when you already have your own proxy/VPN subscription or server configuration. It supports common Xray/V2Ray-style protocols and imports configs/subscriptions.
- **⭐ ByeByeDPI** — recommended local DPI/censorship-bypass tool when the problem is ISP filtering rather than the need for a remote VPN endpoint. **It is not a remote VPN service** and does not hide your public IP by itself.

> Android normally allows only one active `VpnService`-based tunnel at a time. Many of the clients below therefore compete for the same Android VPN slot even when they are technically proxy clients rather than commercial VPN services. When combining tools, check whether one of them can run in proxy mode instead of `VpnService` mode.

### Proxy, VPN & tunneling clients

| Tool | What it is useful for | Source / official site | Install |
| --- | --- | --- | --- |
| **⭐ Recommended — v2RayTun** | Cross-platform Xray-based proxy client for importing your own configs/subscriptions. Supports modern V2Ray/Xray-style protocols; it does **not** sell/provide VPN servers itself. | [Official GitHub (roadmap/releases)](https://github.com/LXST-CODE/v2RayTun) · [Developer site](https://databridges.tech/) | [Google Play](https://play.google.com/store/apps/details?id=com.v2raytun.android) · [GitHub Releases](https://github.com/LXST-CODE/v2RayTun/releases) |
| **sing-box (SFA)** | Official Android client for the universal sing-box proxy platform. Handles local/remote profiles and TUN transparent proxying through Android `VpnService`; excellent when you want a flexible low-level multi-protocol client. | [Android source](https://github.com/SagerNet/sing-box-for-android) · [core](https://github.com/SagerNet/sing-box) · [Docs](https://sing-box.sagernet.org/clients/android/) | [Google Play](https://play.google.com/store/apps/details?id=io.nekohasekai.sfa) · [F-Droid](https://f-droid.org/packages/io.nekohasekai.sfa/) · [GitHub Releases](https://github.com/SagerNet/sing-box/releases) |
| **V2rayGG** | Privacy-focused V2RayNG-style client with VLESS, VMess, Shadowsocks and advanced routing/profile support. The Play listing describes it as open source, but its advertised source URL is currently unavailable (audited 2026-10-01), so no unofficial replacement repo is linked here. | Source advertised by the Play listing is currently unavailable | [Google Play](https://play.google.com/store/apps/details?id=com.github.v2raygg) |
| **Shadowrocket for Android (Cross Ltd.)** | Android proxy/VPN client with built-in nodes plus VMess, VLESS, Trojan, Shadowsocks, Hysteria2, WireGuard, SOCKS/HTTP and subscription import. **Do not confuse it with the unrelated original iOS Shadowrocket app.** | Closed source; no verified public source repository found | [Google Play](https://play.google.com/store/apps/details?id=com.v2cross.proxy) |
| **Tailscale** | Open-source Android client for a WireGuard-based identity-aware mesh/overlay network. Best for securely reaching your own devices, homelab and private networks rather than as a generic V2Ray-style subscription client. | [GitHub](https://github.com/tailscale/tailscale-android) · [Official site](https://tailscale.com/) | [Google Play](https://play.google.com/store/apps/details?id=com.tailscale.ipn) · [Official APK packages](https://pkgs.tailscale.com/stable/#android) |
| **V2BOX** | Multi-protocol proxy client supporting VLESS/VMess, Shadowsocks, Trojan, SSH, Hysteria/Hysteria2, Reality and subscription imports. Closed-source client distributed by HexaSoftware. | [Developer site](https://hexasoftware.dev/) | [Google Play](https://play.google.com/store/apps/details?id=dev.hexasoftware.v2box) |
| **V2Ray Client+ (V2ray VPN Client: Xray Vless)** | Lightweight V2Ray/Xray client focused on VLESS Reality / XTLS RPRX Vision with `vless://` and QR import. Useful when you want a simple VLESS-focused client rather than a huge configuration UI. | Closed source; no verified public source repository found | [Google Play](https://play.google.com/store/apps/details?id=com.v2ray.client) |
| **Happ — Proxy Utility** | Xray-core proxy client with routing and VLESS Reality, VMess, Trojan, Shadowsocks, SOCKS and Hysteria2. The project explicitly does not provide servers; bring your own config/subscription. | [GitHub](https://github.com/Happ-proxy/happ-android) · [Official site](https://happ.su/) | [Google Play](https://play.google.com/store/apps/details?id=com.happproxy) · [GitHub APK](https://github.com/Happ-proxy/happ-android/releases/latest) |
| **Hiddify** | Open-source multi-platform client based on sing-box, with TUN mode, automatic node selection, remote profiles and broad support for VLESS/VMess/Reality/Hysteria2/TUIC/SSH/WireGuard and common subscription formats. | [GitHub](https://github.com/hiddify/hiddify-app) · [Official site](https://hiddify.com/) | [Google Play](https://play.google.com/store/apps/details?id=app.hiddify.com) · [GitHub Releases](https://github.com/hiddify/hiddify-app/releases/latest) |
| **Outline Client** | Open-source client designed for Outline Server and also **fully compatible with standard Shadowsocks servers**. Good when you want a straightforward Shadowsocks-oriented client/server workflow. | [GitHub](https://github.com/OutlineFoundation/outline-apps) · [Official site](https://getoutline.org/) | [Google Play](https://play.google.com/store/apps/details?id=org.outline.android.client) · [official direct APK](https://developer.getoutline.org/download-links/) |

### Local DPI / censorship bypass

| Tool | What it is useful for | Source / official site | Install |
| --- | --- | --- | --- |
| **⭐ Recommended — ByeByeDPI / ByeDPI for Android** | Runs ByeDPI locally and routes traffic through it to work around some DPI-based filtering. It uses Android's VPN interface for local traffic redirection but is **not a remote VPN service**: it does not encrypt traffic by itself or hide your public IP. Works without root and supports split tunneling. | [Current project](https://github.com/romanvht/ByeByeDPI) · [original implementation](https://github.com/dovecoteescapee/ByeDPIAndroid) · [Official site](https://byebyedpi.xyz/) | [GitHub Releases](https://github.com/romanvht/ByeByeDPI/releases/latest) |

### VPN / proxy diagnostics

| Tool | What it is useful for | Source / official site | Install |
| --- | --- | --- | --- |
| **RKNHardering** | Audits an Android device for VPN/proxy detection signals: interfaces, routes, DNS, public-IP mismatches, local proxies, installed VPN apps and other indicators. Useful for understanding what another app may be able to infer about your VPN/proxy setup. | [GitHub](https://github.com/xtclovver/RKNHardering) | [GitHub Releases](https://github.com/xtclovver/RKNHardering/releases/latest) · [F-Droid](https://f-droid.org/packages/com.notcvnt.rknhardering/) |

> RKNHardering is a **diagnostic tool**, not a VPN and not a guarantee that a setup is undetectable. The project documents both confirmed checks and community/research findings, so read its confidence labels and upstream documentation before treating a result as definitive.

## Android Auto & car head units

| Tool | What it is useful for | Source / official site | Install |
| --- | --- | --- | --- |
| **Fermata Auto / Fermata Media Player** | Open-source media player with audio, video, IPTV, playlists and Android Auto support. Useful when you need a much more capable media experience than the stock Android Auto media apps provide. | [GitHub](https://github.com/AndreyPavlenko/Fermata) | [GitHub Releases](https://github.com/AndreyPavlenko/Fermata/releases/latest) |
| **Headunit Reloaded (HUR)** | Turns an Android tablet/head unit into an **Android Auto receiver/emulator**. Useful for DIY head units and tablets mounted in a car. Current connection behavior depends on the Android Auto version and device; check the Play listing/release notes for current USB/wireless limitations. | [Historical GPL source](https://github.com/borconi/headunit) *(legacy code; do not assume it matches the current Play build)* · [official support thread](https://forum.xda-developers.com/t/android-4-1-headunit-reloaded-for-android-auto-with-wifi.3432348/) | [Google Play](https://play.google.com/store/apps/details?id=gb.xxy.hr) |
| **KingInstaller** | Installs APKs while setting installer metadata so Android/Android Auto may treat them as Play-installed. Current versions offer classic, Shizuku and root-assisted methods. Compatibility is ROM/Android-Auto dependent. | [GitHub](https://github.com/fcaronte/KingInstaller) | [GitHub Releases](https://github.com/fcaronte/KingInstaller/releases) |
| **AAStore (Android Auto Store)** | Catalog/installer for third-party Android Auto apps. The original public GitHub project is explicitly **deprecated**, and modern Android Auto compatibility changes frequently. Treat it as a legacy option and verify current compatibility before relying on it. | [Legacy GitHub project](https://github.com/croccio/Android-Auto-Store) | [Legacy GitHub Releases](https://github.com/croccio/Android-Auto-Store/releases) |
| **CarTube** | Community YouTube-for-Android-Auto project intended for rootless setups. The public project is marked alpha and should be treated as highly Android-Auto-version-sensitive. **Video should only be used while safely parked.** | [GitHub](https://github.com/Raperowy/CarTube) | [Project repository](https://github.com/Raperowy/CarTube) |

### Fermata Auto note

Android Auto behavior for sideloaded/non-standard apps is **version-sensitive**. Fermata's releases and issue tracker document compatibility changes as Android Auto evolves, so check the project's current release notes/issues before assuming Fermata Auto or Fermata Mirror will appear and work on your Android Auto version.

## Media, audio & streaming

| Tool | What it is useful for | Source / official site | Install |
| --- | --- | --- | --- |
| **YouTube ReVanced / ReVanced Manager** | Open-source patching platform for Android apps. Commonly used to build a customized YouTube client with selected patches. Use the official Manager and patch your own supported APK rather than downloading random pre-patched APKs. | [GitHub](https://github.com/ReVanced/revanced-manager) · [Official site](https://revanced.app/) | [Official download](https://revanced.app/download) · [GitHub Releases](https://github.com/ReVanced/revanced-manager/releases/latest) |
| **ReVanced GmsCore** | ReVanced's microG fork for **non-root patched Google apps**. It is designed to coexist with normal Google Play Services and is the relevant GmsCore package when a ReVanced patch explicitly requires “GmsCore support”. | [GitHub](https://github.com/ReVanced/GmsCore) | [GitHub Releases](https://github.com/ReVanced/GmsCore/releases/latest) |
| **microG Services (upstream)** | Free/open-source replacement implementation of Google Play Services APIs, mainly for ROMs/devices where regular Google Play Services are unavailable or intentionally not used. **Different purpose from ReVanced GmsCore.** | [GitHub](https://github.com/microg/GmsCore) · [Official site](https://microg.org/) | [Official download docs](https://github.com/microg/GmsCore/wiki/Downloads) · [GitHub Releases](https://github.com/microg/GmsCore/releases/latest) |
| **AirMusic Pro** | Full paid version of AirMusic. Streams audio from almost any Android app to AirPlay/AirPlay 2, Sonos, Chromecast, DLNA, HEOS, Roku, Fire TV and other receivers over the local network. It is a **one-time purchase**, with no AirMusic account or subscription required. The Android app itself is not published as open source; an official Magisk module exists for optional root-based audio capture. | [Official site](https://www.airmusic.app/) · [official Magisk module](https://github.com/Magisk-Modules-Repo/airmusic) | [Google Play — Pro](https://play.google.com/store/apps/details?id=app.airmusic.pro) |
| **AirMusic Trial** | Free trial for checking whether AirMusic works with your exact Android apps, phone and receivers **before buying Pro**. It has the same basic streaming purpose, but after 10 minutes of playback it adds test signals; restarting AirMusic starts another 10-minute test period. | [Official site](https://www.airmusic.app/) | [Google Play — Trial](https://play.google.com/store/apps/details?id=app.airmusic.trial) |
| **AudioRelay** | Streams PC audio to Android, uses an Android phone as a PC microphone, or sends Android audio to another device. Supports Wi-Fi and USB and is useful for low-latency improvised audio routing. | [Official site](https://audiorelay.net/) | [Google Play](https://play.google.com/store/apps/details?id=com.azefsw.audioconnect) · [Desktop downloads](https://audiorelay.net/downloads) |

## NFC & RFID

Only use RFID/NFC read/write tools on cards, tags and systems you own or are explicitly authorized to test.

| Tool | What it is useful for | Source / official site | Install |
| --- | --- | --- | --- |
| **MIFARE Classic Tool (MCT)** | Low-level Android NFC utility for reading, writing, analyzing and managing keys/dumps for **MIFARE Classic** tags. Very useful for inspecting compatible cards and tags. | [GitHub](https://github.com/ikarus23/MifareClassicTool) | [Google Play](https://play.google.com/store/apps/details?id=de.syss.MifareClassicTool) · [F-Droid](https://f-droid.org/packages/de.syss.MifareClassicTool/) · [official APK](https://www.icaria.de/mct/releases/) |
| **RFID Tools (RRG)** | Android frontend/toolkit for external RFID/NFC hardware including Proxmark3 RDV4, ACR122U, Chameleon Mini and PN532-class devices. | [GitHub](https://github.com/RfidResearchGroup/RFIDtools) | [Google Play](https://play.google.com/store/apps/details?id=com.rfidresearchgroup.rfidtools) · [GitHub Releases](https://github.com/RfidResearchGroup/RFIDtools/releases) |
| **NFC Tools** | Friendly general-purpose NFC reader/writer for NDEF tags and common tag workflows. Better suited to everyday NFC tags than low-level MIFARE research. | [Official site](https://www.wakdev.com/en/apps.html) | [Google Play](https://play.google.com/store/apps/details?id=com.wakdev.wdnfc) |
| **NFC Tools Pro** | Paid edition of NFC Tools with the same easy read/write workflow plus the Pro feature set from Wakdev. Useful if the free version already fits your workflow and you want the expanded edition. | [Official site](https://www.wakdev.com/en/apps.html) | [Google Play](https://play.google.com/store/apps/details?id=com.wakdev.nfctools.pro) |
| **NFC TagWriter by NXP** | NXP's official app for writing NDEF content such as contacts, URLs/bookmarks, text, Wi-Fi/Bluetooth handover and other records to NFC tags. | [Official NXP page](https://www.nxp.com/design/design-center/software/rfid-developer-resources/nfc-tagwriter-app-by-nxp%3ANFC-TAGWRITER) | [Google Play](https://play.google.com/store/apps/details?id=com.nxp.nfc.tagwriter) |
| **NFC TagInfo by NXP** | Diagnostic tool from NXP for identifying NFC/RFID tag technology and inspecting supported card/tag information. Excellent first step when you do not yet know what type of tag you are dealing with. | [NXP apps](https://www.nxp.com/pages/nxp-applications%3ANXP-APPS) | [Google Play](https://play.google.com/store/apps/details?id=com.nxp.taginfolite) |
| **MIFARE Ultralight Tool** | Focused reader/writer/scanner for MIFARE Ultralight-family tags (including common NTAG variants). | [MTools Tec](https://shop.mtoolstec.com/) | [Google Play](https://play.google.com/store/apps/details?id=com.mtoolstec.mifareultralighttool) |
| **Chameleon Ultra GUI (CU GUI)** | Cross-platform open-source controller for Chameleon Ultra/Lite via USB-OTG or BLE: firmware updates, card read/write, saved-card/dictionary management and key recovery. | [GitHub](https://github.com/GameTec-live/ChameleonUltraGUI) · [Docs](https://gametec-live.com/ChameleonUltraGUI/) | [Google Play](https://play.google.com/store/apps/details?id=io.chameleon.ultra) · [GitHub Releases](https://github.com/GameTec-live/ChameleonUltraGUI/releases) |
| **PCR532** | Companion tooling around PCR532/PN532 RFID hardware. MTools Tec's current PCR532 hardware page recommends MTools, MTools BLE and RFID Tools; there is also a newer independent open-source Android client/rewrite for PCR532 Pro/compatible PN532 devices. | [PCR532 hardware/software page](https://shop.mtoolstec.com/product/pcr532) · [community Android client](https://github.com/touzi/PCR532) | [Community project](https://github.com/touzi/PCR532) |
| **MTools** | NFC/RFID utility for reading, writing and analyzing MIFARE Classic/Ultralight data using the phone's NFC or external ACR122U/PN532-class readers. | [MTools Tec](https://shop.mtoolstec.com/) | [Google Play](https://play.google.com/store/apps/details?id=tk.toolkeys.mtools) |
| **MTools BLE** | All-in-one BLE/external-reader companion for PN532 BLE, PCR532, Chameleon Ultra/Lite and related hardware, with MIFARE/DESFire/APDU tools, dump/key management and firmware utilities. | [MTools docs](https://docs.mtoolstec.com/help-and-info-mtools-lite) | [Google Play](https://play.google.com/store/apps/details?id=com.mtoolstec.mtoolsLite) |

> Hardware matters: Android NFC capabilities depend on the phone's NFC controller and firmware. For example, not every phone can perform every MIFARE Classic operation even if the app itself supports it.

## Games & free alternatives

| Tool | What it is useful for | Source / official site | Install |
| --- | --- | --- | --- |
| **Lichess** | Fully free/libre open-source chess platform with online play, puzzles, analysis, studies, tournaments and Stockfish. A strong no-subscription alternative for people who do not need Chess.com's paid ecosystem. | [GitHub](https://github.com/lichess-org/mobile) · [Official site](https://lichess.org/) | [Google Play](https://play.google.com/store/apps/details?id=org.lichess.mobileV2) |

## Community knowledge bases

Official project documentation should be the first source for downloads and security-sensitive setup, but many Android edge cases are documented much better by the community.

- **[4PDA forum](https://4pda.to/forum/)** — especially useful for Russian-language device-specific threads, firmware quirks, Android Auto, head units, root/Shizuku, networking and obscure Android utilities.
- **[XDA Forums](https://xdaforums.com/)** — one of the strongest English-language sources for ROM/device-specific guides, bootloader/root topics, Android Auto, ADB, system tweaks and troubleshooting.

A useful search pattern is: **exact app/tool name + device model + Android/firmware version + the symptom**.

> Treat forum attachments, modified APKs and old instructions as untrusted until verified. Prefer upstream GitHub/official releases for installation, and use 4PDA/XDA mainly to discover device-specific fixes, compatibility notes and troubleshooting paths.

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

## License

The original editorial content, documentation, structure, and curation in this repository are licensed under the **Creative Commons Attribution-NonCommercial 4.0 International (CC BY-NC 4.0)** license.

You may copy, share, remix, translate, and adapt this repository for **non-commercial** purposes as long as you provide appropriate attribution and indicate changes. A practical attribution format is:

> Android Power User Toolkit by **lgg** — https://github.com/lgg/android-power-user-toolkit — CC BY-NC 4.0

Third-party app names, trademarks, logos, screenshots, linked source code, and other third-party material remain subject to their respective owners' licenses and rights.

See [LICENSE](LICENSE) for details.

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
