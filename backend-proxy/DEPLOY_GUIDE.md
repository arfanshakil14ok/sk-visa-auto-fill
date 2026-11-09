# 🚀 VisaFill AI - Serverless Backend Deployment Guide

Deploy your own 100% free serverless proxy in less than 3 minutes.
Once deployed, **users of your extension will NEVER need to enter any Gemini API Key**!

---

## ⚡ Option 1: Deploy with Cloudflare Workers (Recommended, 100k requests/day FREE)

### Method A: Via Web Browser (Easiest, No Terminal Needed)
1. Go to [dash.cloudflare.com](https://dash.cloudflare.com/) and create a free account (or log in).
2. On the left sidebar, click **Compute (Workers & Pages)** -> **Create application** -> **Create Worker**.
3. Name it `visafill-proxy` and click **Deploy**.
4. Click **Edit code**:
   - Delete all existing code in the editor.
   - Paste the contents of `cloudflare-worker.js`.
   - Click **Save and deploy**.
5. Set your secret Gemini API Key:
   - Go back to your Worker's settings -> **Settings** tab -> **Variables and Secrets**.
   - Click **Add variable** / **Add secret**.
   - Variable name: `GEMINI_API_KEY`
   - Value: `<Your Gemini API Key starting with AIzaSy...>`
   - Click **Encrypt** and **Save**.
6. Done! Copy your worker URL (e.g. `https://visafill-proxy.yourname.workers.dev`).

### Method B: Via Terminal
```bash
cd backend-proxy
npx wrangler login
npx wrangler secret put GEMINI_API_KEY
npx wrangler deploy
```

---

## 🌐 Option 2: Deploy with Vercel (Alternative)

1. Push this folder to a GitHub repository.
2. Go to [vercel.com](https://vercel.com/) and import the repository.
3. In **Environment Variables**, add:
   - `GEMINI_API_KEY` = `<Your Gemini API Key>`
4. Click **Deploy**.
5. Your endpoint will be: `https://your-project.vercel.app/api/extract`.
