# Click2HAR - One-click HAR capture tool for network analysis

Capture HAR files instantly—without opening DevTools, clicking through menus, or renaming files manually.  
**Click2HAR** records all network activity from the current tab and downloads a clean, complete HAR file named after the **page title**.

No setup. No confusion. Just click → capture → Download.

![Click2HAR](images/meta.png)

---

## 🚀 Key Features

### 🔘 One-Click Recording

Open the popup → click **Record & Download** → the extension captures all network requests and saves the HAR.  
Status automatically updates as:

- Initializing
- Recording
- Processing
- Downloading
- Done

### 📄 Automatic Clean Filenames

HAR files are saved as:


The extension sanitizes forbidden characters and guarantees proper `.har` extension.

### 🔍 Full HAR Export

Includes:

- Request URLs
- Methods
- Status codes
- Request headers
- Response headers
- Response bodies (when accessible)
- Timing information

All compiled into a valid **HAR 1.2** structure.

### 📝 Optional Console Log

If console messages are captured, they are saved as:


### 🔐 Privacy-Focused

- No data leaves your device
- No external servers
- Everything happens within Chrome’s debugger API
- All files are generated and stored locally

### 🌐 Works on Every Site

HAR capture works on any website you have access to.

### ⚡ MV3 Compatible

Runs using a Manifest V3 service worker for maximum stability and performance.

---

## 🧩 How to Use

1. Open any webpage you want to capture.
2. Click the **Click2HAR** icon in your Chrome toolbar.
3. In the popup, click **Record & Download**.
4. Wait a few seconds while:
   - The debugger attaches
   - The page reloads (if needed)
   - Network requests are captured
   - The HAR is generated
5. Your HAR file is automatically downloaded as:


If console logs were captured, you'll also get:



---

## 🛡 Permissions Explained

| Permission | Why It’s Needed                                        |
| ---------- | ------------------------------------------------------ |
| debugger   | Capture network traffic via Chrome's Debugger Protocol |
| downloads  | Save `.har` and `.txt` files locally                   |
| tabs       | Identify the active tab and fetch its title            |
| activeTab  | Temporary access to the tab being captured             |

---

## 📦 Output Files

### HAR File


### Console Log (optional)


---

## 🛠 Troubleshooting

### HAR not downloading?

You may have closed or switched the tab while recording. Re-run the capture.

### File downloaded as `download.json`?

The extension overrides Chrome’s filename behavior to force correct naming.

### Missing response bodies?

Some sites block body extraction for security reasons.

---

## 🛠️ Developer Notes

- `popup.html` — The UI for the button and status
- `popup.js` — Handles interactions and status updates
- `background.js` — Captures network activity, builds HAR, exports files
- `manifest.json` — MV3 service worker configuration & permissions

---

## 👨‍💻 Author

Made with ❤️ by [Jatin Gupta](https://github.com/jatin009v)