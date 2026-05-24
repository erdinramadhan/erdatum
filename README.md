# erdatum.com landing page

Single-file landing page for Erdatum BI consulting practice. Built with vanilla HTML/CSS + Google Fonts (Fraunces, Manrope, JetBrains Mono).

## What's in this file

- `index.html` — full landing page, single file, no build step
- Includes: Hero, Services (6 cards), Case Study (linked to bi.erdatum.com), About, Contact

## What you need to edit before deploy

Open `index.html` and find these placeholders:

1. **Line ~487**: Replace `YOUR-USERNAME` in LinkedIn URL
2. **Line ~488**: Replace `YOUR-USERNAME` in GitHub URL
3. **Bio / services copy**: read through and adjust to your voice
4. **Status indicator** (Hero): "Open for engagements · Q2 2026" — change quarter if needed

## Deploy to Cloudflare Pages (via GitHub)

### Step 1: Create GitHub repo

1. Go to https://github.com/new
2. Name: `erdatum-landing` (or any name)
3. Set to **Private** (recommended) or Public
4. Click "Create repository"

### Step 2: Push file to repo

Option A — via GitHub web UI (no terminal):
1. Click "uploading an existing file"
2. Drag `index.html` to upload area
3. Commit message: "Initial landing page"
4. Click "Commit changes"

Option B — via terminal:
```bash
cd /path/to/this/folder
git init
git add index.html README.md
git commit -m "Initial landing page"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/erdatum-landing.git
git push -u origin main
```

### Step 3: Connect to Cloudflare Pages

1. Open https://dash.cloudflare.com → Workers & Pages → Pages
2. Click "Create application" → "Pages" → "Connect to Git"
3. Authorize Cloudflare to access your GitHub
4. Select repo `erdatum-landing`
5. Production branch: `main`
6. Build settings: leave EMPTY (no framework, static HTML)
   - Framework preset: `None`
   - Build command: (empty)
   - Build output directory: `/` (root)
7. Click "Save and Deploy"

Cloudflare will deploy in ~1 minute. You'll get a URL like `erdatum-landing-abc.pages.dev`.

### Step 4: Connect erdatum.com domain

1. In Cloudflare Pages → your project → Custom domains
2. Click "Set up a custom domain"
3. Enter `erdatum.com` (apex)
4. Cloudflare auto-creates DNS records
5. Wait ~1 minute for SSL
6. Optional: also add `www.erdatum.com` as alias

Done. erdatum.com now serves the landing page.

### Updates

Every `git push` to `main` = auto-redeploy on Cloudflare Pages. No manual upload needed.
