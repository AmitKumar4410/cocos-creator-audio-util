# cocos-creator-audio-util

A lightweight, persistent Audio Manager for Cocos Creator (3.x). This utility handles music, sound effects, volume control, muting, and automatic caching of audio clips. It also persists user settings (volume/mute state) to `localStorage` automatically so player preferences are saved between sessions.

## Features

- **Unified Management:** Control Music and SFX separately.
- **Automatic Caching:** Audio clips are loaded once via `resources.load` and cached for performance.
- **Persistence:** Saves volume levels and mute states to `localStorage` automatically.
- **Global Mute:** Mute everything instantly (useful for pausing or ads).
- **Type Safe:** Fully typed with TypeScript.

# 📥 Installation
# Install via Download (Recommended)
1.  **Get the Library:**
    Download the **`audio-util-[version].tgz`** file provided by the developer.

2.  **Add to Project:**
    Place the `.tgz` file inside your project folder (e.g., create a `libs` folder).
    
    ```text
    MyGameProject/
    ├── assets/
    ├── libs/
    │   └── audio-util-[version].tgz  <-- Put file here
    └── package.json
    ```

3.  **Install:**
    Run this command in your terminal:

    ```bash
    npm install ./libs/cc-audio-util-[version].tgz
    ```
# Install via GIT (Recommended)
This method allows you to use standard imports without manual file copying or path configuration.

1.  Go to the **[Releases](../../releases)** page.
2.  Right-click the **`audio-util-[version].tgz`** file and choose **"Copy Link Address"**.
3.  Open your project terminal and run:

```bash
# Replace the URL below with the link you just copied
npm install https://github.com/AmitKumar4410/cocos-creator-audio-util/releases/download/[version]/cc-audio-util-[version].tgz
```
