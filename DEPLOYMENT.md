# Quick Deployment Guide - Cloudflare Pages

## 🚀 Quick Start (5 minutes)

### Via Cloudflare Dashboard (Easiest)

1. **Commit and Push to GitHub:**
   ```bash
   git add .
   git commit -m "Ready for Cloudflare Pages"
   git push origin main
   ```

2. **Deploy on Cloudflare:**
   - Visit: https://dash.cloudflare.com/
   - Go to **Workers & Pages** → **Create Application** → **Pages** → **Connect to Git**
   - Authorize GitHub and select your repository
   - Configure:
     - **Project name:** `youtube-playlist-extractor`
     - **Production branch:** `main`
     - **Build command:** (leave empty)
     - **Build output directory:** `/`
   - Click **Save and Deploy**

3. **Done!** Your site will be live at `https://youtube-playlist-extractor.pages.dev`

## 🔧 Via Wrangler CLI (Advanced)

1. **Install Wrangler:**
   ```bash
   npm install
   ```

2. **Login:**
   ```bash
   npx wrangler login
   ```

3. **Deploy:**
   ```bash
   npm run deploy
   ```

## 🌐 Custom Domain (Optional)

1. In Cloudflare Pages dashboard, go to your project
2. Click **Custom domains** → **Set up a custom domain**
3. Add your domain and update DNS records as instructed

## 🔄 Auto-Deploy

Once connected, every `git push` to `main` automatically deploys to production!

## 📝 Project Structure

```
YoutubePlaylistExtractor/
├── index.html          # Main application file
├── _headers            # Security headers configuration
├── wrangler.toml       # Cloudflare configuration
├── package.json        # npm scripts
├── .gitignore          # Git ignore rules
├── README.md           # Full documentation
├── DEPLOYMENT.md       # This file
├── LICENSE             # MIT License
└── images/             # Screenshots
```

## ❓ Troubleshooting

**Issue:** Build fails
- **Solution:** Check that build command is empty and output directory is `/`

**Issue:** 404 on deployment
- **Solution:** Ensure `index.html` exists in the root directory

**Issue:** CORS errors
- **Solution:** The `_headers` file should be deployed automatically

## 📚 More Information

See [README.md](README.md) for complete documentation and features.

