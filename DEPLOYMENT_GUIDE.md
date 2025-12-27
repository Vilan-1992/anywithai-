# Deployment Guide for ANJANAYAPPA Website

## Step 1: Get Web3Forms API Key (For Contact Form)

1. Visit [https://web3forms.com](https://web3forms.com)
2. Sign up with your email: **pvprasanna1992@gmail.com**
3. Create a new form and get your access key
4. Open `index.html` and find line 956
5. Replace `YOUR_ACCESS_KEY_HERE` with your actual Web3Forms access key

## Step 2: Create GitHub Repository and Deploy

### Option A: Using GitHub Website (Recommended)

1. Go to [https://github.com/new](https://github.com/new)
2. Repository name: `anywithai` (or any name you prefer)
3. Make it **Public** (required for free GitHub Pages)
4. **Don't** initialize with README (we already have files)
5. Click "Create repository"

6. After creating, GitHub will show you commands. Run these in your terminal:

```bash
cd "c:\Users\prasa\OneDrive\Documents\anywithai"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/anywithai.git
git push -u origin main
```

Replace `YOUR_USERNAME` with your GitHub username.

### Option B: Install GitHub CLI (Alternative)

If you prefer, install GitHub CLI from [https://cli.github.com](https://cli.github.com) and run:

```bash
cd "c:\Users\prasa\OneDrive\Documents\anywithai"
gh auth login
gh repo create anywithai --public --source=. --remote=origin --push
```

## Step 3: Enable GitHub Pages

1. Go to your repository on GitHub
2. Click **Settings** → **Pages** (in left sidebar)
3. Under "Source", select:
   - Branch: **main**
   - Folder: **/ (root)**
4. Click **Save**
5. Wait 1-2 minutes, then your site will be live at:
   `https://YOUR_USERNAME.github.io/anywithai/`

## Step 4: Configure Custom Domain (GoDaddy)

### A. Update CNAME file
1. Open the `CNAME` file in your project
2. Replace `yourdomain.com` with your actual GoDaddy domain (e.g., `anjanayappa.com`)
3. Commit and push:
```bash
git add CNAME
git commit -m "Add custom domain"
git push
```

### B. Configure GoDaddy DNS

1. Log in to [GoDaddy DNS Management](https://dcc.godaddy.com/manage/dns)
2. Select your domain
3. Add/Edit these DNS records:

**For apex domain (anjanayappa.com):**
- Type: **A**, Name: **@**, Value: **185.199.108.153**, TTL: 600
- Type: **A**, Name: **@**, Value: **185.199.109.153**, TTL: 600
- Type: **A**, Name: **@**, Value: **185.199.110.153**, TTL: 600
- Type: **A**, Name: **@**, Value: **185.199.111.153**, TTL: 600

**For www subdomain (www.anjanayappa.com):**
- Type: **CNAME**, Name: **www**, Value: **YOUR_USERNAME.github.io**, TTL: 600

4. Save all changes

### C. Configure GitHub Pages Custom Domain

1. Go to your GitHub repository → **Settings** → **Pages**
2. Under "Custom domain", enter your domain: `anjanayappa.com`
3. Click **Save**
4. Wait for DNS check to complete (may take up to 24 hours)
5. Once verified, check **Enforce HTTPS**

## Step 5: Verify Deployment

After DNS propagates (15 minutes - 24 hours):

1. Visit your domain: `https://anjanayappa.com`
2. Test the contact form by submitting an email
3. Check that Web3Forms sends you an email notification

## Troubleshooting

**Site not loading:**
- Wait 24 hours for DNS propagation
- Clear browser cache
- Check GitHub Pages status in repository settings

**Contact form not working:**
- Verify Web3Forms access key is correct
- Check browser console for errors
- Test on [https://web3forms.com](https://web3forms.com)

**Custom domain not working:**
- Verify DNS records are correct
- Use [https://dnschecker.org](https://dnschecker.org) to check propagation
- Ensure CNAME file contains only your domain (no http://)

## Cost Summary

- **GitHub Pages:** FREE ✓
- **Web3Forms:** FREE (250 submissions/month) ✓
- **GoDaddy Domain:** Paid (you already have) ✓
- **SSL Certificate:** FREE (via GitHub Pages) ✓

**Total Monthly Cost: $0** (excluding domain registration)

## Need Help?

- GitHub Pages docs: [https://pages.github.com](https://pages.github.com)
- Web3Forms docs: [https://docs.web3forms.com](https://docs.web3forms.com)
- GoDaddy DNS help: [https://www.godaddy.com/help](https://www.godaddy.com/help)
