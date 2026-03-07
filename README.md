# MyBot — Deployment Guide

## What's included
```
mybot/
├── server.js          ← Node.js proxy server (keeps API key secret)
├── package.json       ← Dependencies
├── public/
│   └── index.html     ← Bot frontend
└── README.md
```

---

## Deploy to Render (free, recommended)

1. **Push to GitHub**
   - Create a new repo at github.com
   - Upload this entire `mybot/` folder as the repo root

2. **Create a Render Web Service**
   - Go to https://render.com and sign up (free)
   - Click **New → Web Service**
   - Connect your GitHub repo
   - Settings:
     - **Build Command:** `npm install`
     - **Start Command:** `npm start`
     - **Environment:** Node

3. **Add your API key**
   - In Render dashboard → your service → **Environment**
   - Add variable: `ANTHROPIC_API_KEY` = your key from https://console.anthropic.com

4. **Deploy** — Render builds and gives you a public URL like `https://mybot-xxxx.onrender.com`

---

## Deploy to Railway (alternative)

1. Go to https://railway.app
2. New Project → Deploy from GitHub repo
3. Add env var: `ANTHROPIC_API_KEY`
4. Done — Railway auto-detects Node and deploys

---

## Run locally (for testing)

```bash
cd mybot
npm install
export ANTHROPIC_API_KEY=sk-ant-...   # Mac/Linux
set ANTHROPIC_API_KEY=sk-ant-...      # Windows
npm start
# Open http://localhost:3000
```

---

## Get your Anthropic API key
https://console.anthropic.com/settings/keys
