# Awesome AirPods [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of projects, tools, research, and resources for hacking, extending, and creatively using Apple AirPods / AirPods Pro / AirPods Max.
>
> 精選與 Apple AirPods／AirPods Pro／AirPods Max 相關的開源專案、工具、研究與資源：協定逆向、跨平台 Companion、運動感測創意應用等。

**Status / 狀態:** First public curated list of its kind (as of 2026-10). Contributions welcome.

**Note / 說明:** There is currently **no public community custom firmware** you can flash onto AirPods. What exists today is protocol reverse-engineering, companion apps, firmware *image analysis*, and creative use of Apple's motion APIs.  
目前**沒有**可公開刷入 AirPods 的社群自製韌體。現況是協定逆向、Companion App、韌體映像**分析**，以及創意使用 Apple 運動 API。

---

## Start here / 從這裡開始

The projects people actually share. Everything below is the map around them, not a product catalog.
別人會轉發的是這幾個。下面是圍繞它們的地圖，不是產品目錄。

- **[LibrePods](https://github.com/librepods-org/librepods)** — The AAP implementation. ANC, in-ear detection, battery, gestures on Android / Linux. / AAP 實作。Android／Linux 上的降噪、入耳偵測、電量、手勢。
- **[whoisbadai](https://github.com/pavloshargan/whoisbadai)** — AirPod as a handheld IMU controller. / 把 AirPod 當手持 IMU 控制器。
- **[HeadphoneMotion](https://github.com/kulich-ua/HeadphoneMotion)** — `CMHeadphoneMotionManager` demo. / Apple 耳機運動 API 示範。
- **[airtracker](https://github.com/crippler95/airtracker)** — AirPods as a low-latency head tracker (OpenTrack UDP). / 低延遲頭追，輸出 OpenTrack UDP。
- **[aap-head-tracker](https://github.com/FIocker/aap-head-tracker)** — AAP motion decoded for head tracking on Windows. / 在 Windows 解碼 AAP 運動資料做頭追。

---

## Contents / 目錄

- [Start here / 從這裡開始](#start-here--從這裡開始)
- [Protocol & reverse engineering / 協定與逆向](#protocol--reverse-engineering--協定與逆向)
- [Companion apps / Companion 應用](#companion-apps--companion-應用)
  - [Android](#android)
  - [Desktop (Windows / Linux / macOS) / 桌面](#desktop-windows--linux--macos--桌面)
- [Motion, head tracking & creative hacks / 運動、頭追與創意玩法](#motion-head-tracking--creative-hacks--運動頭追與創意玩法)
- [Firmware analysis / 韌體分析](#firmware-analysis--韌體分析)
- [Research & papers / 學術與安全研究](#research--papers--學術與安全研究)
- [Closed-source / commercial (for reference) / 閉源／商業（對照用）](#closed-source--commercial-for-reference--閉源商業對照用)
- [Platform notes / 平台限制說明](#platform-notes--平台限制說明)
- [Communities / 社群](#communities--社群)
- [Related lists / 相關列表](#related-lists--相關列表)
- [Contributing / 貢獻](#contributing--貢獻)

---

## Protocol & reverse engineering / 協定與逆向

Projects that document or implement Apple Accessory Protocol (AAP), Magic Pairing, and related Bluetooth stacks.

實作或文件化 Apple Accessory Protocol（AAP）、Magic Pairing 及相關藍牙協定的專案。

- **[LibrePods](https://github.com/librepods-org/librepods)** — Full AAP implementation unlocking ANC, in-ear detection, battery, gestures, Conversation Awareness, and more on Android / Linux. / 完整實作 AAP，在 Android／Linux 解鎖降噪、入耳偵測、電量、手勢、對話感知等。 ([alt mirror](https://github.com/kavishdevar/librepods); [AAP Definitions](https://github.com/kavishdevar/librepods/blob/main/AAP%20Definitions.md))
- **[AAP-Protocol-Defintion](https://github.com/tyalie/AAP-Protocol-Defintion)** — Research notes on AAP / Magic Pairing packets and L2CAP PSM `0x1001`. / AAP／Magic Pairing 封包與 L2CAP PSM `0x1001` 研究筆記。
- **[apple-wireshark](https://github.com/pabloaul/apple-wireshark)** — Wireshark dissectors for various proprietary Apple Bluetooth protocols. / 多種 Apple 專有藍牙協定的 Wireshark dissector。
- **[librepods-rs](https://github.com/brianpht/librepods-rs)** — Minimal pure-Rust AAP implementation for Linux. / 精簡的 Pure Rust AAP 實作（Linux）。
- **[airpods-helper](https://github.com/superninjv/airpods-helper)** — Linux Rust daemon: AAP over L2CAP, D-Bus, CLI, GTK4 widget. / Linux Rust daemon：AAP over L2CAP、D-Bus、CLI、GTK4 widget。

---

## Companion apps / Companion 應用

Battery status, ANC controls, in-ear detection, and “pop-up” style UX outside the Apple ecosystem.

在非 Apple 生態提供電量、降噪、入耳偵測、開蓋彈窗等體驗。

### Android

- **[LibrePods](https://github.com/librepods-org/librepods)** — See protocol section; the leading open companion. / 見協定章節；目前最完整的開源 Companion。
- **[CAPod](https://github.com/d4rken-org/capod)** — Battery, in-ear detection, lid-open popup; supports many AirPods / Beats generations. / 電量、入耳偵測、開蓋彈窗；支援多代 AirPods／Beats。
- **[OpenPods](https://github.com/adolfintel/OpenPods)** — Early open-source Android battery / status monitor. / 早期 Android 開源電量／狀態監控。

### Desktop (Windows / Linux / macOS) / 桌面

- **[AirPodsDesktop](https://github.com/SpriteOvO/AirPodsDesktop)** — Enhanced desktop experience on Windows / Linux (WIP): battery, media, etc. / Windows／Linux（WIP）桌面體驗增強：電量、媒體等。
- **[PodBridge](https://github.com/bhemsen/PodBridge)** — Open Windows companion without drivers: battery, auto play/pause, optional ANC. / Windows 免驅動開源 Companion：電量、自動播放暫停、可選 ANC。
- **[AirpodsBattery-Monitor-For-Mac](https://github.com/mohamed-arradi/AirpodsBattery-Monitor-For-Mac)** — macOS menu-bar battery / widget. / macOS 選單列電量／Widget。
- **[LinuxPods](https://github.com/Explor3Universe/LinuxPods)** — KDE Plasma 6 plasmoid + C++ daemon. / KDE Plasma 6 plasmoid + C++ daemon。
- **[airpods-helper](https://github.com/superninjv/airpods-helper)** — Also listed under protocol; includes GTK4 UI. / 亦列於協定章節；含 GTK4 UI。

---

## Motion, head tracking & creative hacks / 運動、頭追與創意玩法

Using AirPods IMU / head-tracking data for sports, VR, and controllers — the Kinapod-style track.

把 AirPods 的 IMU／頭部追蹤資料用於運動、VR、控制器等——Kinapod 這條創意路線。

- **[whoisbadai](https://github.com/pavloshargan/whoisbadai)** — Open experiment by Kinapod’s author: use a left AirPod as a “digital whip” IMU controller. / Kinapod 作者開源實驗：用左手 AirPod 當「數位鞭」IMU 控制器。
- **[HeadphoneMotion](https://github.com/kulich-ua/HeadphoneMotion)** — Demo of Apple’s `CMHeadphoneMotionManager` headphone motion data. / 示範 Apple `CMHeadphoneMotionManager` 耳機運動資料。
- **[airtracker](https://github.com/crippler95/airtracker)** — macOS: AirPods as low-latency head tracker, OpenTrack UDP out. / macOS：把 AirPods 當低延遲頭追，輸出 OpenTrack UDP。
- **[aap-head-tracker](https://github.com/FIocker/aap-head-tracker)** — Windows: decode AAP motion (via MagicAAP) for head tracking. / Windows：經 MagicAAP 解碼 AAP 運動資料做頭追。

---

## Firmware analysis / 韌體分析

Tools for inspecting Apple micro-device firmware images — **not** flashable custom firmwares.

用於檢視 Apple 微型裝置韌體映像的工具——**不是**可刷入的自製韌體。

- **[ftab-dump](https://github.com/19h/ftab-dump)** — Extract files from Apple micro-device `rkos` ftab firmware images. / 從 Apple 微型裝置 `rkos` ftab 韌體映像抽出檔案。

---

## Research & papers / 學術與安全研究

- **[MagicPairing](https://arxiv.org/abs/2005.07255)** ([ACM](https://dl.acm.org/doi/10.1145/3395351.3399343)) — SEEMOO / TU Darmstadt reverse-engineering of Apple peripheral pairing and security. / SEEMOO／TU Darmstadt 逆向 Apple 周邊配對與安全機制。
- **[InternalBlue — magicpairing examples](https://github.com/seemoo-lab/internalblue/tree/master/examples/magicpairing)** — Research PoCs / examples related to Magic Pairing. / 與 Magic Pairing 相關的研究 PoC／範例。

---

## Closed-source / commercial (for reference) / 閉源／商業（對照用)

Not open source — listed so readers can compare feature sets and product directions.

非開源，列出方便對照功能與產品方向。

- **[Kinapod](https://kinapod.com/)** — iOS app that turns AirPods IMU into a sports sensor (disc, run, bowling, cycling, golf, jianzi, …). Uses `CMHeadphoneMotionManager`; no public repo found. / 把 AirPods IMU 當運動感測器的 iOS App（飛盤、跑步、保齡球、騎車、高爾夫、毽子等）。走 `CMHeadphoneMotionManager`；目前找不到公開 repo。
- **[MagicPods](https://magicpods.app/)** — Popular paid Windows companion (often compared in LibrePods / PodBridge READMEs). / 常見付費 Windows Companion（LibrePods／PodBridge README 常拿來對比）。

---

## Platform notes / 平台限制說明

- **No public custom flash firmware / 無公開可刷韌體:** Protocol RE and image analysis exist; community flashable CFW for AirPods does not (as of this draft). / 有協定逆向與映像分析；截至本草稿，沒有社群可刷的 AirPods 自製韌體。
- **Android Bluetooth limits / Android 藍牙限制:** Full AAP features may need specific stacks, Vendor ID spoofing, or elevated privileges depending on OEM — check each project’s docs. / 完整 AAP 功能可能依廠商需特定協定棧、Vendor ID spoof 或較高權限——請看各專案文件。
- **iOS motion APIs / iOS 運動 API:** Kinapod-style apps typically need Automatic Ear Detection off and the mounted bud as mic to keep the motion stream alive. / Kinapod 類 App 通常需關閉自動偵測耳朵，並讓掛載那隻當麥克風以維持運動資料流。
- **Models / 機型:** Feature coverage varies by generation (AirPods 1–4, Pro 1–2, Max, Beats). Prefer projects that publish a support matrix. / 功能依世代而異；優先選有支援矩陣的專案。

---

## Communities / 社群

- LibrePods Discord / discussion links — see the [LibrePods](https://github.com/librepods-org/librepods) README. / 見 LibrePods README 內的 Discord／討論連結。
- Hacker News, Reddit (`r/AirPods`, `r/linux`, Android communities) — search “LibrePods”, “AAP”, “Kinapod”. / 在 HN、Reddit 搜 “LibrePods”、“AAP”、“Kinapod”。

---

## Related lists / 相關列表

- **[awesome-apple-ecosystem](https://github.com/Enzo-zsh/awesome-apple-ecosystem)** — Broader Apple cross-platform tools; mentions AirPodsDesktop, LibrePods, MagicPods under Other (not AirPods-focused). / 廣義 Apple 跨平台工具列表；Other 章節提到 AirPodsDesktop、LibrePods、MagicPods（非 AirPods 專題）。

---

## Contributing / 貢獻

PRs welcome. Please:

1. Keep entries **bilingual** (English + Traditional Chinese) in the `Name — EN. / 繁中。` format used above. / 條目請維持 **中英雙語**，格式同上。
2. Prefer **open-source** projects with a clear license; closed-source goes under the commercial section. / 優先收錄有明確授權的開源；閉源放商業對照區。
3. One link per project; include a one-line description of what it actually does. / 每個專案一個連結；簡述實際能做什麼。
4. Do **not** list malware, credential stealers, or anything that impersonates Apple services for fraud. / 勿收錄惡意軟體、憑證竊取，或冒充 Apple 服務進行詐欺的內容。

### Wishlist / 想收還沒收

- More head-tracking / VR bridges / 更多頭追／VR 橋接
- Documented AAP opcode tables beyond LibrePods / LibrePods 以外更完整的 AAP opcode 表
- Verified Beats / non-AirPods Apple earbuds coverage matrices / 經驗證的 Beats／非 AirPods 耳塞支援矩陣

---

## License / 授權

[CC0](https://creativecommons.org/publicdomain/zero/1.0/) — public domain dedication for the list text. Linked projects keep their own licenses.  
列表文字採 CC0；各專案維持原授權。
