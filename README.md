# DEVEN-CUTTING-S-MEDIA-LIBRARY---INSTALLER-v23.7_Full_install_Ubuntu_24.04
DEVEN CUTTING'S MEDIA LIBRARY - INSTALLER v23.8 --- DEVEN CUTTING'S MEDIA LIBRARY - INSTALLER v23.7_Full_install_Ubuntu_24.04

<div align="center">

# 📚 Deven Cutting's Media Library

### A Self-Hosted Personal Media Library Server

**Version 23.7** | Blue/Cyan Edition | MIT Licensed

[![Ubuntu](https://img.shields.io/badge/Ubuntu-24.04%20LTS-E95420?style=for-the-badge&logo=ubuntu&logoColor=white)](https://ubuntu.com/)
[![Python](https://img.shields.io/badge/Python-3.12-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)
[![WSL](https://img.shields.io/badge/WSL-Compatible-0078D4?style=for-the-badge&logo=windows-terminal&logoColor=white)](https://docs.microsoft.com/en-us/windows/wsl/)
[![Maintained](https://img.shields.io/badge/Maintained-Yes-brightgreen?style=for-the-badge)](https://github.com/devencutting)

**Personal Edition - Created & Maintained by Deven Cutting**

*Curating Knowledge, Media & Creative Works*

[Features](#-features) • [Quick Start](#-quick-start) • [Installation](#-installation) • [Usage](#-usage) • [Customization](#-customization) • [License](#-license)

</div>

---

## 🌊 About

**Deven Cutting's Media Library** is a self-hosted, local web server that organizes and streams your personal collection of videos, images, and audio content. Built as a personal project, this lightweight system transforms any folder of media files into a beautiful, browsable web library with a custom blue/cyan theme.

No cloud. No subscriptions. No tracking. Just your media, on your machine, accessible from any device on your network.

**Personal Edition Features:**
- Custom blue/cyan color scheme
- Personalized branding
- MIT licensed for free use
- Auto-refreshing library
- Smart cache management
- Personal collection focus

---

## ✨ Features

### 🎬 **Media Support**
- **Videos** - MP4, MOV, WebM, AVI, MKV with HTML5 player
- **Images** - PNG, JPG, JPEG, GIF, WebP with click-to-zoom lightbox
- **Audio** - MP3, WAV, OGG, M4A, FLAC with playback controls
- **Unlimited files** - No 50-file limit like Python's built-in server
- **Multiple simultaneous playback** - Watch videos and listen to audio at the same time

### 🚀 **Easy To Use**
- **One-command install** - Just paste and run
- **One-command start** - Type `ark` to launch
- **Auto-refresh** - Library updates automatically on start
- **Smart updates** - Type `ark-add` to refresh file list
- **One-command stop** - Type `ark-stop` to shut down
- **Auto browser open** - Library opens in your default browser

### 🎨 **Beautiful Design (Blue/Cyan Edition)**
- Custom blue/cyan color scheme
- Modern Segoe UI font
- Smooth animations and hover effects
- Cyan glow effects on cards
- Responsive grid layout (mobile, tablet, desktop)
- Clean filename display (removes timestamps and hashes)
- Professional footer with licensing info

### 🛠️ **Technical Highlights**
- Pure Python - no external dependencies
- Works on **Ubuntu 24.04 LTS** and **WSL**
- Smart Windows user detection
- Preserves existing media files during install
- **Cache-busting** built-in (no stale data!)
- Configurable paths (stored in `~/.ark_install_dir`)
- Cross-platform compatible
- Auto-creates missing `index.html`

---

## 🚀 Quick Start

### Prerequisites
- Ubuntu 24.04 LTS (native or WSL on Windows 10/11)
- Python 3.12+ (installed automatically)
- ~100MB free disk space (plus your media)

### Installation (3 minutes)

**One command installs everything:**

```bash
bash -c "$(curl -fsSL https://raw.githubusercontent.com/devencutting/ark-library/main/install.sh)"


Or paste the installer manually:

Download install.sh from this repository
Open Ubuntu terminal
Paste the contents and press Enter
Follow the prompts (pick your Windows user if using WSL)
Wait for "INSTALLATION COMPLETE!"
First Run
bash

Collapse
Save
Copy
1
2
3
4
5
# Start the library
ark

# Your browser opens automatically to http://localhost:9000
# Press Ctrl+Shift+R in browser to refresh file list
📦 Installation
What Gets Installed

Collapse
Save
Copy
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
~/ark-library/                  # Main library folder (or Windows path)
├── index.html                  # Web interface (Blue/Cyan Edition)
├── manifest.json               # Auto-generated file list
├── generate-manifest.py        # File scanner
├── videos/                     # Your video files
├── images/                     # Your image files
└── audio/                      # Your audio files

~/.local/bin/
├── ark                         # Start server command
├── ark-add                     # Refresh library command
└── ark-stop                    # Stop server command

~/.ark_install_dir              # Saved library path
~/.ark_is_wsl                   # WSL detection flag
System Requirements
COMPONENT
MINIMUM
RECOMMENDED
OS
Ubuntu 24.04 LTS
Ubuntu 24.04 LTS
Python
3.12
3.12+
RAM
512MB
1GB+
Disk
100MB + media
10GB+
Browser
Any modern
Chrome, Firefox, Edge


Windows + WSL Setup
This is the recommended setup for Windows users:

Install WSL:
powershell

Collapse
Save
Copy
1
2
3
# Open PowerShell as Administrator
wsl --install
# Restart your computer
Install Ubuntu 24.04 from Microsoft Store
Open Ubuntu terminal and run the installer
Your media files can live in either:
Windows (e.g., C:\Users\You\Downloads\ark-library\)
Ubuntu (e.g., ~/ark-library/) ← Faster, recommended
💻 Usage
Daily Commands
COMMAND
WHAT IT DOES
ark
Starts the library server AND auto-refreshes file list
ark-add
Scans folders and updates the file list
ark-stop
Stops the running server
Ctrl+C
Emergency stop (in the terminal)


Adding New Media
Method 1: File Manager

Open your file manager
Navigate to your library's videos/ (or images/ or audio/)
Copy/paste or drag your files in
Run: ark (auto-refreshes!)
Hard refresh browser (Ctrl+Shift+R)
Method 2: Terminal

bash

Collapse
Save
Copy
1
2
3
4
5
6
7
# Copy a video (example)
cp ~/Downloads/new-video.mp4 ~/ark-library/videos/

# Update and restart (ark does this automatically now!)
ark

# That's it!
Accessing From Other Devices
The library is accessible from any device on your local network:

Find your computer's IP address:
bash

Collapse
Save
Copy
1
2
hostname -I
# Example output: 192.168.1.100
On another device (phone, tablet, another computer), open:

Collapse
Save
Copy
1
http://192.168.1.100:9000
🎨 Customization
Change The Theme Colors
The Blue/Cyan theme uses these colors in index.html:

css

Collapse
Save
Copy
1
2
3
4
5
6
7
8
9
10
11
/* Deep navy background */
background: linear-gradient(135deg, #0a1929 0%, #1e3a5f 50%, #2c5282 100%);

/* Cyan accents */
color: #00d4ff;

/* Gold highlights */
color: #ffd700;

/* Light text */
color: #e8f0f7;
Popular alternatives:

Green/Forest: #0a2919, #1e5f3a, #2c8252, #00ff88
Purple/Mystic: #1a0a29, #3a1e5f, #522c82, #d400ff
Red/Crimson: #290a0a, #5f1e1e, #822c2c, #ff0040
Personalize The Branding
Edit index.html and find:

html

Collapse
Save
Copy

Preview
1
2
3
4
<h1>📚 Deven Cutting's Media Library</h1>
<div class="subtitle">Personal Collection</div>
<div class="name">— Deven Cutting —</div>
<div class="tagline">Curating Knowledge, Media & Creative Works</div>
Change to your own name and tagline!

Change The Port
Edit ~/.local/bin/ark:

bash

Collapse
Save
Copy
1
2
3
4
5
# Find this line:
python3 -m http.server 9000

# Change to:
python3 -m http.server 8080  # or any port
Add More File Types
Edit generate-manifest.py:

python

Collapse

Run
Save
Copy
1
2
videos = scan_folder('videos', ('.mp4', '.mov', '.webm', '.avi', '.mkv', '.flv'))
# Add .flv, .m4v, .webm, etc.
🏗️ Architecture
How It Works

Collapse
Save
Copy
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
25
┌─────────────────────────────────────────┐
│  Your Media Files                       │
│  (videos, images, audio)                │
└──────────────┬──────────────────────────┘
               │
               ▼
┌─────────────────────────────────────────┐
│  generate-manifest.py                   │
│  Scans folders → manifest.json          │
└──────────────┬──────────────────────────┘
               │
               ▼
┌─────────────────────────────────────────┐
│  Python HTTP Server (port 9000)         │
│  Serves files + index.html              │
│  (Cache-busting: ?v=Date.now())         │
└──────────────┬──────────────────────────┘
               │
               ▼
┌─────────────────────────────────────────┐
│  Your Browser                           │
│  http://localhost:9000                  │
│  Blue/Cyan themed interface             │
│  Plays videos, shows images, audio      │
└─────────────────────────────────────────┘
Cache-Busting Magic
The HTML uses fetch('manifest.json?v=' + Date.now()) to force the browser to always get fresh data. No more seeing stale file counts!

Why No Database?
Simplicity - Just files and a JSON manifest
Portability - Copy the folder anywhere
Backup-friendly - Standard file structure
Version control - Works with Git
Fast - No database overhead
🐛 Troubleshooting
"Command 'ark' not found"
Close your terminal and open a new one. The PATH update from the installer needs a fresh terminal session.

Browser shows wrong numbers (stale data)
Press Ctrl + Shift + R to hard refresh. The cache-busting should handle this automatically, but sometimes browsers cache aggressively.

"Address already in use"
Port 9000 is taken. Either:

Stop the other service: pkill -f "http.server 9000"
Change the port (see Customization above)
Videos won't play
Check file format: file ~/ark-library/videos/problem-video.mp4
Try converting: ffmpeg -i input.mov output.mp4
Check file permissions: chmod 644 ~/ark-library/videos/*.mp4
Slow performance
Reduce number of files per folder
Use Ubuntu home (~/ark-library/) instead of Windows path for faster access
Close other browser tabs
Clear browser cache (Ctrl+Shift+Delete)
"manifest.json not found"
bash

Collapse
Save
Copy
1
2
# Regenerate the manifest
ark-add
index.html missing
The ark-add command will tell you if it's missing. Just run ark and it will be auto-created if needed.

📚 Version History
v23.7 (Current) - Blue/Cyan Personal Edition, Deven Cutting branding
v20.1 - Auto-refresh, cache-busting, smart updates
v10.777a - Multi-file playback, lightbox, all features working
v7.x - Safe installer series with proper escaping
v6.0 - Hardcoded paths, user selection
v5.0 - User selection menu
v1.0 - Initial release
🤝 Contributing
This is a personal project by Deven Cutting, but contributions and forks are welcome!

Fork the repository
Create your feature branch (git checkout -b feature/YourFeature)
Commit your changes (git commit -m 'Add YourFeature')
Push to the branch (git push origin feature/YourFeature)
Open a Pull Request
Ideas for contributions:

New color themes
Additional media format support
Performance improvements
Documentation improvements
Translations
📜 License
This project is licensed under the MIT License - see the LICENSE file for details.


Collapse

Run
Save
Copy
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
MIT License

Copyright © 2026 Deven Cutting

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
Free to use, modify, and distribute. Make it your own! 🎨

🙏 Credits
Created & Maintained by: Deven Cutting
Powered by: Python 🐍 and the open-source community
Theme: Custom Blue/Cyan design
Built with: ❤️ and lots of ☕
📞 Contact & Support
GitHub: @devencutting
Issues: GitHub Issues
🌊 Personal Note
This project represents a journey from "can you make an HTML page?" to a fully functional, personalized media library system. Every bug fixed, every feature added, every installer iteration brought us closer to this v23.7 release.

Built for personal use, shared with the world. 🌍

<div align="center">
Made with 💙 by Deven Cutting

📚 Curating Knowledge, Media & Creative Works 📚

Version 23.7 - Blue/Cyan Edition

</div> ```
🎨 What's New In This README:
✅ Matches your Blue/Cyan theme - colors and style
✅ Deven Cutting branding throughout
✅ MIT License section - with full license text
✅ Version history - shows the journey from v1.0 to v23.7
✅ Personal note - mentions the journey
✅ Professional badges - maintained, MIT, etc.
✅ Customization section - how to change colors to other themes










