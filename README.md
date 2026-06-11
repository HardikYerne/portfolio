# Hardik Yerne — Portfolio

Personal AI/ML portfolio built with vanilla HTML/CSS/JS.

## 🚀 Deployment — GitHub Pages + Custom Domain

### Step 1: Create GitHub Repository

```bash
git init
git add .
git commit -m "Initial portfolio deploy"
git branch -M main
git remote add origin https://github.com/HardikYerne/HardikYerne.github.io.git
git push -u origin main
```

> **Tip:** For GitHub Pages user site, name your repo exactly `HardikYerne.github.io`
> This gives you the URL: `https://hardikyerne.github.io` automatically.

---

### Step 2: Enable GitHub Pages

1. Go to your repo on GitHub
2. Click **Settings** → **Pages** (left sidebar)
3. Under **Source**, select **GitHub Actions**
4. Save — the workflow in `.github/workflows/deploy.yml` will auto-deploy on every push

---

### Step 3: Set Up Custom Domain

#### A. Edit the CNAME file
Open `CNAME` in this repo and replace `www.yourdomain.com` with your actual domain:
```
www.hardikyerne.com
```
Commit and push this change.

#### B. Configure DNS at your domain registrar
Log in to where you bought your domain (GoDaddy, Namecheap, Porkbun, etc.) and add these DNS records:

**For apex domain (hardikyerne.com):**
| Type | Name | Value |
|------|------|-------|
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |

**For www subdomain (www.hardikyerne.com):**
| Type | Name | Value |
|------|------|-------|
| CNAME | www | HardikYerne.github.io |

#### C. Enable HTTPS in GitHub Pages settings
1. Go to **Settings → Pages**
2. Under **Custom domain**, type your domain and click Save
3. Wait ~10 minutes for DNS to propagate
4. Check **Enforce HTTPS** ✅

---

### Step 4: Verify Deployment

After pushing to `main`, go to:
- **Actions tab** in your repo → watch the deploy workflow run
- Your site will be live at `https://www.yourdomain.com` within minutes

---

## 📁 Project Structure

```
portfolio/
├── index.html                  # Main portfolio page
├── CNAME                       # Custom domain config
├── README.md                   # This file
└── .github/
    └── workflows/
        └── deploy.yml          # Auto-deploy GitHub Action
```

## 🔧 Making Updates

Any time you push to `main`, the GitHub Action automatically redeploys:

```bash
# Make your changes to index.html, then:
git add .
git commit -m "Update portfolio"
git push
```

The site will update within ~60 seconds.

---

## 💡 Tips

- **Free HTTPS** is included automatically via GitHub Pages + Let's Encrypt
- **No build step needed** — pure HTML/CSS/JS, zero dependencies
- DNS propagation can take up to 48 hours (usually much faster)
- Test DNS propagation at: https://dnschecker.org
