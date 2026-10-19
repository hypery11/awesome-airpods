# Awesome AirPods [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

[English](README.md) | 繁體中文

> 精選與 Apple AirPods／AirPods Pro／AirPods Max 相關的開源專案、工具、研究與資源：協定逆向、跨平台 Companion、運動感測創意應用等。

**狀態：** 第一份公開的同類精選清單（2026-10 起）。歡迎貢獻。

**說明：** 目前**沒有**可公開刷入 AirPods 的社群自製韌體。現況是協定逆向、Companion App、韌體映像**分析**，以及創意使用 Apple 運動 API。

---

## 目錄

- [從這裡開始](#從這裡開始)
- [協定與逆向](#協定與逆向)
- [Companion 應用](#companion-應用)
  - [Android](#android)
  - [桌面（Windows／Linux／macOS）](#桌面windowslinuxmacos)
- [運動、頭追與創意玩法](#運動頭追與創意玩法)
- [韌體分析](#韌體分析)
- [學術與安全研究](#學術與安全研究)
- [閉源／商業（對照用）](#閉源商業對照用)
- [平台限制說明](#平台限制說明)
- [社群](#社群)
- [相關列表](#相關列表)
- [貢獻](#貢獻)

---

## 從這裡開始

別人會轉發的是這幾個。下面是圍繞它們的地圖，不是產品目錄。

- **[LibrePods](https://github.com/librepods-org/librepods)** — AAP 實作。Android／Linux 上的降噪、入耳偵測、電量、手勢。
- **[linux-client-for-airpods-pro](https://github.com/ozankenangungor/linux-client-for-airpods-pro)** — 在 Linux 讀 AirPods Pro 3 心率。
- **[whoisbadai](https://github.com/pavloshargan/whoisbadai)** — 把 AirPod 當手持 IMU 控制器。
- **[HeadphoneMotion](https://github.com/kulich-ua/HeadphoneMotion)** — Apple 耳機運動 API 示範。
- **[airtracker](https://github.com/crippler95/airtracker)** — 低延遲頭追，輸出 OpenTrack UDP。
- **[aap-head-tracker](https://github.com/FIocker/aap-head-tracker)** — 在 Windows 解碼 AAP 運動資料做頭追。

---

## 協定與逆向

實作或文件化 Apple Accessory Protocol（AAP）、Magic Pairing 及相關藍牙協定的專案。

- **[LibrePods](https://github.com/librepods-org/librepods)** — 完整實作 AAP，在 Android／Linux 解鎖降噪、入耳偵測、電量、手勢、對話感知等。 ([alt mirror](https://github.com/kavishdevar/librepods); [AAP Definitions](https://github.com/kavishdevar/librepods/blob/main/AAP%20Definitions.md))
- **[AAP-Protocol-Defintion](https://github.com/tyalie/AAP-Protocol-Defintion)** — AAP／Magic Pairing 封包與 L2CAP PSM `0x1001` 研究筆記。
- **[apple-wireshark](https://github.com/pabloaul/apple-wireshark)** — 多種 Apple 專有藍牙協定的 Wireshark dissector。
- **[librepods-rs](https://github.com/brianpht/librepods-rs)** — 精簡的 Pure Rust AAP 實作（Linux）。
- **[airpods-helper](https://github.com/superninjv/airpods-helper)** — Linux Rust daemon：AAP over L2CAP、D-Bus、CLI、GTK4 widget。
- **[airpods-tui](https://github.com/annoyedmilk/airpods-tui)** — Linux Rust TUI＋daemon（AACP）：電量、降噪模式、對話感知、柄控設定、入耳偵測、Waybar JSON（GPL-3.0）。
- **[MagicPodsCore](https://github.com/steam3d/MagicPodsCore)** — 開源 Linux 後端（WebSocket API），支援 AirPods／Beats／Galaxy Buds／Pixel Buds：電量、降噪，以及 AirPods 專屬設定（GPL-3.0）。
- **[linux-client-for-airpods-pro](https://github.com/ozankenangungor/linux-client-for-airpods-pro)** — 逆向 AirPods Pro 3 心率資料流（Linux）：BlueZ daemon，附 Rust／Python／C API 與桌面 App。
- **[openulla](https://github.com/mstampfli/openulla)** — 逆向 AirPods Pro 2（USB-C）H2 晶片的 5 GHz 無損／低延遲連結（韌體內稱 ULLA）：記錄 AAP service 4 工作階段建立、耳機狀態機與 HCI／LMP 步驟，附可經 PSM `0x1001` 啟動工作階段的 Linux 探測工具；無線電音訊層尚未破解（MIT）。

---

## Companion 應用

在非 Apple 生態提供電量、降噪、入耳偵測、開蓋彈窗等體驗。

### Android

- **[LibrePods](https://github.com/librepods-org/librepods)** — 見協定章節；目前最完整的開源 Companion。
- **[CAPod](https://github.com/d4rken-org/capod)** — 電量、入耳偵測、開蓋彈窗；支援多代 AirPods／Beats。
- **[OpenPods](https://github.com/adolfintel/OpenPods)** — 早期 Android 開源電量／狀態監控。
- **[GreenPods](https://github.com/andrewkomkov/GreenPods)** — 免 root 的 Android 夥伴 App（Kotlin／Compose）：以 BLE 取得電量、入耳偵測與自動暫停，並在較新 Android 上經 L2CAP 走 AAP 控制降噪、對話感知、耳柄設定與頭部追蹤，附各功能在系統限制下是否可用的對照表（MIT）。

### 桌面（Windows／Linux／macOS）

- **[AirPodsDesktop](https://github.com/SpriteOvO/AirPodsDesktop)** — Windows／Linux（WIP）桌面體驗增強：電量、媒體等。
- **[PodBridge](https://github.com/bhemsen/PodBridge)** — Windows 免驅動開源 Companion：電量、自動播放暫停、可選 ANC。
- **[NTPods](https://github.com/arctumn/ntpods)** — 由 LibrePods Windows 移植獨立出來：電量、降噪、入耳偵測、對話感知、高音質麥克風、Pro 3 心率；驅動也開源（GPL-3.0）。
- **[winpods](https://github.com/sinanovicanes/winpods)** — 輕量 Windows Companion（Rust）：電量、連線狀態、系統匣、低電量提醒、可移動 Widget（MIT）。
- **[Near](https://github.com/jlbjulio/Near)** — 輕量 Windows Companion（Rust）：左右耳機／充電盒電量、開蓋彈窗、取出耳機時自動重連、入耳偵測暫停／續播、系統匣飛出面板（MIT）。
- **[AirpodsBattery-Monitor-For-Mac](https://github.com/mohamed-arradi/AirpodsBattery-Monitor-For-Mac)** — macOS 選單列電量／Widget。
- **[pods-control](https://github.com/raulgg/pods-control)** — macOS 命令列工具（Homebrew），透過未公開的 CoreAudio 屬性讀取／切換 AirPods 與 Beats 聆聽模式（關閉、通透、自適應、降噪）及對話感知（MIT）。 ([Alfred workflow](https://github.com/laipz8200/alfred-airpods)，以此為基礎的 Alfred workflow)
- **[kAirPods](https://github.com/can1357/kAirPods)** — 原生 KDE Plasma 6 整合（Rust L2CAP 後端＋面板小工具）：電量、降噪、入耳偵測、自動播放／暫停（GPL-3.0）。
- **[LinuxPods](https://github.com/Explor3Universe/LinuxPods)** — KDE Plasma 6 plasmoid + C++ daemon。
- **[airpods-plasmoid](https://github.com/MintOcha/airpods-plasmoid)** — Plasma 6 plasmoid：精確電量（含開蓋附近 BLE）、聆聽模式（含自適應）、柄控／設定同步、入耳偵測、對話感知，以及經 `libmysofa` 的虛擬空間音訊（MIT）。
- **[EarPort](https://github.com/Anoryth/earport)** — GNOME Shell Quick Settings＋C daemon（L2CAP）：電量（含在其他裝置使用時）、降噪模式、對話感知、入耳偵測、實驗性與 Apple 裝置交接（GPL-3.0）。
- **[LinuxPods (GNOME)](https://github.com/mstroecker/LinuxPods)** — 另一個同名專案，原生 libadwaita App：經 BLE 讀電量（透過 AAP 取得廣播金鑰後可精確到 1%）、降噪模式、多組耳機切換、電量顯示於 GNOME 設定；仍在早期（GPL-3.0）。
- **[GnomePods](https://github.com/michaelcaxias/gnomepods)** — GNOME Shell 頂列擴充，作為 [LinuxPods](https://github.com/Explor3Universe/LinuxPods) `linuxpods-daemon` 的前端：左右耳機／充電盒電量、降噪模式、對話感知、單耳降噪；daemon 的 D-Bus 或 AirPods 資料中斷時會自動重啟（GPL-3.0）。
- **[omarchy-pods](https://github.com/thisisgm/omarchy-pods)** — Omarchy 面板：左右耳機／充電盒電量、聆聽模式、自適應強度、對話感知、單耳降噪、入耳偵測（MIT）。
- **[podctl](https://github.com/Rockykln/podctl)** — Linux 命令列工具＋daemon，從零實作 AAP（L2CAP PSM `0x1001`）：電量、聆聽模式、對話感知、入耳偵測自動暫停／續播，另附可選系統匣與開蓋彈窗（Apache-2.0）。
- **[airpods-tui](https://github.com/annoyedmilk/airpods-tui)** — 亦列於協定章節；Linux TUI＋Waybar。
- **[airpods-helper](https://github.com/superninjv/airpods-helper)** — 亦列於協定章節；含 GTK4 UI。
- **[MagicPodsCore](https://github.com/steam3d/MagicPodsCore)** — 亦列於協定章節；Linux WebSocket 後端。

---

## 運動、頭追與創意玩法

把 AirPods 的 IMU／頭部追蹤資料用於運動、VR、控制器等——Kinapod 這條創意路線。

- **[whoisbadai](https://github.com/pavloshargan/whoisbadai)** — Kinapod 作者開源實驗：用左手 AirPod 當「數位鞭」IMU 控制器。
- **[HeadphoneMotion](https://github.com/kulich-ua/HeadphoneMotion)** — 示範 Apple `CMHeadphoneMotionManager` 耳機運動資料。
- **[AirPodsPro-Motion-Sampler](https://github.com/tukuyo/AirPodsPro-Motion-Sampler)** — 經典 iOS 範例：即時運動讀值、頭部驅動方塊／列表捲動、以 `CMHeadphoneMotionManager` 匯出 CSV（MIT）。
- **[AirPosture](https://github.com/allenv0/AirPosture)** — iOS（已開源）：用 AirPods 頭部運動做即時姿勢教練（MIT）。
- **[airpods-posture](https://github.com/anilsrml/airpods-posture)** — Linux：經 AAP（BlueZ）讀取 AirPods 頭追資料，在 KDE Plasma 面板小工具顯示駝背提示（GPL-3.0）。
- **[airtracker](https://github.com/crippler95/airtracker)** — macOS：把 AirPods 當低延遲頭追，輸出 OpenTrack UDP。
- **[aap-head-tracker](https://github.com/FIocker/aap-head-tracker)** — Windows：經 MagicAAP 解碼 AAP 運動資料做頭追。
- **[pods-head-tracker](https://github.com/batubozkan/pods-head-tracker)** — 用 Raspberry Pi 或任何有 BlueZ 的 Linux 開啟 AirPods 頭追資料流，經 Wi-Fi UDP 或 USB 序列埠把 pitch／yaw 送進 OpenTrack，也可兼當 USB 音效卡把遊戲聲音轉送到 AirPods（GPL-3.0）。
- **[Headitude](https://github.com/DanielRudrich/Headitude)** — macOS：把 AirPods 姿態以 OSC 轉發出去（MIT）。
- **[Nod](https://github.com/ydisli/nod)** — macOS：用 AirPods 頭追免手控制滑鼠游標，主打無障礙／RSI 使用者。
- **[QuietGlass](https://github.com/clintonimaroo/quietglass)** — macOS：轉頭不看螢幕時自動模糊，使用 AirPods 頭部運動（或鏡頭）。
- **[O-Pose](https://github.com/fengkaobanli/O-Pose)** — Android（OPPO ColorOS 16，需 root）：經 AACP 讀 AirPods Pro 2 頭追，驅動系統空間音訊。
- **[ZANKYO](https://github.com/shilokuma-inc/zankyo-apple)** — iOS／iPadOS／macOS／visionOS：用 AirPods 頭部動作單手遊玩 BeatSaver 譜面的節奏遊戲。
- **[SkateFit Motion Lab](https://github.com/banddude/skatefit-airpods-motion)** — iOS 實驗：把 AirPod 固定在滑板上、與 iPhone 一起記錄運動資料，用來偵測滑板招式／manual／落地，附網頁調參主控台（MIT）。

---

## 韌體分析

用於檢視 Apple 微型裝置韌體映像的工具——**不是**可刷入的自製韌體。

- **[ftab-dump](https://github.com/19h/ftab-dump)** — 從 Apple 微型裝置 `rkos` ftab 韌體映像抽出檔案。

---

## 學術與安全研究

- **[MagicPairing](https://arxiv.org/abs/2005.07255)** ([ACM](https://dl.acm.org/doi/10.1145/3395351.3399343)) — SEEMOO／TU Darmstadt 逆向 Apple 周邊配對與安全機制。
- **[InternalBlue — magicpairing examples](https://github.com/seemoo-lab/internalblue/tree/master/examples/magicpairing)** — 與 Magic Pairing 相關的研究 PoC／範例。

---

## 閉源／商業（對照用）

非開源，列出方便對照功能與產品方向。

- **[Kinapod](https://kinapod.com/)** — 把 AirPods IMU 當運動感測器的 iOS App（飛盤、跑步、保齡球、騎車、高爾夫、毽子等）。走 `CMHeadphoneMotionManager`；目前找不到公開 repo。
- **[MagicPods](https://magicpods.app/)** — 常見付費 Windows Companion（LibrePods／PodBridge README 常拿來對比）；開源 Linux 後端見 [MagicPodsCore](https://github.com/steam3d/MagicPodsCore)。

---

## 平台限制說明

- **無公開可刷韌體：** 有協定逆向與映像分析；截至目前，沒有社群可刷的 AirPods 自製韌體。
- **Android 藍牙限制：** 完整 AAP 功能可能依廠商需特定協定棧、Vendor ID spoof 或較高權限——請看各專案文件。
- **iOS 運動 API：** Kinapod 類 App 通常需關閉自動偵測耳朵，並讓掛載那隻當麥克風以維持運動資料流。
- **機型：** 功能依世代而異（AirPods 1–4、Pro 1–3、Max、Beats）；優先選有支援矩陣的專案。

---

## 社群

- LibrePods Discord／討論連結——見 [LibrePods](https://github.com/librepods-org/librepods) README。
- Hacker News、Reddit（`r/AirPods`、`r/linux`、Android 社群）——搜 “LibrePods”、“AAP”、“Kinapod”。

---

## 相關列表

- **[awesome-apple-ecosystem](https://github.com/Enzo-zsh/awesome-apple-ecosystem)** — 廣義 Apple 跨平台工具列表；Other 章節提到 AirPodsDesktop、LibrePods、MagicPods（非 AirPods 專題）。

---

## 貢獻

歡迎 PR。請：

1. 每個條目同時加到 `README.md`（英文）與 `README.zh-TW.md`（繁體中文），章節與順序一致。
2. 優先收錄有明確授權的開源專案；閉源放商業對照區。
3. 每個專案一個連結，簡述實際能做什麼。
4. 勿收錄惡意軟體、憑證竊取，或冒充 Apple 服務進行詐欺的內容。

### 想收還沒收

- 更多頭追／VR 橋接
- LibrePods 以外更完整的 AAP opcode 表
- 經驗證的 Beats／非 AirPods 耳塞支援矩陣

---

## 授權

列表文字採 [CC0](https://creativecommons.org/publicdomain/zero/1.0/)；各專案維持原授權。
