# Quick Deployment Guide - Cloudflare Pages

## 🚀 Quick Start (5 minutes)

### Step 1: Push to GitHub

```bash
git add .
git commit -m "Ready for Cloudflare Pages"
git push origin main
```

### Step 2: Deploy on Cloudflare

1. **Go to Cloudflare Dashboard:**
   - Visit: https://dash.cloudflare.com/
   - Navigate to **Workers & Pages** → **Pages**

2. **Connect to Git:**
   - Click **Create application** → **Pages** → **Connect to Git**
   - Authorize GitHub and select your repository

3. **Configure Build Settings:**

   **IMPORTANT - Use these exact settings:**

   | Setting | Value |
   |---------|-------|
   | **Project name** | `youtube-playlist-extractor` (or your choice) |
   | **Production branch** | `main` |
   | **Framework preset** | None |
   | **Build command** | **(leave completely empty)** |
   | **Build output directory** | `/` |

4. **Deploy:**
   - Click **Save and Deploy**
   - Wait 1-2 minutes for deployment to complete

### Step 3: Done!

Your site will be live at: `https://youtube-playlist-extractor.pages.dev`

## 🔄 Automatic Deployments

Once connected, every `git push` to `main` automatically triggers a new deployment. No commands needed!

```bash
# Make changes to your code
git add .
git commit -m "Update feature"
git push origin main
# 🎉 Cloudflare automatically deploys the changes!
```

## 🌐 Custom Domain (Optional)

1. In Cloudflare Pages dashboard, go to your project
2. Click **Custom domains** → **Set up a custom domain**
3. Add your domain and update DNS records as instructed

## 📝 Project Structure

```
YoutubePlaylistExtractor/
├── index.html          # Main application file
├── _headers            # Security headers configuration
├── package.json        # Project metadata
├── .gitignore          # Git ignore rules
├── README.md           # Full documentation
├── DEPLOYMENT.md       # This file
├── LICENSE             # MIT License
└── images/             # Screenshots
```

**Note:** No build configuration files (`wrangler.toml`, `webpack.config.js`, etc.) are needed - this is a pure static HTML site!

## ❓ Troubleshooting

**Issue:** Build fails with configuration errors
- **Solution:** Make sure the build command field is **completely empty** (not even a space)
- **Solution:** Verify build output directory is exactly `/` (forward slash)

**Issue:** 404 error on deployment
- **Solution:** Ensure `index.html` exists in the root directory of your repository

**Issue:** CORS errors when fetching playlists
- **Solution:** The `_headers` file must be in the root directory and will be deployed automatically
- **Solution:** Check that `_headers` file has proper CORS configuration for API domains

**Issue:** "Configuration file does not support 'site'" error
- **Solution:** Delete any `wrangler.toml` file if it exists - it's not needed for Pages deployments

## 📚 More Information

See [README.md](README.md) for complete documentation and features.

