# Use Another Android Device as a Real Wireless Secondary Display

[Русская версия](android-wireless-secondary-display-ru.md)

This guide shows how to turn another Android phone or tablet into a **real independent secondary display** for an Android host device — not just a mirror.

The result is a setup where:

- the host Android device keeps its own screen;
- a second Android device receives a separate virtual display over Wi-Fi;
- apps can run independently on that virtual display;
- touch input from the receiver can control the remote display;
- vendor desktop modes such as Lenovo PC Mode can remain enabled while selected running apps are moved to the wireless display.

This is the setup we arrived at after testing several Android multi-display approaches.

## Tested setup

The complete workflow was verified on:

- **Host:** Lenovo Xiaoxin Pad Pro 12.7 (2025)
- **Model:** TB375FC
- **SoC:** MediaTek Dimensity 8300
- **OS:** Android 15
- **Firmware:** ZUXOS 1.1.04.287
- **Vendor desktop mode:** Lenovo PC Mode
- **Receiver:** Android phone running Moonlight

It should not be treated as Lenovo-only. The core mechanism uses standard Android virtual-display/task APIs through Shizuku and should be useful on other compatible Android devices as well. OEM firmware can still change multi-display behavior, so some devices may need additional troubleshooting.

## What each app does

| App | Role |
| --- | --- |
| [Shizuku](https://github.com/RikkaApps/Shizuku) | Provides privileged Android system API access without requiring full root. |
| [Mirror](https://github.com/jqssun/android-display-mirror) | Creates the virtual display and exposes it through a built-in Sunshine server. |
| [Extend](https://github.com/jqssun/android-display-extend) | Optional but useful display manager for resolution/DPI, app placement and input/display controls. |
| [Moonlight](https://github.com/moonlight-stream/moonlight-android) | Runs on the second Android device and displays/controls the Sunshine stream. |
| [MagicDesk](https://github.com/mekhontsev/magicdesk) | Moves **already-running Android tasks** from one display to another. This is the important workaround for OEM desktop modes that intercept normal app launches. |

### Why MagicDesk matters

A normal "launch this app on display X" request can be intercepted by an OEM desktop environment.

That is exactly what happened in our Lenovo PC Mode test: when PC Mode was already running, **Extend → Cast Applications** caused Lenovo to open the application as a PC Mode window on the main tablet instead of placing it on the virtual Sunshine display.

MagicDesk solves a different problem: it can take an **existing running Android task** and move that task to another display. That avoided Lenovo's new-launch interception in our test.

## Requirements

For the exact workflow below:

- host device running **Android 14+** for current MagicDesk builds;
- Developer Options enabled;
- Shizuku started through Wireless Debugging, USB debugging or root;
- host and receiver on the same local network for the easiest Moonlight setup;
- Moonlight installed on the receiver;
- Mirror, Extend and MagicDesk installed on the host.

If you use a VPN on either device, temporarily disable it during initial setup if Moonlight discovery or pairing does not work. A VPN can work later if local-LAN traffic is bypassed correctly.

## Downloads

### Host Android device

- Shizuku: https://github.com/RikkaApps/Shizuku/releases
  - If you hit the specific UserService timeout described below on Shizuku 13.6.0, tested fallback: https://github.com/RikkaApps/Shizuku/releases/tag/v13.5.4
- Mirror: https://github.com/jqssun/android-display-mirror/releases/latest
- Extend: https://github.com/jqssun/android-display-extend/releases/latest
- MagicDesk: https://github.com/mekhontsev/magicdesk/releases/latest

### Receiver Android device

- Moonlight: https://play.google.com/store/apps/details?id=com.limelight
- Source/releases: https://github.com/moonlight-stream/moonlight-android

## Step 1 — Start Shizuku

On Android 11+ the easiest non-root method is usually Wireless Debugging:

1. Enable **Developer options**.
2. Enable **Wireless debugging**.
3. Open Shizuku.
4. Pair Shizuku with Android using **Pair device with pairing code**.
5. Start Shizuku.
6. Confirm that Shizuku reports that the service is running.

Authorize Mirror, Extend and MagicDesk when they request Shizuku access.

## Step 2 — Create the virtual display in Mirror

Open **Mirror** on the host and start a virtual display using the built-in Sunshine path.

Recommended starting settings from our test:

- **Send input to external display:** ON
- **Use H.265:** OFF initially for maximum compatibility; enable later if both devices handle it well
- **Show cursor location:** OFF
- **Auto connect Moonlight beta:** OFF while setting up manually

Mirror should create an Android display named something similar to:

```text
Sunshine [13]
```

The numeric display ID is temporary and can change whenever the virtual display is recreated.

## Step 3 — Connect Moonlight

On the receiver:

1. Open Moonlight.
2. Pair/connect to the Sunshine server exposed by Mirror.
3. Start the stream.

At this stage Moonlight may display:

> Please select application to cast via the managed display or use mirror only mode.

That is **normal**. It means the virtual display exists and is being streamed, but Android has not placed an application on it yet.

For direct touchscreen-style interaction rather than relative trackpad behavior, disable:

**Moonlight → Use touchscreen as a trackpad**

if that option is enabled on your receiver.

## Step 4 — Keep Extend's Managed Virtual Display Mode OFF

Extend can see the display created by Mirror and is useful for inspecting/configuring it.

However, in our tested configuration, enabling:

**Managed Virtual Display Mode**

caused Moonlight to disconnect and broke the working Mirror/Sunshine display lifecycle until the stream was restarted.

For this setup, leave **Managed Virtual Display Mode OFF**.

The virtual display should remain owned by Mirror/Sunshine.

## Step 5 — Give MagicDesk working shell access

Open MagicDesk.

The important state is:

```text
Access: shell
Service UID: 2000
```

Typical configuration:

- **Settings → Integrations → Privileged service:** Shizuku
- **Settings → Limits → Maximum access:** Shell

After changing MagicDesk startup/integration settings, use **Exit MagicDesk** and reopen it rather than only swiping it away from Recents.

Do **not** start MagicDesk Desktop just for this guide. We only need its independent display/task tools.

## Step 6 — Test task moving before enabling an OEM desktop mode

Before involving Lenovo PC Mode, DeX, or another vendor desktop shell:

1. Make sure Mirror/Sunshine is running.
2. Make sure Moonlight is connected.
3. Open an app such as Chrome on the host.
4. Open MagicDesk.
5. Select the **Sunshine [X]** display.
6. Open **Apps**.
7. Switch to **Running applications**.
8. Select Chrome.

MagicDesk should show an action similar to:

```text
Move from display 0 (task 123)
```

Select it.

Chrome should disappear from the host display and appear on the Moonlight receiver without a cold restart.

If this works, the core Android-to-Android extended-display setup is working.

## Step 7 — Use it together with Lenovo PC Mode or another OEM desktop mode

Now test the vendor desktop environment.

1. Keep Mirror/Sunshine and Moonlight running.
2. Enable the vendor desktop mode — for our tested device, **Lenovo PC Mode**.
3. Open the application you want on the host/PC Mode desktop.
4. Return to MagicDesk.
5. Select the virtual **Sunshine [X]** display.
6. Open **Apps → Running applications**.
7. Find the already-running application.
8. Choose **Move from display 0 ...**.

On our Lenovo TB375FC, this successfully moved the existing Chrome task from Lenovo PC Mode to the Sunshine virtual display while PC Mode remained active.

That gives you:

```text
Host tablet
├── Main physical display → Lenovo PC Mode
└── Virtual Sunshine display → independent Android app
                                  │
                                  └── Wi-Fi → Moonlight → second phone/tablet
```

## Important Lenovo PC Mode behavior we observed

### What did not work

With Lenovo PC Mode already enabled:

**Extend → Cast Applications → app**

was intercepted by Lenovo and the app opened as a window on the main PC Mode desktop instead of on the Sunshine virtual display.

### What did work

Two approaches worked:

1. **Pre-cast an app before enabling PC Mode.**  
   The app already living on the virtual display survived after PC Mode was enabled.

2. **Better: move an already-running task with MagicDesk.**  
   This allows PC Mode to be enabled first, then lets you move selected live tasks to Sunshine afterwards.

The second approach is the most useful workflow.

## Shizuku 13.6.0 + MediaTek UserService problem

This was the hardest issue in our test.

### Symptoms

Shizuku itself looked healthy and Mirror/Extend could use it, but MagicDesk stayed at:

```text
Access: none
Privileged service is connecting
```

MagicDesk Diagnostics showed:

```text
Privileged runtime: unavailable
WARN [SHELL-001] Privileged command service: Privileged service is connecting
Timed out waiting for privileged service binding
```

The tested device was a **MediaTek Dimensity 8300** device running **Shizuku 13.6.0.r1086**.

### Fix that worked for us

Downgrading Shizuku to:

**13.5.4**

immediately fixed MagicDesk's privileged UserService binding after Shizuku and MagicDesk were restarted and permissions were granted again.

After that MagicDesk reported shell access and task moving worked.

At the time of this test (**2026-10-01**), Shizuku 13.6.0 was the latest release and there were multiple open upstream reports relevant to this failure mode:

- [#1198 — User services don't work on MediaTek devices](https://github.com/RikkaApps/Shizuku/issues/1198)
- [#2443 — Shizuku hangs / stops responding to shell commands after Wi-Fi state changes (regression in 13.6.0)](https://github.com/RikkaApps/Shizuku/issues/2443)
- [#2463 — Had to downgrade from 13.6.0 to 13.5.4 after encountering problems](https://github.com/RikkaApps/Shizuku/issues/2463)

Issue #2463 also reports the unusual situation where the **13.6.0 app UI still shows “Version 13.5, adb”**. We observed the same mismatch on the tested Lenovo before downgrading.

### Recommendation

Do **not** blindly pin every device forever to Shizuku 13.5.4.

Start with the current Shizuku release. If all of these are true:

- Shizuku says it is running;
- MagicDesk permission has been granted;
- MagicDesk remains stuck on `Privileged service is connecting`;
- Diagnostics show a privileged service binding timeout;
- especially if the device uses a MediaTek SoC;

then testing the official [Shizuku 13.5.4 release](https://github.com/RikkaApps/Shizuku/releases/tag/v13.5.4) is a very worthwhile troubleshooting step.

Because this is version- and firmware-sensitive, do not downgrade unless the symptoms match. Future Shizuku releases may fix the regression; check the upstream issues and current release notes first.

## Troubleshooting

| Problem | What to check |
| --- | --- |
| Moonlight sees the host but only shows the "select application" message | Normal until a task is placed on the virtual display. Move/cast an app to Sunshine. |
| Touch acts like a laptop touchpad instead of direct touch | Disable **Use touchscreen as a trackpad** in Moonlight. |
| Moonlight cannot discover/pair | Put both devices on the same LAN; temporarily disable VPNs/firewalls; connect manually if needed. |
| Virtual display disappears/reappears with another number | Normal. Display IDs such as 8, 13, 14 are not permanent. Re-select the current Sunshine display in MagicDesk/Extend. |
| Extend casts back into Lenovo PC Mode instead of Sunshine | Use MagicDesk **Running applications** to move the already-running task instead of launching a new one. |
| Moonlight disconnects after enabling Extend Managed Virtual Display Mode | Disable Managed Virtual Display Mode and let Mirror own the virtual display. Restart Mirror/Sunshine if necessary. |
| MagicDesk says `Access: none` even though Shizuku permission was granted | Check Shizuku is running, MagicDesk integration is set to Shizuku, Maximum access is Shell, then **Exit MagicDesk** and reopen. |
| MagicDesk Diagnostics says `Timed out waiting for privileged service binding` on MediaTek | If using Shizuku 13.6.x, test 13.5.4. This fixed the exact issue on our TB375FC. |
| App refuses to move or crashes on secondary display | Some apps/OEM frameworks do not behave correctly on secondary displays. Test another app to separate app-specific behavior from display-stack problems. |

## Extend vs MagicDesk

These tools overlap, but they are not identical.

**Extend** is excellent for:

- selecting displays;
- launching/casting apps to a target display;
- resolution/DPI/orientation management;
- touchpad/touchscreen/input tools.

**MagicDesk** is especially useful here because it can:

- enumerate live running tasks;
- **move a specific existing task to another display**.

That distinction is what made the Lenovo PC Mode setup work.

## Why this is better than simple screen mirroring

Traditional screen mirroring shows the same content twice.

This setup creates a separate Android `VirtualDisplay`, so the receiver can show an application that is not visible on the host's physical screen.

That means a tablet can effectively become:

- display 1: OEM desktop/PC mode;
- display 2: another Android tablet;
- display 3: potentially another virtual/physical display, subject to device/firmware limits.

## Related projects

- Mirror: https://github.com/jqssun/android-display-mirror
- Extend: https://github.com/jqssun/android-display-extend
- Shizuku: https://github.com/RikkaApps/Shizuku
- Moonlight Android: https://github.com/moonlight-stream/moonlight-android
- MagicDesk: https://github.com/mekhontsev/magicdesk

## Tested, not guaranteed

Android multi-display behavior is heavily affected by:

- OEM firmware;
- Android version;
- desktop-mode implementation;
- application support for secondary displays;
- Shizuku/system API changes.

The Lenovo TB375FC result proves the workflow can work even when the OEM's own desktop mode does not expose the desired extended-display behavior, but other devices may behave differently.

If you confirm another device/ROM combination, please open a PR or issue with the model, Android version, firmware, Shizuku version, and what worked.
