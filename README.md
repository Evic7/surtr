# Surtr ⚔️🔥
**The fire giant of desktop automation**

<img src="./assets/surtr-banner.png" alt="Surtr – Automate with fire" width="100%"/>

Surtr is the open-source automation engine forged in Ragnarök fire.  
One CLI. Zero mercy. Total control over mouse, keyboard, windows, files, web, and pixels — Windows today, Linux & macOS in the forge.

- Image & OCR automation that works when every other tool fails  
- Built-in macro recorder (startRecorder → instant script)  
- Full remote desktop streaming + multi-user WebUI (Pro)  
- Segmented web downloader (Fetcher), JSON engine, watchdog, pixel-perfect detection, and 200+ commands  
- 100% offline · Zero cloud · Pure fire

Formerly ScreenBot4. Now it has a name worthy of its power.

## Why Surtr?

| Feature                              | Surtr                                      | Power Automate / Ui.Vision / Others |
|--------------------------------------|--------------------------------------------|-------------------------------------|
| Image + OCR automation               | Yes (robust, packaged Tesseract)          | Limited / cloud-only                |
| Macro recorder → instant script      | Yes                                        | Rare                                |
| Remote desktop + multi-user WebUI    | Yes (Pro)                                  | Paid / cloud only                   |
| Segmented downloader (IDM-like)      | Yes (Fetcher)                              | No                                  |
| Fully offline & open-source          | Yes                                        | No                                  |
| Cross-platform roadmap               | Yes (Linux/macOS in the forge)            | Usually not                         |
| Price                                | Free / one-time Pro                        | Subscriptions                       |

## Core Features
- Mouse/keyboard control (coordinates + image-based)
- OCR text detection & interaction (`moveToText`, `readScreen`)
- Conditional logic, loops, labels, variables
- File/watchdog monitoring, JSON engine, base64, pixel color detection
- Built-in web fetcher & segmented downloader
- System monitoring (CPU, RAM, disk)
- Macro recorder (`startRecorder` / `stopRecorder`)
- Pro: Live desktop streaming, file browser, terminal, visual script builder

## Command Highlights
```as
~~ Click button even if position changes
seeImage save.png ?run click

~~ Highlight every occurrence of "Surtr"
textOnScreen eng Surtr dragToText all eng Surtr

~~ Wait for pixel color change (e.g. download finished)
waitPixelColor 100 100 #00FF00 60

~~ Record actions and generate script instantly
startRecorder recorded.as
~~ do stuff …
stopRecorder



Installation
Download surtr-setup-v4.0.exe from Releases
Run installer
(Optional) Add to PATH
surtr --version

Pro Version – WebUIRun webui4.exe → http://127.0.0.1:4444Live desktop streaming
File browser
Terminal console
Visual script builder
Multi-user sessions

Config tool: webuiconfig.exeRoadmapWindows v4.0 complete
Linux port (priority after 5k stars)
macOS port
Mobile controller app

CommunityX / Twitter: @evavictor456

Issues & feature requests welcome
Pull requests = instant legend status

Automate with fire.
The age of Surtr has begun.

Made by Evander Victor 

