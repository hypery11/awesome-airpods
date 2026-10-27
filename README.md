# Awesome AirPods [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

English | [繁體中文](README.zh-TW.md)

> A curated list of projects, tools, research, and resources for hacking, extending, and creatively using Apple AirPods / AirPods Pro / AirPods Max.

**Status:** First public curated list of its kind (as of 2026-10). Contributions welcome.

**Note:** There is currently **no public community custom firmware** you can flash onto AirPods. What exists today is protocol reverse-engineering, companion apps, firmware *image analysis*, and creative use of Apple's motion APIs.

---

## Contents

- [Start here](#start-here)
- [Protocol & reverse engineering](#protocol--reverse-engineering)
- [Companion apps](#companion-apps)
  - [Android](#android)
  - [Desktop (Windows / Linux / macOS)](#desktop-windows--linux--macos)
- [Motion, head tracking & creative hacks](#motion-head-tracking--creative-hacks)
- [Firmware analysis](#firmware-analysis)
- [Research & papers](#research--papers)
- [Closed-source / commercial (for reference)](#closed-source--commercial-for-reference)
- [Platform notes](#platform-notes)
- [Communities](#communities)
- [Related lists](#related-lists)
- [Contributing](#contributing)

---

## Start here

The projects people actually share. Everything below is the map around them, not a product catalog.

- **[LibrePods](https://github.com/librepods-org/librepods)** — The AAP implementation. ANC, in-ear detection, battery, gestures on Android / Linux.
- **[linux-client-for-airpods-pro](https://github.com/ozankenangungor/linux-client-for-airpods-pro)** — Read the AirPods Pro 3 heart-rate stream on Linux.
- **[whoisbadai](https://github.com/pavloshargan/whoisbadai)** — AirPod as a handheld IMU controller.
- **[HeadphoneMotion](https://github.com/kulich-ua/HeadphoneMotion)** — `CMHeadphoneMotionManager` demo.
- **[airtracker](https://github.com/crippler95/airtracker)** — AirPods as a low-latency head tracker (OpenTrack UDP).
- **[aap-head-tracker](https://github.com/FIocker/aap-head-tracker)** — AAP motion decoded for head tracking on Windows.

---

## Protocol & reverse engineering

Projects that document or implement Apple Accessory Protocol (AAP), Magic Pairing, and related Bluetooth stacks.

- **[LibrePods](https://github.com/librepods-org/librepods)** — Full AAP implementation unlocking ANC, in-ear detection, battery, gestures, Conversation Awareness, and more on Android / Linux. ([alt mirror](https://github.com/kavishdevar/librepods); [AAP Definitions](https://github.com/kavishdevar/librepods/blob/main/AAP%20Definitions.md))
- **[AAP-Protocol-Defintion](https://github.com/tyalie/AAP-Protocol-Defintion)** — Research notes on AAP / Magic Pairing packets and L2CAP PSM `0x1001`.
- **[apple-wireshark](https://github.com/pabloaul/apple-wireshark)** — Wireshark dissectors for various proprietary Apple Bluetooth protocols.
- **[librepods-rs](https://github.com/brianpht/librepods-rs)** — Minimal pure-Rust AAP implementation for Linux.
- **[airpods-helper](https://github.com/superninjv/airpods-helper)** — Linux Rust daemon: AAP over L2CAP, D-Bus, CLI, GTK4 widget.
- **[airpods-tui](https://github.com/annoyedmilk/airpods-tui)** — Linux Rust TUI + daemon over AACP: battery, noise modes, Conversation Awareness, stem settings, ear detection, Waybar JSON (GPL-3.0).
- **[MagicPodsCore](https://github.com/steam3d/MagicPodsCore)** — Open Linux backend (WebSocket API) for AirPods / Beats / Galaxy Buds / Pixel Buds: battery, noise control, and AirPods-exclusive settings (GPL-3.0).
- **[linux-client-for-airpods-pro](https://github.com/ozankenangungor/linux-client-for-airpods-pro)** — Reverse-engineered AirPods Pro 3 heart-rate stream on Linux: BlueZ daemon plus Rust / Python / C APIs and a desktop app.
- **[openulla](https://github.com/mstampfli/openulla)** — Reverse engineering of the AirPods Pro 2 (USB-C) H2 5 GHz lossless / low-latency link (firmware name ULLA): documents the AAP service-4 session setup, earbud state machine, and HCI / LMP steps, with a Linux probe that starts the session over PSM `0x1001`; the radio audio layer is not recovered yet (MIT).

---

## Companion apps

Battery status, ANC controls, in-ear detection, and “pop-up” style UX outside the Apple ecosystem.

### Android

- **[LibrePods](https://github.com/librepods-org/librepods)** — See protocol section; the leading open companion.
- **[CAPod](https://github.com/d4rken-org/capod)** — Battery, in-ear detection, lid-open popup; supports many AirPods / Beats generations.
- **[OpenPods](https://github.com/adolfintel/OpenPods)** — Early open-source Android battery / status monitor.
- **[GreenPods](https://github.com/andrewkomkov/GreenPods)** — No-root Android companion (Kotlin / Compose): BLE battery, ear detection and auto-pause, plus AAP over L2CAP for noise control, Conversation Awareness, stem settings, and head tracking on recent Android, with a per-feature table of what the OS allows (MIT).
- **[OpenPodsMax](https://github.com/sidnvy/OpenPodsMax)** — Android companion for AirPods Max 2 (no root or Shizuku): listening modes, Personalized Volume, Conversation Awareness, battery, pause on removal / resume when worn, plus experimental ADB-registered controls inside Android’s Connected devices settings; early release (GPL-3.0).
- **[HyperPods-X](https://github.com/YeFeng233/HyperPods-X)** — Android app + LSPosed module for Xiaomi HyperOS (Kotlin / Miuix): native HyperOS lid-open popup and Super Island battery, listening modes and AirPods-reported settings (EQ, press duration, single-bud ANC and more) written with read-back confirmation, Conversation Awareness media ducking, and spatial audio that feeds the real AirPods head pose into the system head tracker; preview release tested on HyperOS 4 with AirPods 5 (GPL-3.0).

### Desktop (Windows / Linux / macOS)

- **[AirPodsDesktop](https://github.com/SpriteOvO/AirPodsDesktop)** — Enhanced desktop experience on Windows / Linux (WIP): battery, media, etc.
- **[PodBridge](https://github.com/bhemsen/PodBridge)** — Open Windows companion without drivers: battery, auto play/pause, optional ANC.
- **[NTPods](https://github.com/arctumn/ntpods)** — Windows port that grew out of LibrePods: battery, noise control, ear detection, Conversation Awareness, hi-res mic, Pro 3 heart rate; drivers open too (GPL-3.0).
- **[winpods](https://github.com/sinanovicanes/winpods)** — Lightweight Windows companion (Rust): battery, connection status, tray, low-battery alerts, movable widget (MIT).
- **[Earlo](https://github.com/kylianxdev/Earlo)** (formerly PodPilot) — Windows 10/11 tray companion (C#) for AirPods, Beats and Galaxy Buds: iPhone-style case-open popup, per-bud battery, ear-detection auto-pause, one-click connect, stem-swipe volume indicator; noise modes and Conversation Awareness via an experimental driver (MIT).
- **[NEXRON AirPods Battery Widget](https://github.com/nexron-studios/NEXRON-airpods-battery-windows)** — Windows 10/11 always-on-top battery widget (Tauri + Vue) that decrypts the encrypted BLE battery advert for exact left / right / case levels, using the `MagicAccIRK` / `MagicAccEncKey` keys read once from a Mac keychain on the same Apple ID; offline (GPL-3.0).
- **[WPods](https://github.com/FPNDev/wpods)** — Windows 11 companion (C#) with its own open drivers: stereo playback while the mic is on (mic exposed as "Headset (A2DP)"), local noise-suppression mic modes, noise control incl. Adaptive, Conversation Awareness, Personalized Volume, Hearing Aid, Pro 3 heart rate, press settings, nearby popup; needs Test Mode with Secure Boot off (GPL-3.0).
- **[Near](https://github.com/jlbjulio/Near)** — Lightweight Windows companion (Rust): battery (left / right / case), case-open popup, auto-reconnect on earbud remove, ear-detection pause / resume, tray flyout (MIT).
- **[AirpodsBattery-Monitor-For-Mac](https://github.com/mohamed-arradi/AirpodsBattery-Monitor-For-Mac)** — macOS menu-bar battery / widget.
- **[pods-control](https://github.com/raulgg/pods-control)** — macOS CLI (Homebrew) to read / set AirPods and Beats listening mode (off, transparency, adaptive, ANC) and Conversation Awareness via undocumented CoreAudio properties (MIT). ([Alfred workflow](https://github.com/laipz8200/alfred-airpods) built on it)
- **[kAirPods](https://github.com/can1357/kAirPods)** — Native KDE Plasma 6 integration (Rust L2CAP backend + panel widget): battery, noise control, ear detection, auto play/pause (GPL-3.0).
- **[LinuxPods](https://github.com/Explor3Universe/LinuxPods)** — KDE Plasma 6 plasmoid + C++ daemon.
- **[airpods-plasmoid](https://github.com/MintOcha/airpods-plasmoid)** — Plasma 6 plasmoid: exact battery (incl. BLE when case opens nearby), listening modes (incl. Adaptive), stem / settings sync, ear detection, Conversation Awareness, and virtual spatial audio via `libmysofa` (MIT).
- **[EarPort](https://github.com/Anoryth/earport)** — GNOME Shell Quick Settings + C daemon over L2CAP: battery (incl. while on another device), noise modes, Conversation Awareness, ear detection, experimental Apple-device handoff (GPL-3.0).
- **[LinuxPods (GNOME)](https://github.com/mstroecker/LinuxPods)** — Separate native libadwaita app: BLE battery (exact 1% once it pulls the advertisement key over AAP), noise control, multi-pair switcher, battery in GNOME Settings; early stage (GPL-3.0).
- **[GnomePods](https://github.com/michaelcaxias/gnomepods)** — GNOME Shell top-bar extension front end for [LinuxPods](https://github.com/Explor3Universe/LinuxPods) `linuxpods-daemon`: per-bud / case battery, noise modes, Conversation Awareness, One-Bud ANC; auto-restarts the daemon if D-Bus or AirPods data drops (GPL-3.0).
- **[omarchy-pods](https://github.com/thisisgm/omarchy-pods)** — AirPods panel for Omarchy: per-pod / case battery, listening modes, adaptive level, Conversation Awareness, One-Bud ANC, ear detection (MIT).
- **[podctl](https://github.com/Rockykln/podctl)** — Linux CLI + daemon with a from-scratch AAP (L2CAP PSM `0x1001`) client: battery, listening modes, Conversation Awareness, ear-detection pause / resume, plus optional tray and case-open popup (Apache-2.0).
- **[MyPods](https://github.com/HanreichC/MyPods)** — Qt 6 / C++ Linux (and Windows) companion built on the MagicPods code base: Mac-style case-open popup, 1 % battery from decrypted BLE advertisements and AAP (handed to BlueZ / UPower), noise modes, Conversation Awareness, ear-detection pause, iPhone-to-PC auto handoff; tested on AirPods Max, Pro 3 support unverified, AI-assisted code (GPL-3.0).
- **[airpods-transparency-linux](https://github.com/Taardisaa/airpods-transparency-linux)** — Linux (Python, Qt) control center, tray, and JSON CLI over AACP: battery, listening modes, and custom Transparency tuning (amplification, tone, ambient noise reduction, Conversation Boost, own-voice level) per ear with presets and automatic backups; validated on Ubuntu 22.04 + AirPods Pro 3, early stage (GPL-3.0).
- **[airpods-tui](https://github.com/annoyedmilk/airpods-tui)** — Also listed under protocol; TUI + Waybar for Linux.
- **[airpods-helper](https://github.com/superninjv/airpods-helper)** — Also listed under protocol; includes GTK4 UI.
- **[MagicPodsCore](https://github.com/steam3d/MagicPodsCore)** — Also listed under protocol; Linux WebSocket backend.

---

## Motion, head tracking & creative hacks

Using AirPods IMU / head-tracking data for sports, VR, and controllers — the Kinapod-style track.

- **[whoisbadai](https://github.com/pavloshargan/whoisbadai)** — Open experiment by Kinapod’s author: use a left AirPod as a “digital whip” IMU controller.
- **[HeadphoneMotion](https://github.com/kulich-ua/HeadphoneMotion)** — Demo of Apple’s `CMHeadphoneMotionManager` headphone motion data.
- **[AirPodsPro-Motion-Sampler](https://github.com/tukuyo/AirPodsPro-Motion-Sampler)** — Classic iOS sample: live motion readout, head-driven cube / table scroll, CSV export via `CMHeadphoneMotionManager` (MIT).
- **[AirPosture](https://github.com/allenv0/AirPosture)** — iOS (open-sourced): turns AirPods head motion into a real-time posture coach (MIT).
- **[airpods-posture](https://github.com/anilsrml/airpods-posture)** — Linux: reads the AirPods head-tracking stream over AAP (BlueZ) and shows a slouch indicator in a KDE Plasma panel widget (GPL-3.0).
- **[airtracker](https://github.com/crippler95/airtracker)** — macOS: AirPods as low-latency head tracker, OpenTrack UDP out.
- **[aap-head-tracker](https://github.com/FIocker/aap-head-tracker)** — Windows: decode AAP motion (via MagicAAP) for head tracking.
- **[pods-head-tracker](https://github.com/batubozkan/pods-head-tracker)** — Raspberry Pi / any BlueZ Linux box opens the AirPods head-tracking stream and sends pitch / yaw to OpenTrack over Wi-Fi UDP or USB serial, optionally also acting as a USB sound card that forwards game audio to the AirPods (GPL-3.0).
- **[Headitude](https://github.com/DanielRudrich/Headitude)** — macOS: forwards AirPods orientation over OSC (MIT).
- **[Nod](https://github.com/ydisli/nod)** — macOS: hands-free pointer control with AirPods head tracking, aimed at accessibility / RSI.
- **[HeadControl](https://github.com/knockkeykey/HeadControl)** — macOS (Apple Silicon, AirPods Pro 2): bind six head gestures (tilt, turn, nod, shake) to global shortcuts or app switching, with per-gesture thresholds, calibration practice, and cross-talk testing (MIT).
- **[QuietGlass](https://github.com/clintonimaroo/quietglass)** — macOS: blur your screens when you look away, using AirPods head motion (or the camera).
- **[O-Pose](https://github.com/fengkaobanli/O-Pose)** — Android (OPPO ColorOS 16, root): read AirPods Pro 2 head tracking over AACP and drive system spatial audio.
- **[ZANKYO](https://github.com/shilokuma-inc/zankyo-apple)** — iOS / iPadOS / macOS / visionOS: one-handed BeatSaver rhythm game played with AirPods head motion.
- **[SkateFit Motion Lab](https://github.com/banddude/skatefit-airpods-motion)** — iOS experiment: records motion from a board-mounted AirPod plus the iPhone for skateboard trick / manual / landing detection, with a web tuning console (MIT).

---

## Firmware analysis

Tools for inspecting Apple micro-device firmware images — **not** flashable custom firmwares.

- **[ftab-dump](https://github.com/19h/ftab-dump)** — Extract files from Apple micro-device `rkos` ftab firmware images.

---

## Research & papers

- **[MagicPairing](https://arxiv.org/abs/2005.07255)** ([ACM](https://dl.acm.org/doi/10.1145/3395351.3399343)) — SEEMOO / TU Darmstadt reverse-engineering of Apple peripheral pairing and security.
- **[InternalBlue — magicpairing examples](https://github.com/seemoo-lab/internalblue/tree/master/examples/magicpairing)** — Research PoCs / examples related to Magic Pairing.

---

## Closed-source / commercial (for reference)

Not open source — listed so readers can compare feature sets and product directions.

- **[Kinapod](https://kinapod.com/)** — iOS app that turns AirPods IMU into a sports sensor (disc, run, bowling, cycling, golf, jianzi, …). Uses `CMHeadphoneMotionManager`; no public repo found.
- **[MagicPods](https://magicpods.app/)** — Popular paid Windows companion (often compared in LibrePods / PodBridge READMEs); open Linux backend is [MagicPodsCore](https://github.com/steam3d/MagicPodsCore).

---

## Platform notes

- **No public custom flash firmware:** Protocol RE and image analysis exist; community flashable CFW for AirPods does not (as of this writing).
- **Android Bluetooth limits:** Full AAP features may need specific stacks, Vendor ID spoofing, or elevated privileges depending on OEM — check each project’s docs.
- **iOS motion APIs:** Kinapod-style apps typically need Automatic Ear Detection off and the mounted bud as mic to keep the motion stream alive.
- **Models:** Feature coverage varies by generation (AirPods 1–4, Pro 1–3, Max, Beats). Prefer projects that publish a support matrix.

---

## Communities

- LibrePods Discord / discussion links — see the [LibrePods](https://github.com/librepods-org/librepods) README.
- Hacker News, Reddit (`r/AirPods`, `r/linux`, Android communities) — search “LibrePods”, “AAP”, “Kinapod”.

---

## Related lists

- **[awesome-apple-ecosystem](https://github.com/Enzo-zsh/awesome-apple-ecosystem)** — Broader Apple cross-platform tools; mentions AirPodsDesktop, LibrePods, MagicPods under Other (not AirPods-focused).

---

## Contributing

PRs welcome. Please:

1. Add every entry to **both** `README.md` (English) and `README.zh-TW.md` (Traditional Chinese), in the same section and order.
2. Prefer **open-source** projects with a clear license; closed-source goes under the commercial section.
3. One link per project; include a one-line description of what it actually does.
4. Do **not** list malware, credential stealers, or anything that impersonates Apple services for fraud.

### Wishlist

- More head-tracking / VR bridges
- Documented AAP opcode tables beyond LibrePods
- Verified Beats / non-AirPods Apple earbuds coverage matrices

---

## License

[CC0](https://creativecommons.org/publicdomain/zero/1.0/) — public domain dedication for the list text. Linked projects keep their own licenses.
