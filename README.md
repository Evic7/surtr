# Surtr ⚔️🔥


Surtr – Reliable Windows Automation When Other Tools Fail

[![GitHub stars](https://img.shields.io/github/stars/Evic7/surtr?style=social)](https://github.com/Evic7/surtr/stargazers)
[![GitHub release](https://img.shields.io/github/v/release/Evic7/surtr)](https://github.com/Evic7/surtr/releases)
[![Downloads](https://img.shields.io/github/downloads/Evic7/surtr/total)](https://github.com/Evic7/surtr/releases)

Many automation tools rely on fixed coordinates or fragile selectors. Scripts break when windows move, apps update, or screens change resolution.

**Surtr** uses **image detection and OCR** to find and interact with elements visually — making automation stable on dynamic UIs. It's a single lightweight app that also handles macros, web tasks, file monitoring, and more.

<!-- Replace with your best demo GIF (macro recorder or image click vs coordinate fail) -->
![Surtr Demo](assets/macro-recorder-demo.gif)  
*(Macro recorder capturing actions and replaying reliably)*
*(Image-based targeting works even if positions change)*

## Why Surtr?

- **Stable on changing UIs**: Clicks/buttons work via images or text — no more broken scripts from resizes or updates.
- **All-in-one tool**: Combines GUI automation, macro recording, web scraping/downloads, file watching, system monitoring, and JSON handling.
- **Easy to start**: Built-in macro recorder captures actions and generates scripts instantly.
- **Free & open-source**: Community edition has everything core. Pro adds remote browser control (WebUI).

| Feature                              | Surtr                                      | Power Automate / Ui.Vision / Others |
|--------------------------------------|--------------------------------------------|-------------------------------------|
| Image + OCR automation               | Yes (robust, packaged Tesseract)          | Limited / cloud-only                |
| Macro recorder → instant script      | Yes                                        | Rare                                |
| Remote desktop + multi-user WebUI    | Yes (Pro)                                  | Paid / cloud only                   |
| Segmented downloader (IDM-like)      | Yes (Fetcher)                              | No                                  |
| Fully offline & open-source          | Yes                                        | No                                  |
| Cross-platform roadmap               | Yes (Linux/macOS in the forge)            | Usually not                         |
| Price                                | Free / one-time Pro                        | Subscriptions                       |

Perfect for productivity workflows, testing, data entry, backups, or when other tools (like coordinate-based macros) let you down.

## Quick Start

1. Download the installer: [Latest Release](https://github.com/Evic7/surtr/releases/latest)
2. Run `surtr-setup-v4.0.exe` (optional: add to PATH)
3. Test: `surtr --version`

Create a script (`example.as`):
~~ Record actions instantly
startRecorder mymacro.as
~~ Do your mouse/keyboard actions, then stopRecorder
~~ Click a button by image (works anywhere on screen)
if seeImage save-button.png ?run mouse click
~~ Web download example
fetcher -fetch-download -url https://example.com/file.zip -saveto file.zip
textRun: `surtr run example.as`

## Key Features

- **Image & OCR targeting**: `seeImage`, `moveToWord`, `readScreen` — reliable on dynamic apps.
- **Macro recorder**: `startRecorder` / `stopRecorder` for instant scripts.
- **Web tools**: Built-in fetcher for scraping, API calls, segmented downloads.
- **File & system**: Watch folders, monitor resources, JSON ops, pixel checks.
- **Window control**: Focus, resize, screenshot specific apps.
- **Pro WebUI**: Remote access with live desktop view, visual script builder, file browser.

Full command reference in [documentation]((http://screenbot.cu.ma/docs.php)) or run `define` in Surtr.

## Installation

- Free: Download installer from [Releases](https://github.com/Evic7/surtr/releases)
- Pro upgrade: [Gumroad](https://evandervictor.gumroad.com/l/surtr)

## Examples

- Automate login even if window position changes.
- Monitor folder and restore files on change.
- Schedule or download large files with segmented support.

More in the repo examples folder (coming soon) or community scripts.

## Contributing & Feedback

Issues, suggestions, or PRs welcome!  
For support: Open an issue or email thescreenbot@gmail.com

If traditional automation tools have let you down — try Surtr.

🔥 Thanks for checking it out!

Made by Victor James

email: thescreenbot@gmail.com
