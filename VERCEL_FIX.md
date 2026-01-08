# ✅ Fixed Vercel Deployment Guide

## What Was Fixed

Your `vercel.json` had configuration issues. I've updated it to use the correct format.

## Deployment Steps

### 1. **Commit Your Changes**
```bash
git add .
git commit -m "Fix Vercel deployment configuration"
git push origin main
```

### 2. **Deploy to Vercel**

#### Option A: Via Vercel CLI (Recommended)
```bash
npm install -g vercel
vercel --prod
```

#### Option B: Via Web Dashboard
1. Go to [vercel.com](https://vercel.com)
2. Click "Add New" → "Project"
3. Import your GitHub repository
4. Vercel will auto-detect your project
5. Click "Deploy"

#### Option C: Reconnect Existing Project
If already connected but failing:
1. Go to [vercel.com/dashboard](https://vercel.com/dashboard)
2. Select your project
3. Go to Settings → Git
4. Disconnect and reconnect GitHub repo
5. Re-deploy

### 3. **Verify Deployment**
Once deployed:
- Your site will be at: `https://your-project.vercel.app`
- Check "Deployments" tab for status
- Click "Visit" to view live site

## Configuration Details

**Updated `vercel.json`:**
- ✅ Build command: `npm run build`
- ✅ Output directory: `_site`
- ✅ Node version: 18.17.0
- ✅ Installation: `npm install`

## If Still Failing

### Check Vercel Logs
1. Go to [vercel.com/dashboard](https://vercel.com/dashboard)
2. Select your project
3. Click latest deployment
4. Check "Logs" tab for errors

### Common Issues & Fixes

**Issue: "npm install failed"**
- Solution: Clear cache in project settings

**Issue: "Build timed out"**
- Solution: Check for infinite loops in config

**Issue: "Output not found"**
- Solution: Verify `_site` directory is being created

### Manual Test Build
```bash
# Test locally
npm install
npm run build
ls _site/  # Should show: index.html, posts/, css/, feed.xml, sitemap.xml
```

All files should be present.

## Troubleshooting

### Step 1: Verify Local Build
```bash
npm run build
```
Should complete without errors.

### Step 2: Check package.json
Verify scripts section:
```json
"scripts": {
  "build": "eleventy",
  "start": "eleventy --serve"
}
```

### Step 3: Check Vercel.json
Should look like:
```json
{
  "buildCommand": "npm run build",
  "outputDirectory": "_site",
  "installCommand": "npm install",
  "nodeVersion": "18.17.0"
}
```

### Step 4: Retry Deployment
```bash
git add .
git commit -m "Deployment fixes"
git push origin main
# Then re-trigger in Vercel dashboard or use CLI
```

## Alternative: Use Netlify Instead

If Vercel continues having issues, Netlify is more reliable for static sites:

```bash
npm install -g netlify-cli
netlify deploy --prod
```

Or connect via web at [netlify.com](https://netlify.com)

---

**Your site should now deploy successfully! 🚀**

Let me know if you get any other errors!
