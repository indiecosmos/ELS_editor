import zipfile
from pathlib import Path

# Create the base directory
repo_root = Path("/mnt/data/ELS_Lightbar_Editor")
repo_root.mkdir(exist_ok=True)

# Copy els_editor.py from uploaded file
source_script = Path("/mnt/data/els_editor (2).py")
target_script = repo_root / "els_editor.py"
target_script.write_text(source_script.read_text())

# Create README.md
readme_text = """
# 🚨 ELS Lightbar Pattern Editor

A standalone emergency lighting pattern editor inspired by ERLC (Emergency Response Liberty County). Create, visualize, and save custom lightbar animations for front and rear lights with color-coded rows and customizable flash speeds.

---

## 🎮 Features

- 🔴 **Grid-based Pattern Editor** — Design frame-by-frame lightbar sequences using intuitive front and rear grids.
- 🌈 **Multi-Color Support** — Use up to 8 colors (Red, Blue, White, Amber, Green, Purple, Cyan, Off).
- 🟪 **Animated Playback** — A purple bar moves top-to-bottom, playing each row of the lightbar pattern in real time.
- ⏱ **Flashes Per Minute (FPM)** — Adjust the animation speed live with numeric input.
- 💾 **Save & Load** — Export and import patterns as `.json` files.
- ✅ **Cross-platform Ready** — Designed with portability in mind (works on macOS with PyInstaller).

---

## 📸 Screenshots

*Coming soon!* (You can include screenshots or GIFs of the editor and playback animation here.)

---

## 🛠 How to Use

### 🖥 Run on macOS (or any Python-capable system)

1. Install Python and dependencies:
    ```bash
    pip install pygame
    ```

2. Clone the repository and run:
    ```bash
    python els_editor.py
    ```

---

## 🍏 Build a macOS App

1. Install PyInstaller:
    ```bash
    pip install pyinstaller
    ```

2. Build the standalone app:
    ```bash
    pyinstaller --windowed --onefile els_editor.py
    ```

3. Optionally, package as a `.dmg`:
    ```bash
    brew install create-dmg
    create-dmg dist/els_editor
    ```

---

## 💡 Controls

- **Left Click** a grid cell to color it with the selected color.
- **Color Selector** on the left lets you choose which light color to paint with.
- **Buttons** at the top:
  - `Clear All` — resets all frames
  - `Insert Row` / `Delete Row` — add/remove frames
  - `Play` — animates pattern row by row with the purple bar
  - `Save` — exports pattern to JSON
  - `Load` — imports saved pattern
- **FPM Box** — enter a number to change playback speed

---

## 🗂 File Structure
