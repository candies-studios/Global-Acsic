# GitHub Setup & Deployment Guide

This guide will help you push the Global ACSIC Conference website to GitHub and deploy it using GitHub Pages.

## Prerequisites

- GitHub account (create at https://github.com if you don't have one)
- Git installed on your computer (https://git-scm.com)
- Basic command line/terminal knowledge

## Step 1: Create a GitHub Repository

1. **Log in to GitHub** at https://github.com
2. **Click the "+" icon** in the top-right corner
3. **Select "New repository"**
4. **Enter repository details:**
   - Repository name: `global-acsic-website-2026`
   - Description: "Official website for Global Symposium & 38th ACSIC Conference 2026"
   - Public (so it's accessible online)
   - DO NOT initialize with README, .gitignore, or license (we already have these)
5. **Click "Create repository"**

## Step 2: Prepare Your Local Repository

1. **Open terminal/command prompt**
2. **Navigate to the global-acsic-website-final folder:**
   ```bash
   cd path/to/global-acsic-website-final
   ```

3. **Initialize git (if not already initialized):**
   ```bash
   git init
   ```

4. **Add all files:**
   ```bash
   git add .
   ```

5. **Create initial commit:**
   ```bash
   git commit -m "Initial commit: Conference website for ACSIC 2026"
   ```

## Step 3: Connect to GitHub

1. **Add the remote repository:**
   Replace `yourusername` with your GitHub username.
   ```bash
   git remote add origin https://github.com/yourusername/global-acsic-website-2026.git
   ```

2. **Verify the remote:**
   ```bash
   git remote -v
   ```
   You should see two lines with the origin URL.

3. **Rename branch to main (if needed):**
   ```bash
   git branch -M main
   ```

4. **Push to GitHub:**
   ```bash
   git push -u origin main
   ```
   
   When prompted, enter your GitHub username and personal access token (or password).

## Step 4: Enable GitHub Pages

1. **Go to your repository on GitHub**
2. **Click "Settings"** (top menu)
3. **Scroll down to "Pages"** section on the left sidebar
4. **Under "Build and deployment":**
   - Source: Select "Deploy from a branch"
   - Branch: Select "main"
   - Folder: Select "/ (root)"
5. **Click "Save"**

Your site will be available at:
```
https://yourusername.github.io/global-acsic-website-2026/
```

## Step 5: Verify Deployment

1. **Wait 1-2 minutes** for GitHub to build and deploy
2. **Check the "Deployments" tab** on your repository
3. **Visit your GitHub Pages URL** to verify the site is live

## Updating Content

To update the website after deployment:

1. **Make changes** to HTML, CSS, or JavaScript files
2. **Stage and commit:**
   ```bash
   git add .
   git commit -m "Update: Description of changes"
   ```
3. **Push to GitHub:**
   ```bash
   git push origin main
   ```

Changes will be live within **1-2 minutes**.

## Authentication Methods

### Using Personal Access Token (Recommended)

1. Go to GitHub Settings > Developer settings > Personal access tokens
2. Create a new token with `repo` scope
3. Use the token instead of your password when prompted

### Using SSH (Advanced)

1. Generate SSH key pair
2. Add public key to GitHub SSH settings
3. Use `git@github.com:yourusername/repo.git` as remote URL

## Common Issues & Solutions

### "Permission denied (publickey)" or Authentication Error

**Solution:**
- Use HTTPS instead of SSH: `git remote set-url origin https://github.com/yourusername/repo.git`
- Use a personal access token instead of password
- Check that your GitHub credentials are correctly configured

### Site not showing up at GitHub Pages URL

**Solution:**
1. Verify "Pages" settings are configured correctly
2. Check that files are pushed to the `main` branch
3. Wait 2-5 minutes for deployment
4. Check the "Deployments" tab for any errors

### "fatal: remote origin already exists"

**Solution:**
```bash
git remote remove origin
git remote add origin https://github.com/yourusername/global-acsic-website-2026.git
```

### Changes not appearing on the website

**Solution:**
1. Verify you pushed the changes: `git push origin main`
2. Clear your browser cache (Ctrl+Shift+Delete)
3. Try in an incognito/private browser window
4. Wait 1-2 minutes for deployment

## Useful Git Commands

```bash
# Check current status
git status

# View commit history
git log --oneline

# Undo last commit (keeps files)
git reset --soft HEAD~1

# Revert a specific file
git checkout HEAD -- filename.html

# View remote URL
git remote -v

# Update remote URL
git remote set-url origin https://new-url.git
```

## Domain Configuration (Optional)

To use a custom domain instead of GitHub Pages URL:

1. **Buy a domain** from any registrar (GoDaddy, Namecheap, etc.)
2. **Add DNS records** pointing to GitHub Pages:
   - Type A: @ -> 185.199.108.153
   - Type A: @ -> 185.199.109.153
   - Type A: @ -> 185.199.110.153
   - Type A: @ -> 185.199.111.153
   - Type AAAA: @ -> 2606:50c0:8000::153
   - Type AAAA: @ -> 2606:50c0:8001::153
   - Type AAAA: @ -> 2606:50c0:8002::153
   - Type AAAA: @ -> 2606:50c0:8003::153
3. **Add custom domain** in GitHub Pages settings
4. **Wait 15-30 minutes** for DNS propagation

## Support

For GitHub-related questions:
- GitHub Documentation: https://docs.github.com
- GitHub Pages Guide: https://pages.github.com
- Contact GitHub Support: https://support.github.com

---

**Congratulations!** Your conference website is now live on GitHub Pages! 🚀
