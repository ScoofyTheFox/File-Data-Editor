<div align="center">

# 🗂️ File Data Editor
### by [scoofyx](https://github.com/scoofyx) · © 2026

*View, edit, spoof, wipe, and export image metadata — in the browser or terminal.*

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20macOS%20%7C%20Linux-blue)
![Python](https://img.shields.io/badge/python-3.8%2B-green)
![Browser](https://img.shields.io/badge/browser-any-orange)

---

<img width="2559" height="1305" alt="Screenshot 2026-03-20 123122" src="https://github.com/user-attachments/assets/78663b10-b174-475e-993f-fc205bff825b" />

</div>

---

## 📌 What is EXIF?

EXIF *(Exchangeable Image File Format)* is hidden metadata baked into every image file.
It records things like camera model, GPS coordinates, date taken, lens settings, ISO, and more.
Every photo you shoot with a phone or camera has it — most people never see it.

**File Data Editor** lets you see all of it, and change any of it.

---

## ⚡ Quick Start

> ### 🏆 Recommendation — Use the Web Version
>
> Open `medit-site/medit.html` in your browser. That's it.
> No Python, no install, no terminal. Works on any device with a browser.
> The CLI is a bonus for power users and batch automation.

---

## 🌐 Web Version `[RECOMMENDED]`

<img width="810" height="453" alt="Screenshot 2026-03-20 123652" src="https://github.com/user-attachments/assets/31694d31-d705-4a89-ab12-a083221d3eb7" />

### Usage
1. Open `medit-site/medit.html` in any browser
2. Drag & drop your image (or click to browse)
3. Pick a category from the sidebar
4. Click any field → type a new value → it saves instantly
5. Hit **↓ Download** to get your edited image

<img width="2523" height="1149" alt="Screenshot 2026-03-20 123831" src="https://github.com/user-attachments/assets/e8f2c835-f3c7-43f7-bfe8-5b940b2a21d3" />

### Supported Formats

| Format | View | Edit | Download with edits |
|--------|------|------|---------------------|
| JPG / JPEG | ✅ | ✅ | ✅ Full support |
| PNG | ✅ | ✅ | ⚠️ Re-downloads original |
| GIF | ✅ | ✅ | ⚠️ Re-downloads original |
| WEBP | ✅ | ✅ | ⚠️ Re-downloads original |

> EXIF embedding on download is JPEG-only due to a browser limitation. Use JPG for the full experience.

---

## 💻 CLI Version

<img width="1466" height="1051" alt="Screenshot 2026-03-20 124419" src="https://github.com/user-attachments/assets/c2abf540-b082-4a5f-a781-ed2172c008a2" />

### Install

```bash
pip install -r medit-cmd/requirements.txt
```

### Run

```bash
# Drop image.jpg in the same folder, then:
py medit.py

# Or pass a path directly:
py medit.py "C:\Users\you\Pictures\photo.jpg"
```

Works in both **cmd** and **PowerShell**.

### Dependencies

```
Pillow>=10.0.0
piexif>=1.1.3
cryptography>=41.0.0
numpy>=1.24.0
```

---

## 🖥️ Setup by OS

### 🪟 Windows

<details>
<summary>Click to expand</summary>

**1. Install Python**
- Go to [python.org/downloads](https://python.org/downloads) and download the latest 3.x installer
- ✅ Check **"Add Python to PATH"** during install — this is important

**2. Download the project**
- Click **Code → Download ZIP** on GitHub, then extract it

**3. Install dependencies**
- Open the `medit-cmd` folder
- Hold `Shift` + right-click inside the folder → **Open PowerShell window here**
- Run:
```powershell
pip install -r requirements.txt
```

**4. Run**
```powershell
py medit.py
```

**Web version:** just double-click `medit-site/medit.html` — opens in your default browser.

</details>

---

### 🍎 macOS

<details>
<summary>Click to expand</summary>

**1. Install Python**

macOS may have Python 2 built in — you need Python 3. Use Homebrew:
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
brew install python
```

Or download directly from [python.org/downloads](https://python.org/downloads).

**2. Download the project**
- Click **Code → Download ZIP** on GitHub, then extract it
- Or clone it:
```bash
git clone https://github.com/scoofyx/file-data-editor.git
cd file-data-editor
```

**3. Install dependencies**
```bash
cd medit-cmd
pip3 install -r requirements.txt
```

**4. Run**
```bash
python3 medit.py
```

**Web version:** double-click `medit-site/medit.html` — or right-click → Open With → your browser.

</details>

---

### 🐧 Linux

<details>
<summary>Click to expand</summary>

**1. Install Python & pip**

Python 3 is usually pre-installed. If not:
```bash
# Ubuntu / Debian
sudo apt update && sudo apt install python3 python3-pip

# Arch
sudo pacman -S python python-pip

# Fedora
sudo dnf install python3 python3-pip
```

**2. Download the project**
```bash
git clone https://github.com/scoofyx/file-data-editor.git
cd file-data-editor
```

**3. Install dependencies**
```bash
cd medit-cmd
pip3 install -r requirements.txt
```

If you get a permissions error, use:
```bash
pip3 install -r requirements.txt --user
```

**4. Run**
```bash
python3 medit.py
```

**Web version:** open `medit-site/medit.html` in Firefox or Chromium.
```bash
xdg-open medit-site/medit.html
```

</details>

---

## ✨ Features

### Both Versions

| Feature | Description |
|---------|-------------|
| 📋 View metadata | Full structured report across 6 categories |
| ✏️ Edit any field | Browse by category, pick by number or click |
| 📍 GPS editor | Decimal degrees in → DMS stored automatically |
| 📅 Date & Time | Set all dates at once, or shift by ±N hours |
| 📱 Fake device | Spoof as iPhone 15 Pro, Galaxy S24, Pixel 8 Pro, or custom |
| 💀 Wipe metadata | Strip all EXIF from the image in one click |
| 💾 Export report | Save a full `.txt` metadata report |

### CLI Only

| Feature | Description |
|---------|-------------|
| 🔐 Encrypt tag | Store an encrypted secret in a custom EXIF tag (Fernet) |
| 🔓 Decrypt tag | Recover it with your key |
| 🕵️ Hide message | LSB steganography — hide text invisibly in pixel data |
| 🔍 Extract message | Read a hidden message back out of any image |
| 🔁 Clone EXIF | Copy all metadata from one image onto another |

<img width="498" height="261" alt="Screenshot 2026-03-20 124518" src="https://github.com/user-attachments/assets/6579c8cf-143d-4684-925f-d1a9023ae443" />

---

## 📂 Editable Categories

| Category | Notable Fields |
|----------|---------------|
| 📷 Camera Information | Make, Model, Lens Model, Serial Number, Software |
| 🎞️ Image Settings | ISO, F-Number, Exposure, Focal Length, Flash, White Balance |
| 🌍 GPS Data | Latitude, Longitude, Altitude, Speed, Direction |
| 🕐 Date & Time | Original, Digitized, Modify Date, Sub Sec fields |
| ✍️ Author & Copyright | Artist, Copyright, Image Description, User Comment, Maker Note |
| 🖼️ Image Properties | Width, Height, Color Space, Resolution, Exif Version, Compression |

---

## 📖 Field Format Reference

| Label | What to type | Example |
|-------|-------------|---------|
| `text` | Plain string | `Apple` |
| `int` | Whole number | `100` |
| `ratio` | Fraction or decimal | `1/100` or `2.8` |
| `deg` | Decimal degrees | `44.4268` |
| `ref` | Single letter | `N` `S` `E` `W` |
| `datetime` | Date/time string or `now` | `2026:03:20 14:30:00` |

---

## 🗃️ Project Structure

```
File Data Editor/
├── README.md                 ← you are here
├── LICENSE
├── medit-site/
│   ├── medit.html            ← web app — just open this
│   └── README.md
└── medit-cmd/
    ├── medit.py              ← CLI tool
    ├── requirements.txt
    └── README.md
```

---

## 🔒 Privacy

| Version | Data handling |
|---------|--------------|
| 🌐 Web | Runs 100% in your browser. Nothing is uploaded or sent anywhere. |
| 💻 CLI | Runs entirely on your local machine. No network calls. |

---

## 📝 Notes

- Original files are **never modified** until you explicitly save or download
- CLI auto-backs up `filename_backup.jpg` before overwriting an existing output
- Web version tested on Chrome, Edge, Firefox, Safari
- Runs on Windows, macOS, Linux

---

<div align="center">

*File Data Editor — made by scoofyx*

</div>
