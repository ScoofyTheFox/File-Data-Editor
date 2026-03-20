# File Data Editor
**by scoofyx** · © 2026

A lightweight EXIF metadata editor — view, edit, spoof, wipe, and export image metadata.
Available as a web app (recommended) and a Python CLI tool.

---

## What is EXIF?

EXIF (Exchangeable Image File Format) is hidden metadata stored inside image files.
It records things like the camera model, GPS location, date taken, lens settings, and more.
Every photo you take with a phone or camera has it — most people never see it.

**File Data Editor** lets you read and change all of it.

---

## Versions

| Version | File | Requirements |
|---------|------|--------------|
| 🌐 Web (recommended) | `medit-site/medit.html` | Any browser |
| 💻 CLI | `medit-cmd/medit.py` | Python 3.8+ |

---

## 🌐 Web Version

Open `medit-site/medit.html` in any browser. No install, no server, no internet needed.

### How to use
1. Drag & drop your image onto the page (or click to browse)
2. Pick a category from the sidebar
3. Click any field and type a new value
4. Hit **Download** to save your edited image

### Supported formats
| Format | Edit & Download |
|--------|----------------|
| JPG / JPEG | ✅ Full support |
| PNG | ⚠️ Edit only — re-downloads original |
| GIF | ⚠️ Edit only — re-downloads original |
| WEBP | ⚠️ Edit only — re-downloads original |

> EXIF embedding on download is JPEG-only (browser limitation). Use JPG for full support.

---

## 💻 CLI Version

### Install
```bash
pip install -r medit-cmd/requirements.txt
```

### Run
```bash
# Drop image.jpg in the same folder, then:
py medit.py

# Or pass a path:
py medit.py "C:\Users\you\Pictures\photo.jpg"
```

### Dependencies
```
Pillow>=10.0.0
piexif>=1.1.3
cryptography>=41.0.0
numpy>=1.24.0
```

---

## Features

### Available in both versions
| Feature | Description |
|---------|-------------|
| 📋 View metadata | Full structured report across 6 categories |
| ✏️ Edit any field | Browse by category and pick fields by number/click |
| 📍 GPS editor | Set coordinates by decimal degrees — auto-converts to DMS |
| 📅 Date & Time | Set all dates at once, or shift by ±N hours for timezone fixes |
| 📱 Fake device | Spoof Make/Model as iPhone 15 Pro, Galaxy S24, Pixel 8 Pro, or custom |
| 💀 Wipe metadata | Remove all EXIF from the image entirely |
| 💾 Export report | Save full metadata report as `.txt` |

### CLI only
| Feature | Description |
|---------|-------------|
| 🔐 Encrypt tag | Store an encrypted secret inside a custom EXIF tag using Fernet |
| 🔓 Decrypt tag | Recover the secret with your key |
| 🕵️ Hide message | LSB steganography — hide text invisibly inside pixel data |
| 🔍 Extract message | Read back a hidden message from any image |
| 🔁 Clone EXIF | Copy all metadata from one image onto another |

---

## Editable Categories

| Category | Fields |
|----------|--------|
| Camera Information | Make, Model, Lens Model, Lens Make, Serial Number, Software |
| Image Settings | ISO, F-Number, Exposure Time, Focal Length, Flash, White Balance, and more |
| GPS Data | Latitude, Longitude, Altitude, Speed, Direction, Date |
| Date & Time | Date/Time Original, Digitized, Modify Date, Sub Sec fields |
| Author & Copyright | Artist, Copyright, Image Description, User Comment, Maker Note |
| Image Properties | Width, Height, Color Space, Resolution, Exif Version, Compression, and more |

---

## Field Format Reference

| Hint | What to type | Example |
|------|-------------|---------|
| `text` | Plain string | `Apple` |
| `int` | Whole number | `100` |
| `ratio` | Fraction or decimal | `1/100` or `2.8` |
| `deg` | Decimal degrees (GPS) | `44.4268` |
| `ref` | Single letter | `N` `S` `E` `W` |
| `datetime` | Date and time or `now` | `2026:03:20 14:30:00` |

---

## Project Structure

```
File Data Editor/
├── medit-site/
│   ├── medit.html        ← web app (open in browser)
│   └── README.md
├── medit-cmd/
│   ├── medit.py          ← CLI tool
│   ├── requirements.txt
│   └── README.md
└── README.md             ← this file
```

---

## Privacy

- **Web version** — everything runs in your browser. No data is sent anywhere.
- **CLI version** — everything runs locally on your machine. No network calls.

---

## Notes

- The original file is never modified until you explicitly save / download
- CLI auto-creates a `_backup.jpg` before overwriting an existing output file
- Works on Windows, macOS, and Linux
- Web version tested on Chrome, Edge, Firefox, and Safari

---

*File Data Editor — made by scoofyx*
