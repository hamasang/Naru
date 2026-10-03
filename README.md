<p align="center">
  <img src="docs/icon.png" width="128" height="128" alt="Naru icon">
</p>

<h1 align="center">Naru</h1>

<p align="center"><b>Your phone, at home in Finder.</b><br>
Plug in your Android phone and it shows up in the Finder sidebar — just like a USB drive.</p>

<p align="center">English · <a href="README.ko.md">한국어</a></p>

---

## What it does

Naru puts your Android phone under **Locations** in the Finder sidebar, with an
eject button, the moment you plug it in. Browse, open, copy, edit, rename and
delete files the way you do on any other drive.

- **Feels like a USB drive** — shows up in the Finder sidebar, opens a Finder
  window automatically, ejects like a disk.
- **Read and write** — drag files in and out, edit documents in place,
  create folders, rename, move and delete.
- **Automatic** — Naru lives in the menu bar and starts at login. Plug in the
  phone and it mounts; unplug it and everything is cleaned up.
- **No ADB, no Developer Options** — on the phone you only choose
  **File transfer**.
- **Apple-native** — built on Apple's FSKit with its own USB MTP
  implementation. No kernel extensions, no third-party drivers.
- **Private** — everything runs locally. Naru makes no network connections and
  collects no data.

## Requirements

- A Mac with Apple silicon running **macOS 27** or later
- An Android phone and a USB cable that carries data

## Install

1. Download the latest **Naru-*version*.dmg** from **[Releases](https://github.com/hamasang/Naru/releases/latest)**.
2. Open the DMG and drag **Naru** into **Applications**.
3. Open **Naru**. Its icon appears in the menu bar.
4. **Turn on the file system extension** (one time).
   macOS asks you to allow third-party file systems yourself:
   **System Settings → General → Login Items & Extensions →
   File System Extensions → Naru**.
   When you connect a phone while it's off, Naru shows a notification — click it
   to jump straight to that setting.
5. When asked, allow Naru to:
   - **send notifications** — so it can tell you when something needs your attention;
   - **control Finder** — so the phone opens in a regular Finder window with the sidebar.

Naru is signed with an Apple Developer ID and notarized by Apple, so it opens
without a Gatekeeper warning.

## Use

1. Connect the phone with a USB cable and **unlock** it.
2. In the USB notification on the phone, choose **File transfer**.
3. The phone appears in Finder under **Locations** and a Finder window opens.
4. When you're done, click **⏏** next to it in the sidebar (or **Eject** in the
   Naru menu) before unplugging.

Menu bar options:

| Option | What it does |
|---|---|
| **Open in Finder** | Opens the phone in a Finder window |
| **Mount / Eject** | Connect or disconnect manually |
| **Mount Automatically** | Mount whenever a phone is plugged in (on by default) |
| **Launch at Login** | Start Naru when you log in (on by default) |

If you eject the phone in Finder, Naru won't remount it until you unplug and
reconnect it.

## Good to know

- **One app at a time.** Only one app can talk to a phone over MTP. Quit
  Android File Transfer, OpenMTP, Image Capture or similar apps first.
- **Unlock the phone.** Android hides its storage while the phone is locked.
  Naru keeps retrying for a minute, so just unlock it.
- **Changes made on the phone** appear when you reopen the folder in Finder
  (folder listings are refreshed after a few seconds).
- **macOS metadata stays on the Mac.** Files like `.DS_Store` and `._*` are
  never written to your phone.
- **After updating Naru**, check that the extension is still on in System
  Settings. Naru will notify you if it isn't.
- Editing files in place relies on Android's MTP extensions. Other MTP devices
  (cameras, media players) can be browsed and read, but writing may not work.

## Troubleshooting

| Problem | Try this |
|---|---|
| Menu says "File system extension is turned off" | Turn on **Naru** in System Settings → General → Login Items & Extensions → File System Extensions. |
| "No phone connected" while it's plugged in | Choose **File transfer** on the phone. Try another cable or port — some cables only charge. |
| Mount fails: "could not open the MTP interface" | Another app is using the phone. Quit other file-transfer or photo apps. |
| The phone stops responding | Unplug and reconnect the cable. |
| Finder window has no sidebar | Allow Naru under System Settings → Privacy & Security → Automation → Finder. |

## How it works

FSKit only presents block devices as local, ejectable volumes, and a phone over
MTP isn't one. So when a phone is connected, Naru attaches a tiny 1 MB "marker"
disk image. macOS hands it to Naru's FSKit extension, which mounts it as a
normal local volume and serves your phone's files over USB instead of the
image's contents. The extension speaks MTP directly through IOKit, and writes
use Android's partial-edit commands, so files are changed in place on the phone.

## Disclaimer

Naru is an independent project and is not affiliated with or endorsed by Google
or Apple. Android is a trademark of Google LLC. macOS and Finder are trademarks
of Apple Inc.
