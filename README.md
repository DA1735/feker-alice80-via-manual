# FEKER Alice 80 – VIA Configuration Notes (macOS)

This repository documents **verified, practical procedures**
for configuring the FEKER Alice 80 mechanical keyboard with VIA on macOS.

It focuses on **reproducible steps and technical constraints**.
Personal preferences and recommended layouts are intentionally omitted.

---

## このリポジトリについて（Japanese）

本リポジトリは、**macOS 環境における FEKER Alice 80 + VIA 設定**について、
実際に動作確認できた手順と制約のみをまとめた技術メモです。

- 試行錯誤が必要だったポイントを明文化
- VIA が認識しない理由を因果関係で説明
- macOS 側の制約（ファンクションキー／入力監視）を含む

個人の好みやおすすめ配列は記載していません。

---

## Scope / 対象範囲

- ✅ macOS
- ✅ FEKER Alice 80
- ✅ VIA (desktop application)

Not covered:
- Custom layouts or keymap recommendations
- Performance tuning
- Firmware modification

---

## Documentation

### Practical Manuals

- 🇯🇵 **Japanese**  
  `practical/feker_alice80_via_mac_practical_manual_ja.md`

- 🇬🇧 **English**  
  `practical/feker_alice80_via_mac_practical_manual.md`

Each document describes:
- Why VIA does not detect the keyboard automatically
- Why `Searching for device...` never finishes
- Required macOS settings
- Verified Fn / layer behavior

---

## FN + Key Quick Reference (Hardware Functions)

These are **hardware-level functions** built into the keyboard firmware.
They work regardless of VIA configuration.

### Japanese / 日本語

| FN + キー | Mac 機能 |
|---|---|
| Esc | ` 入力 |
| Esc + Shift | ~ 入力 |
| \|\\ | LED色の切り替え |
| Del | LEDエフェクトの切り替え |
| L | LEDのON/OFF |
| M | 消音 |
| Backspace | 3秒長押しで初期化 |
| Page up | — |
| Page down | — |
| ↑ | LED輝度を上げる |
| ↓ | LED輝度を下げる |
| C | Bluetooth 1 に接続 |
| V | Bluetooth 2 に接続 |
| B | Bluetooth 3 に接続 |
| G | 2.4GHzレシーバーに接続 |
| N | USB有線接続に切り替え |

### English

| FN + Key | Mac Function |
|---|---|
| Esc | Input ` |
| Esc + Shift | Input ~ |
| \|\\  | Cycle LED colors |
| Del | Cycle LED effects |
| L | Toggle LED on/off |
| M | Mute audio |
| Backspace | Hold 3s to factory reset |
| Page up | — |
| Page down | — |
| ↑ | Increase LED brightness |
| ↓ | Decrease LED brightness |
| C | Connect to Bluetooth slot 1 |
| V | Connect to Bluetooth slot 2 |
| B | Connect to Bluetooth slot 3 |
| G | Connect to 2.4GHz receiver |
| N | Switch to USB wired mode |

---

## Firmware Update Note (Windows Required)

In some cases, firmware update may be required **before VIA works correctly**.

At the time of writing, firmware update tools for FEKER Alice 80
are provided **for Windows only**.

If VIA does not work as expected even after:
- loading the official VIA JSON file
- using wired mode
- verifying macOS settings

please check the official vendor site and perform firmware update on Windows.

After firmware update, VIA configuration can be performed on macOS.

---

## Official Resources (Links Only)

This repository does **NOT** redistribute official manuals, firmware,
drivers, or VIA JSON files.

Please refer to the official sources below:

- FEKER Alice 80 Keyboard Manual  
  https://manuals.plus/ja/feker/alice-80-keyboard-manual

- How to Use and Upgrade FEKER Alice80 Mechanical Keyboard to Support VIA  
  https://www.whatgeek.com/pages/how-to-use-and-upgrade-feker-alice80-mechanical-keyboard-to-support-via

- EPOMAKER FEKER Alice Driver Page  
  https://epomaker.com/blogs/software/epomaker-feker-alice-driver

---

## Notes on VIA JSON Files

- Official VIA JSON files are downloaded separately
- They are **intentionally excluded** from this repository via `.gitignore`
- This repository documents behavior observed using official JSON files,
  but does not redistribute them

---

## License

MIT License

This repository contains only original documentation
based on observed behavior.
