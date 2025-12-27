# Quick Start Guide - 5 Minutes to Deploy

## 1️⃣ Get Web3Forms Key (2 minutes)
- Go to: https://web3forms.com
- Sign up and get your API key
- Edit `index.html` line 956: replace `YOUR_ACCESS_KEY_HERE` with your key

## 2️⃣ Create GitHub Repo (1 minute)
- Go to: https://github.com/new
- Name: `anywithai`
- Make it **Public**
- Don't initialize with README
- Click "Create"

## 3️⃣ Push Your Code (1 minute)
Run these commands (replace YOUR_USERNAME):

```bash
cd "c:\Users\prasa\OneDrive\Documents\anywithai"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/anywithai.git
git push -u origin main
```

## 4️⃣ Enable GitHub Pages (1 minute)
- Go to: Repository → Settings → Pages
- Source: Branch **main**, Folder **/ (root)**
- Save
- Your site is now live at: `https://YOUR_USERNAME.github.io/anywithai/`

## 5️⃣ Add Custom Domain (Optional)
- Edit `CNAME` file: add your GoDaddy domain
- In GoDaddy DNS, add A records pointing to GitHub Pages IPs
- Full details in `DEPLOYMENT_GUIDE.md`

---

**Done!** Your website is live. See `DEPLOYMENT_GUIDE.md` for detailed instructions.
