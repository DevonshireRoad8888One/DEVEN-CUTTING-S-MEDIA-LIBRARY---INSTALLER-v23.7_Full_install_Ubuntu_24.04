<div align="center">

# 💙 Deven Cutting's Media Library

### A Self-Hosted, Beautiful Media Library Server

**Version 24.4** | Personalized Edition with Delete Buttons

[![Ubuntu](https://img.shields.io/badge/Ubuntu-24.04%20LTS-E95420?style=for-the-badge&logo=ubuntu&logoColor=white)](https://ubuntu.com/)
[![Python](https://img.shields.io/badge/Python-3.12-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](LICENSE)
[![WSL](https://img.shields.io/badge/WSL-Compatible-0078D4?style=for-the-badge&logo=windows-terminal&logoColor=white)](https://docs.microsoft.com/en-us/windows/wsl/)
[![Version](https://img.shields.io/badge/Version-24.4-00d4ff?style=for-the-badge)](https://github.com/YOUR-USERNAME/ark-library/releases)

[Features](#-features) • [Quick Start](#-quick-start) • [Installation](#-installation) • [Usage](#-usage) • [Delete Feature](#-delete-feature) • [Architecture](#-architecture)

</div>

---

## 📖 About

**Deven Cutting's Media Library** is a self-hosted, personalized web server that organizes and streams videos, images, audio messages, and music. Built with a beautiful **blue/cyan** theme, this system transforms any folder of media files into a stunning, browsable web library.

Created by **Deven Cutting** for organizing personal media collections, prophetic teachings, and creative works.

**No cloud. No subscriptions. No tracking.** Just your media, on your machine, with full control and beautiful design.

---

## ✨ Features

### 🎬 **Media Support**
- **Videos** - MP4, MOV, WebM, AVI, MKV with HTML5 player
- **Images** - PNG, JPG, JPEG, GIF, WebP with click-to-zoom lightbox
- **Audio Messages** - MP3, WAV, OGG, M4A, FLAC
- **Music** - Dedicated music section with special gold styling
- **Unlimited files** - No 50-file limit

### 🗑️ **NEW! Delete Feature (v24.4)**
- Delete buttons on **every item**
- Confirmation modal prevents accidents
- Files go to `trash/` folder (recoverable!)
- Manifest auto-regenerates after deletion
- Path traversal protection (security)
- Command: `ark-trash` to view deleted files

### 🚀 **Easy To Use**
- **One-command install** - Just paste and run
- **One-command start** - Type `ark` to launch
- **One-command update** - Type `ark-add` to refresh
- **One-command stop** - Type `ark-stop` to shut down
- **Auto browser open** - Library opens automatically
- **Auto-refresh** - Index updates every time you start

### 🎨 **Beautiful Design (v24.4)**
- **Blue/cyan theme** personalized for Deven
- Dark mode with cyan accents
- Gold highlights for music section
- Red delete buttons for safety
- Responsive grid layout
- Smooth animations and hover effects
- Clean filename display

### 🛠️ **Technical Highlights**
- Pure Python - no external dependencies
- Works on **Ubuntu 24.04 LTS** and **WSL**
- Smart Windows user detection
- Preserves existing files during install
- Configurable paths (stored in `~/.ark_install_dir`)
- Cross-platform compatible
- MIT License - free to use and modify

---

## 🚀 Quick Start

### Prerequisites
- Ubuntu 24.04 LTS (native or WSL on Windows 10/11)
- Python 3.12+ (installed automatically)
- ~100MB free disk space (plus your media)

### Installation (3 minutes)

**One command installs everything:**

```bash
bash -c "$(curl -fsSL https://raw.githubusercontent.com/YOUR-USERNAME/ark-library/main/install.sh)"

Or paste the installer manually:

Download install.sh
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
# Start the library
ark

# Your browser opens automatically to http://localhost:9000
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
16
~/ark-library/                  # Main library folder
├── index.html                  # Beautiful blue/cyan web interface
├── manifest.json               # Auto-generated file list
├── generate-manifest.py        # File scanner
├── delete-handler.py           # Delete button backend
├── videos/                     # Your video files
├── images/                     # Your image files
├── audio/                      # Your audio messages
├── music/                      # Your music files
└── trash/                      # Recoverable deleted files

~/.local/bin/
├── ark                         # Start server command
├── ark-add                     # Refresh library command
├── ark-stop                    # Stop server command
└── ark-trash                   # View deleted files
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
Starts library, refreshes index, opens browser
ark-add
Updates file list without starting server
ark-stop
Stops the running server
ark-trash
Shows deleted files in trash folder
Ctrl+C
Emergency stop (in terminal)


The 4 Folders
Your library organizes media into 4 folders:

FOLDER
PURPOSE
EXAMPLE
videos/
Video files
Sermons, teachings, movies
images/
Image files
Infographics, posters, photos
audio/
Audio messages
Voice recordings, teachings
music/
Music files
Songs, worship music


Adding New Media
Method 1: File Manager

Open file manager
Navigate to ~/ark-library/videos/ (or other folders)
Copy/paste your files
Run: ark (it auto-refreshes!)
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
# Copy a video
cp ~/Downloads/new-video.mp4 ~/ark-library/videos/

# Update the library (auto-refreshes!)
ark
Deleting Files (v24.4 NEW!)
Click the 🗑️ button on any item card
Confirmation appears: "Move 'song.mp3' to trash?"
Click "Delete" → File moves to trash/
Item disappears from your view
Count updates automatically
Restoring deleted files:

bash

Collapse
Save
Copy
1
2
3
4
5
# View trash
ark-trash

# Restore a file
mv ~/ark-library/trash/1234567890_song.mp3 ~/ark-library/music/
Accessing From Other Devices
The library is accessible from any device on your local network:

Find your computer's IP:
bash

Collapse
Save
Copy
1
2
hostname -I
# Example: 192.168.1.100
On another device, open:

Collapse
Save
Copy
1
http://192.168.1.100:9000
🗑️ Delete Feature (NEW in v24.4)
How It Works
Click 🗑️ button → Confirmation modal appears
Confirm → File moves to trash/ folder (NOT permanently deleted!)
Manifest regenerates automatically
Stats update instantly
Safety Features
✅ Confirmation required - No accidental deletes
✅ Trash folder - Files are recoverable
✅ Path traversal protection - Can't delete system files
✅ Folder validation - Only allowed folders
✅ Audit trail - Trash shows when files were deleted

Recovering Files
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
8
# See what's in trash
ark-trash

# Files are named: timestamp_originalname
# Example: 1694537234_my-song.mp3

# Restore manually
mv ~/ark-library/trash/1694537234_my-song.mp3 ~/ark-library/music/
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
26
27
28
┌─────────────────────────────────────────┐
│  Your Media Files                       │
│  (videos, images, audio, music)         │
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
│  delete-handler.py (Python Server)      │
│  • Serves files on port 9000            │
│  • Handles /delete requests             │
│  • Moves files to trash/                │
└──────────────┬──────────────────────────┘
               │
               ▼
┌─────────────────────────────────────────┐
│  Your Browser                           │
│  http://localhost:9000                  │
│  • Beautiful blue/cyan theme            │
│  • Delete buttons on every item         │
│  • Click-to-zoom images                 │
│  • Multiple simultaneous playback       │
└─────────────────────────────────────────┘
File Organization

Collapse
Save
Copy
1
2
3
4
5
6
v24.4/
├── 📹 videos/          (Video files)
├── 🖼️  images/          (Image files)
├── 🎤 audio/           (Audio messages)
├── 🎵 music/           (Music files)
└── 🗑️  trash/           (Deleted files - recoverable)
🎨 Customization
Change The Theme Colors
Edit ~/ark-library/index.html and modify the CSS:

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
12
13
14
⌄
⌄
⌄
/* Main background gradient (blue/cyan) */
body {
  background: linear-gradient(135deg, #0a1929, #1e3a5f, #2c5282);
}

/* Accent color (cyan) */
:root {
  --accent: #00d4ff;  /* Try #ff6b6b (red) or #4ecdc4 (teal) */
}

/* Music section gold gradient */
.music-card {
  background: linear-gradient(135deg, rgba(255,215,0,0.05), rgba(0,212,255,0.05));
}
Personalize The Header
In index.html, change:

html

Collapse
Save
Copy

Preview
1
2
3
4
<h1>Deven Cutting's Media Library</h1>
<div class="subtitle">Personal Collection</div>
<div class="name">— Deven Cutting —</div>
<div class="tagline">Curating Knowledge, Media & Creative Works</div>
Replace with your own branding!

Change The Port
Edit the server scripts:

bash

Collapse
Save
Copy
1
2
3
4
# In delete-handler.py and ark command, change:
PORT = 9000
# To:
PORT = 8080  # or any available port
🐛 Troubleshooting
"Command 'ark' not found"
Close your terminal and open a new one. The PATH update from the installer needs a fresh terminal session.

"Address already in use"
Port 9000 is taken. Either:

Stop the other service: sudo lsof -i :9000 then kill <PID>
Change the port (see Customization above)
Delete button doesn't work
Check browser console (F12) for errors
Make sure you hard refreshed: Ctrl+Shift+R
Verify delete-handler.py exists in library folder
Deleted files don't go to trash
Check that the trash folder exists:

bash

Collapse
Save
Copy
1
ls -la ~/ark-library/trash/
If missing, create it:

bash

Collapse
Save
Copy
1
mkdir ~/ark-library/trash
Videos won't play
Check file format: file ~/ark-library/videos/problem-video.mp4
Try converting: ffmpeg -i input.mov output.mp4
Check file permissions: chmod 644 ~/ark-library/videos/*.mp4
Slow performance
Use Ubuntu home (~/ark-library/) instead of Windows path
Close other browser tabs
Clear browser cache (Ctrl+Shift+Delete)
Reduce number of files per folder
"manifest.json not found"
bash

Collapse
Save
Copy
1
2
# Regenerate the manifest
ark-add
🆕 Version History
v24.4 (Current) - Deven Cutting Edition
✅ Delete buttons on every item
✅ Confirmation modal for safety
✅ Trash folder for recovery
✅ ark-trash command
✅ Blue/cyan personalized theme
✅ MIT License
✅ Path traversal protection
v23.8 - Music Addition
✅ Separate music/ folder
✅ Music section with gold styling
✅ Music button in navigation
v23.7 - Personalization
✅ Custom branding for Deven Cutting
✅ Blue/cyan modern design
v20.1 - Smart Updates
✅ Auto-refresh on ark
✅ Cache-busting
✅ Smart ark-add
v10.777a - The Working Version
✅ Multiple simultaneous playback
✅ Fixed all path issues
✅ Fast and stable
🤝 Contributing
This project was built by Deven Cutting for personal use and shared as a blessing to others. Contributions, ideas, and feedback are welcome!

Fork the repository
Create your feature branch (git checkout -b feature/AmazingFeature)
Commit your changes (git commit -m 'Add some AmazingFeature')
Push to the branch (git push origin feature/AmazingFeature)
Open a Pull Request
📜 License
This project is licensed under the MIT License - see the LICENSE file for details.

Copyright © 2026 Deven Cutting. All rights reserved.


Collapse

Run
Save
Copy
1
2
3
4
5
MIT License - Permission is hereby granted, free of charge, to any person 
obtaining a copy of this software and associated documentation files (the 
"Software"), to deal in the Software without restriction, including without 
limitation the rights to use, copy, modify, merge, publish, distribute, 
sublicense, and/or sell copies of the Software...
Free to use, modify, and distribute. Use it well! 💙

🙏 Credits
Created by: Deven Cutting
For: Organizing personal media collections, prophetic teachings, and creative works
Powered by: Python 🐍 and the open-source community
Tested on: Dell 5400, Ubuntu 24.04 LTS, WSL
📞 Support
Issues: GitHub Issues
Email: your-email@example.com
Documentation: Wiki
🌟 Show Your Support
If this project helped you, please:

⭐ Star this repository
🐛 Report bugs
💡 Suggest features
📢 Share with others who might need it
<div align="center">
Made with 💙 for personal media curation

💙 Deven Cutting's Media Library 💙

Curating Knowledge, Media & Creative Works

</div> ```
📋 How To Add This To GitHub:
Option 1: Web Interface
Go to your repo
Click "Add file" → "Create new file"
Name: README.md
Paste everything
Commit
Option 2: Command Line
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
nano README.md
# Paste everything
# Ctrl+O, Enter, Ctrl+X
git add README.md
git commit -m "Add comprehensive README"
git push
✏️ Before Publishing, Replace:
YOUR-USERNAME → Your GitHub username (3-4 places)
your-email@example.com → Your real email
Add LICENSE file (paste the MIT license text)
Optional: Take screenshots and add to screenshots/ folder
🎯 Want Me To Also Create:
📜 LICENSE file (MIT)?
🤝 CONTRIBUTING.md guide?
📸 Screenshots folder structure?
Just say the word! 🕊️✨

This README is professional, comprehensive, and ready to impress anyone who visits your repo! 💙✨


# DEVEN-CUTTING-S-MEDIA-LIBRARY---INSTALLER-v24.4_Full_install_Ubuntu_24.04
DEVEN CUTTING'S MEDIA LIBRARY - INSTALLER v24.4 --- DEVEN CUTTING'S MEDIA LIBRARY - INSTALLER v24.4_Full_install_Ubuntu_24.04

<div align="center">

# 📚 Deven Cutting's Media Library

### A Self-Hosted Personal Media Library Server

**Version 24.4** | Blue/Cyan Edition | MIT Licensed

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










