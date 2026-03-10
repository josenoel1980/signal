# SIGNAL — AI Intelligence for PMs

> A Claude-powered daily briefing app for product managers. PWA, works on iOS, iPadOS, Android, and desktop.

![SIGNAL App](icons/icon-192.png)

---

## ✦ Features

- **AI-generated briefings** — Claude writes 16 fresh articles every 12 hours
- **12-hour cache** — open the app multiple times, only 1 API call per 12h (~$0.09/day)
- **PIN-protected key** — enter your Anthropic key once, unlock with 4-digit PIN every time after
- **Save for later** — bookmark articles, synced across devices
- **PWA** — installs as a native app on iOS, iPadOS, and Android
- **Bottom tab navigation** — Today feed + Saved reading list

---

## 🚀 Deploy to GitHub Pages

### 1. Fork or clone this repo

```bash
git clone https://github.com/YOUR_USERNAME/signal-app.git
cd signal-app
```

### 2. Push to GitHub

```bash
git add .
git commit -m "Deploy SIGNAL"
git push origin main
```

### 3. Enable GitHub Pages

1. Go to your repo on GitHub
2. **Settings → Pages**
3. Under **Source**, select **GitHub Actions**
4. The workflow runs automatically — your app will be live at:

```
https://YOUR_USERNAME.github.io/signal-app
```

> The first deploy takes ~1 minute. After that, every push auto-deploys.

---

## 📱 Install as an App

### iPhone / iPad (Safari)
1. Open your GitHub Pages URL in **Safari**
2. Tap the **Share** button (box with arrow)
3. Tap **Add to Home Screen**
4. Tap **Add** — SIGNAL appears as an app icon

### Android (Chrome)
1. Open your GitHub Pages URL in **Chrome**
2. Tap the **⋮ menu → Add to Home Screen** 
3. Or tap the **Install** banner that appears automatically

### Desktop (Chrome / Edge)
1. Click the **install icon** in the address bar (➕)

---

## 🔑 First-time setup

1. Open SIGNAL
2. Enter your **Anthropic API key** (`sk-ant-api03-...`)
   - Get one at [console.anthropic.com](https://console.anthropic.com)
3. **Set a 4-digit PIN** — your key is encrypted and saved locally
4. Next time: just enter your PIN, no key needed

> Your API key never leaves your device. It's XOR-encrypted with your PIN and stored in `localStorage`.

---

## 💰 Cost

| Usage | Cost |
|-------|------|
| Daily (1 briefing/day) | ~$0.09/day · ~$2.70/month |
| Open app 10× a day | Still ~$0.09/day (12h cache) |
| Heavy use with manual refreshes | ~$5–10/month |

Model: `claude-sonnet-4-5` — $3/M input, $15/M output tokens.

---

## 🔒 Privacy

- API key stored encrypted in `localStorage` (your device only)
- Saved articles optionally synced via Claude's artifact storage API
- No tracking, no analytics, no ads
- GitHub Pages serves only static files — no server-side code

---

## 🗂 File Structure

```
signal-app/
├── index.html              # The entire app (single file)
├── manifest.json           # PWA manifest
├── sw.js                   # Service worker (offline support)
├── icons/
│   ├── icon-192.png        # Android / PWA icon
│   ├── icon-512.png        # Android splash / PWA
│   ├── apple-touch-icon.png       # iPhone (180px)
│   └── apple-touch-icon-167.png   # iPad (167px)
└── .github/
    └── workflows/
        └── deploy.yml      # Auto-deploy to GitHub Pages
```

---

## 🛠 Local development

Just open `index.html` in any browser. No build step, no dependencies.

For service worker to work locally, serve with a local server:

```bash
npx serve .
# or
python3 -m http.server 8080
```

---

## Making it private

If you want the app only accessible to you:

1. Keep the GitHub repo **private**
2. Deploy to **Netlify** instead (supports private repos, free tier):
   - [netlify.com](https://netlify.com) → New site → Connect GitHub → select repo → Deploy

---

Built with [Claude](https://anthropic.com) · [Anthropic API](https://docs.anthropic.com)
