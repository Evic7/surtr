# Surtr ⚔️🔥

**Reliable Windows Automation — Image & OCR Powered**

Surtr – Reliable Windows Automation When Other Tools Fail

[![GitHub stars](https://img.shields.io/github/stars/Evic7/surtr?style=social)](https://github.com/Evic7/surtr/stargazers)
[![GitHub release](https://img.shields.io/github/v/release/Evic7/surtr)](https://github.com/Evic7/surtr/releases)
[![Downloads](https://img.shields.io/github/downloads/Evic7/surtr/total)](https://github.com/Evic7/surtr/releases)

Many automation tools rely on fixed coordinates or fragile selectors. Scripts break when windows move, apps update, or screens change resolution.

Surtr is a free, open-source, lightweight tool that automates almost anything on Windows — especially when other tools break due to UI changes, window moves, app updates, or different resolutions.

Instead of fragile coordinates or brittle selectors, Surtr **looks at your screen like a human** — using **image detection** and **OCR (text recognition)** to find and interact with buttons, text, icons, and forms reliably.

![Surtr in action — clicking button by image even after resize](assets/surtr-image-click-demo.gif)  
*(Image-based automation survives window moves and resolution changes)*

## Why Choose Surtr?

- Works when coordinate-based macros fail  
- Built-in macro recorder turns actions into instant scripts  
- Powerful web downloader (often faster than IDM)  
- Advanced OCR for reading receipts, invoices, screenshots  
- **SurtrUI** desktop IDE + **WebUI** remote access — both completely free  
- Task Bot scheduler for unattended recurring jobs  
- No subscriptions, no ads, fully offline by default  

## Quick Start (2 minutes)

1. Download the latest release: [https://github.com/Evic7/surtr/releases/latest](https://github.com/Evic7/surtr/releases/latest)
2. Run the installer (adds to PATH automatically)
3. Open CMD and test:
surtr --version
text4. Launch the desktop IDE:  
Double-click surtrUI on the desktop or `surtrui.exe` in surtr installation folder (or run `surtrui`)
5. Launch WebUI (remote/browser control):  
Run `webuilauncher` → open http://127.0.0.1:4444  
Default login: admin / admin (change immediately!)

You now have:
- Local SurtrUI (IDE + Task Bot)
- Remote WebUI (browser access to desktop, scripts, files)

Full docs: [surtr.cu.ma/docs.php](http://surtr.cu.ma/docs.php) or run `define` in Surtr.

## How Surtr Works: The Basics

Surtr runs as a lightweight CLI tool, but shines through its **visual intelligence**:
- **Image Detection** (`seeImage`, `moveToWord`, `textOnScreen`)  
Searches screen for images or text → returns coordinates or true/false
- **OCR Engine** (`imageReader`, `readScreen`)  
Extracts text from live screen or images
- **Scripting (.as files)**  
Variables `{{var}}`, conditions `if ?run`, loops, labels, multi-line `^^ … ^^`
- **SurtrUI** — native IDE with visual builder, terminal, Task Bot
- **WebUI** — browser-based remote control (live desktop stream, file browser, terminal, script builder)

Everything runs locally — no cloud dependency.

## Power Feature #1 — Fetcher: Faster Downloads & Scraping

Fetcher is Surtr's built-in web tool — often **faster than IDM** thanks to parallel segmented downloads, retries, and backoff.

### Single Fast Download (beats IDM on big files)
<div align="center">
  <img src="assets/livedownload.png" width="48%" alt="Live fetcher download">
</div>
```
fetcher -fetch-download ^
-url https://example.com/linux.iso ^
-saveto linux.iso ^
-split-download 8 ^           # 8 parallel chunks
-chunk-size 4096 ^            # 4 MB per chunk
-retries 10 ^                 # retry up to 10 times
-backoff-factor 1.5 ^         # increasing delay on retry
-show-progress                # live progress bar
```
Multiple / Batch Downloads
Create downloads.json:
```
[
  {"url": "https://site.com/file1.zip", "save_as": "dl1.zip", "split_download": 6},
  {"url": "https://site.com/video.mp4", "save_as": "movie.mp4", "split_download": 12}
]
```
Run:
`fetcher -fetch-download-json downloads.json -max-worker 10`
→ Downloads 10 files concurrently, each split → finishes batch much faster.

Web Scraping with Fetcher

Fetch → parse → extract:
```fetcher -fetch '[{"url":"https://news.com/article","parser":"bs4","select":"div"}]'```

BS4 vs SBS4 parser — which to use?

BS4 (BeautifulSoup): full HTML parsing — accepts local file path even raw html text in the url field. Best for complex selectors, classes, nesting
Example: -select "div.article > p:first-child"
SBS4 (STRICT): only accepts http,https in the url field
Example: -select "p" → all paragraphs as plain text

Scrape Local HTML Files

```fetcher -fetch '[{"url":"C:\path\myfile.html","parser":"bs4","select":"div"}]'```

Power Feature #2 — imageReader (Advanced OCR)
Extract text from images, screenshots, receipts, invoices.

Basic:
`imageReader -image receipt.png -lang eng`

Best practices:

Clean low-contrast scans `imageReader -image scan.jpg -transform bw -min-conf 65 -psm 6`
Preserve columns/layout `imageReader -image invoice.png -char-width 9 -line-height 22 -save invoice.txt`
Silent + save `imageReader -image screenshot.png -hide-output -save result.txt`
Live screen OCR `screenShot temp.png ++ imageReader -image temp.png -lang eng`

Power Feature #3 — SurtrUI (Desktop IDE)
Launch: surtrui or double-click surtrUi

Three tabs:

Script Builder — visual editor, syntax highlighting, command buttons, run/save instantly
Terminal — type Surtr commands live, see output immediately
Surtr Task Bot — schedule anything (every 5 min, daily, weekly), monitor next run

SurtrUI screenshot — Script Builder + Task Bot

## Surtr in Action

<div align="center">
  <img src="assets/ide.png" width="48%" alt="SurtrUI Script Builder view">
  <img src="assets/taskbot.png" width="48%" alt="SurtrUi Taskbot view">
  <img src="assets/terminal.png" width="48%" alt="surtrUi Terminal view">
</div>


Power Feature #4 — WebUI (Remote Browser Control)

Launch: webuilauncher → open http://127.0.0.1:4444

<div align="center">
  <img src="assets/webuisettings0.png" width="48%" alt="Surtr Webui Settings 0 view">
  <img src="assets/webuisettings1.png" width="48%" alt="Surtr Webui Settings 1 view">
  <img src="assets/webuiclidashboard.png" width="48%" alt="surtr Webui CLI view">
</div>

Default login: admin / admin (change immediately!)
What you get in browser:

Live Desktop Stream — watch Surtr automate in real time
File Browser — explore/download files remotely
Terminal — run commands from anywhere
Script Builder — build/run scripts visually in browser

WebUI live desktop stream example

<div align="center">
  <img src="assets/webuilogin.png" width="48%" alt="Surtr Webui Login view">
  <img src="assets/dashboard.png" width="48%" alt="Surtr Webui Dashboard view">
  <img src="assets/webscriptbuilder.png" width="48%" alt="surtr Webui Script Builder view">
</div>



Security notes:

Change default password via webuiconfig.exe
Use strong password + limit max users (webuilauncher ... maxuser:2)
Runs locally — no external server needed

Security & Best Practices

Enable guest mode: guestUser on → blocks dangerous commands
Password protect: setSecurityPassword strongpass → activateSecurity
Use set {{onerror}} mylabel: to handle failures gracefully
Validate inputs: if {{input}} ?cntn bad ?run stop
Test in SurtrUI terminal before scheduling
Keep Surtr updated — fixes improve security

Quick Examples

Auto-click save button 
```
while not seeImage save-btn.png ?run wait 2
mouse click
```
Read price from screenshot
```
screenShot price.png ++ imageReader -image price.png -lang eng -save price.txt
```
Schedule daily backup
In SurtrUI Task Bot:
Command: fileman copy C:\Data D:\Backup
Interval: every day at 23:00

Download & Get Started
Latest Release → Download Installer
No ads. No tracking. No subscriptions.
Just powerful, reliable automation — completely free.
Made with 🔥 by Victor James
Questions or ideas? → Open an issue or email thescreenbot@gmail.com
Star the repo if it helps you — ⭐
