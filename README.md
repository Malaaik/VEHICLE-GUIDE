# Vehicle Request Guide

A single self-contained page (`index.html`) — no build step, no backend. Open it in VS Code and run it locally, then deploy it anywhere as a static site.

## 1. Open in VS Code

1. Unzip/copy this folder somewhere on your machine.
2. In VS Code: **File → Open Folder...** → select this folder.

## 2. Run it locally (pick one)

**Option A — VS Code "Live Server" extension (easiest)**
1. Install the extension: open the Extensions panel (`Ctrl+Shift+X`), search **"Live Server"** (by Ritwick Dey), click Install.
2. Right-click `index.html` in the file explorer → **"Open with Live Server"**.
3. It opens automatically at something like `http://127.0.0.1:5500` — any edit you save auto-refreshes the page.

**Option B — Node.js, from the terminal**
Requires [Node.js](https://nodejs.org) installed.
```bash
npm start
```
This runs `npx serve .` and prints a local URL (usually `http://localhost:5500` or `http://localhost:3000`). Open it in your browser.

**Option C — Python (if you have it, no install needed)**
```bash
python3 -m http.server 5500
```
Then open `http://localhost:5500` in your browser.

## 3. Editing

Just edit `index.html` directly (open it in VS Code's editor) and save — if you're using Live Server, the browser refreshes automatically. All the page's HTML, CSS and JS live in this one file.

## 4. Publish it (make it a real public link)

Once you're happy with it locally, push the same `index.html` to any static host. The URL stays the same every time you redeploy — only the content changes.

**GitHub Pages (free)**
1. Create a new GitHub repo.
2. Add this folder's contents to it and push.
3. Repo → **Settings → Pages** → set source to the branch/root → save.
4. You'll get a link like `https://yourname.github.io/reponame/`.

**Netlify / Vercel / Cloudflare Pages (free, fastest)**
1. Go to the site (netlify.com, vercel.com, or pages.cloudflare.com), sign up.
2. Drag-and-drop this folder onto their deploy page (or connect your GitHub repo).
3. You get an instant live link, and a custom domain can be attached later.

## Notes

- `package.json` only exists to give you a one-command local server (`npm start`); it is **not** needed for deployment — static hosts just serve `index.html` directly.
- PDF generation uses [jsPDF](https://github.com/parallax/jsPDF) loaded from a CDN (`cdnjs.cloudflare.com`), so an internet connection is needed for that feature even when running locally.
