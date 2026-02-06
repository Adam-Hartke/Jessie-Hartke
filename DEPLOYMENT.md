# GitHub Pages Deployment Guide

## Step-by-Step Setup

### 1. Create GitHub Repository

1. Go to https://github.com/new
2. Repository name: `jessie-hartke-portfolio` (or your choice)
3. Description: "Professional portfolio website"
4. Select "Public"
5. **Do NOT** initialize with README, .gitignore, or license (we already have these)
6. Click "Create repository"

### 2. Upload Your Files

In your terminal, navigate to the folder containing the website files, then:

```bash
# Initialize git repository
git init

# Add all files
git add .

# Create first commit
git commit -m "Initial portfolio website"

# Add your GitHub repository as remote
# Replace YOUR-USERNAME and YOUR-REPO-NAME with your actual values
git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPO-NAME.git

# Push to GitHub
git branch -M main
git push -u origin main
```

### 3. Enable GitHub Pages

1. Go to your repository on GitHub
2. Click **Settings** (top right)
3. In the left sidebar, click **Pages**
4. Under "Build and deployment":
   - Source: Select **"Deploy from a branch"**
   - Branch: Select **"main"** and **"/ (root)"**
   - Click **Save**

### 4. Wait for Deployment

- GitHub will automatically deploy your site
- This usually takes 1-2 minutes
- You'll see a green checkmark when it's ready
- Your site will be available at: `https://YOUR-USERNAME.github.io/YOUR-REPO-NAME/`

### 5. Optional: Custom Domain

If you want to use a custom domain (e.g., jessiehartke.com):

1. In the Pages settings, add your custom domain
2. In your domain registrar's DNS settings, add these records:
   - Type: **A Record**
   - Host: **@**
   - Value: 
     ```
     185.199.108.153
     185.199.109.153
     185.199.110.153
     185.199.111.153
     ```
   - Type: **CNAME Record**
   - Host: **www**
   - Value: **YOUR-USERNAME.github.io**

3. Wait 24-48 hours for DNS propagation
4. Enable HTTPS in GitHub Pages settings (recommended)

## Making Updates

After the initial setup, to update the website:

```bash
# Make your changes to the files
# Then:

git add .
git commit -m "Description of changes"
git push
```

GitHub will automatically redeploy the site within 1-2 minutes.

## Troubleshooting

**Site not loading?**
- Check that GitHub Pages is enabled in Settings > Pages
- Ensure the branch is set to "main" and folder to "/ (root)"
- Wait a few minutes - deployments aren't instant

**Links not working?**
- If using a repository name (not root), you may need to update paths
- Check that all file paths are relative (start with `/` or `./`)

**Custom domain not working?**
- DNS changes can take 24-48 hours
- Use https://dnschecker.org to verify propagation
- Ensure CNAME file is in your repository root

## Support

- GitHub Pages documentation: https://docs.github.com/pages
- If you get stuck, the error messages in the Actions tab are usually helpful
