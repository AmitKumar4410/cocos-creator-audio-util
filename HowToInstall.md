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