# Wilderness Workflow Specification - Deployment Guide

## Overview
This HTML application can be deployed in multiple ways with persistent data storage. All user changes are automatically saved to browser localStorage and can be exported/imported as JSON files.

---

## Deployment Options

### Option 1: Static File Hosting (Simplest)

**Best for:** Quick deployment, small teams, single browser access

**How it works:**
- Open the HTML file directly in a browser
- Settings automatically save to browser's localStorage
- Data persists between sessions on the same browser
- Export/Import buttons allow sharing configurations

**Steps:**
1. Double-click `wilderness_workflow_spec.html` to open in browser
2. Or use a local web server:
   ```bash
   # Python 3
   python -m http.server 8000

   # Or using Node.js
   npx serve .
   ```
3. Access at: `http://localhost:8000/refs/wilderness_workflow_spec.html`

**Pros:**
- Zero setup required
- Works offline
- No server needed

**Cons:**
- Data only persists in one browser
- Need to manually share exports between users

---

### Option 2: GitHub Pages (Free Hosting)

**Best for:** Team collaboration, public/private access, version control

**Steps:**

1. **Create a GitHub repository:**
   ```bash
   cd /Users/benjoss/Desktop/code/wild-workflow
   git init
   git add .
   git commit -m "Initial commit - Wilderness workflow spec"
   ```

2. **Push to GitHub:**
   ```bash
   git remote add origin https://github.com/YOUR-USERNAME/wild-workflow.git
   git branch -M main
   git push -u origin main
   ```

3. **Enable GitHub Pages:**
   - Go to repository Settings → Pages
   - Source: Deploy from branch `main`
   - Folder: `/ (root)`
   - Click Save

4. **Access your site:**
   - URL: `https://YOUR-USERNAME.github.io/wild-workflow/refs/wilderness_workflow_spec.html`
   - Share this URL with your team

**Pros:**
- Free hosting
- HTTPS enabled
- Version control included
- Team can access from anywhere

**Cons:**
- Public by default (unless using private repo with GitHub Pro)
- Data saved per-browser (use export/import to share)

---

### Option 3: Netlify (Free with Custom Domain)

**Best for:** Professional deployment, custom domains, continuous deployment

**Steps:**

1. **Sign up at [netlify.com](https://netlify.com)**

2. **Deploy via drag-and-drop:**
   - Drag the entire `wild-workflow` folder to Netlify
   - Or connect your GitHub repo for auto-deployment

3. **Configure:**
   - Settings → Domain Management → Add custom domain
   - Deploy settings → Auto-publish on push

4. **Access:**
   - Free subdomain: `your-app.netlify.app`
   - Or custom domain: `workflow.yourproduction.com`

**Pros:**
- Free SSL/HTTPS
- Custom domains
- Instant deploys
- CDN included

**Cons:**
- Data saved per-browser (use export/import)

---

### Option 4: Self-Hosted with Docker + Database (Enterprise)

**Best for:** Full control, multi-user persistence, centralized data

**Requirements:**
- Docker installed
- Basic server knowledge

**Create `Dockerfile`:**
```dockerfile
FROM nginx:alpine
COPY refs/wilderness_workflow_spec.html /usr/share/nginx/html/index.html
EXPOSE 80
```

**Deploy:**
```bash
cd /Users/benjoss/Desktop/code/wild-workflow

# Build Docker image
docker build -t wilderness-workflow .

# Run container
docker run -d -p 8080:80 --name workflow wilderness-workflow

# Access at http://localhost:8080
```

**For Multi-User Database Persistence (Advanced):**

You would need to:
1. Set up a backend (Node.js/Python/PHP)
2. Database (PostgreSQL/MySQL/MongoDB)
3. API endpoints to save/load configurations
4. User authentication

This requires significant development. Contact me if you need this setup.

---

### Option 5: Cloud Storage Services

**Best for:** Quick team collaboration without setup

**Using Google Drive/Dropbox:**

1. Save `wilderness_workflow_spec.html` to shared folder
2. Team members download and open locally
3. Use Export/Import buttons to share configurations
4. Store exported JSON files in shared folder

**Pros:**
- Easy for non-technical users
- Version history (if using Drive/Dropbox)
- No hosting needed

**Cons:**
- Manual file management
- Not real-time collaboration

---

## Data Persistence Features

### Automatic Browser Storage
- All dropdown changes automatically save to localStorage
- Data persists when you close/reopen the browser
- Specific to each browser and device

### Export Settings
1. Click "Export Settings" button
2. Downloads `wilderness_workflow_settings.json`
3. Share this file with team members
4. Store in version control or shared drive

### Import Settings
1. Click "Import Settings" button
2. Select a `.json` settings file
3. All configurations load instantly
4. Auto-saves to localStorage

### Settings File Example:
```json
{
  "project-aspect": "2.39",
  "project-framerate": "24",
  "project-resolution": "4k-uhd",
  "camA-format": "x-ocn-st",
  "camA-sensor": "8k",
  "camA-framerate": "24"
}
```

---

## Recommended Setup for Production Team

### For Small Teams (1-5 people):
1. Host on **GitHub Pages** (free)
2. Each user exports their settings at end of day
3. Share settings file via Slack/email
4. Morning: import latest settings

### For Medium Teams (5-20 people):
1. Host on **Netlify** with custom domain
2. Create shared Dropbox folder for settings exports
3. Designate one person to maintain "master" configuration
4. Others import master settings as needed

### For Large Productions (20+ people):
1. Use **Docker deployment** on company server
2. Consider building database backend for multi-user
3. Integrate with production management tools
4. Contact for custom enterprise solution

---

## Quick Start Commands

### Local Testing:
```bash
cd /Users/benjoss/Desktop/code/wild-workflow
open refs/wilderness_workflow_spec.html
```

### Python Server:
```bash
cd /Users/benjoss/Desktop/code/wild-workflow
python3 -m http.server 8000
# Open: http://localhost:8000/refs/wilderness_workflow_spec.html
```

### Deploy to GitHub Pages:
```bash
git init
git add .
git commit -m "Initial workflow spec"
git remote add origin YOUR-REPO-URL
git push -u origin main
# Enable Pages in GitHub settings
```

### Docker Deployment:
```bash
docker build -t wilderness-workflow .
docker run -d -p 8080:80 wilderness-workflow
# Access: http://localhost:8080
```

---

## Troubleshooting

### Settings not saving?
- Check browser console (F12) for errors
- Ensure localStorage is enabled
- Try different browser
- Use Export/Import as backup

### Lost settings?
- Check browser localStorage: Open DevTools → Application → Local Storage
- Look for `wildernessWorkflowSettings` key
- Restore from exported JSON file

### Share with team?
1. Click "Export Settings"
2. Share JSON file via email/Slack/Drive
3. Team clicks "Import Settings" and selects file

---

## Security Notes

- **LocalStorage data is NOT encrypted**
- Don't store passwords or sensitive info in settings
- For public GitHub Pages, anyone with URL can access
- Use private repos or Netlify password protection for confidential projects

---

## Support & Customization

Need help with:
- Custom backend development
- Multi-user database integration
- SSO/authentication
- Enterprise deployment
- Custom features

Contact your development team or the original creator.

---

## Backup Best Practices

1. **Daily Exports:** Export settings at end of each shoot day
2. **Version Control:** Commit exports to git with date stamps
3. **Cloud Backup:** Store in Google Drive/Dropbox
4. **Team Share:** Keep master config in shared location
5. **Documentation:** Note any custom camera additions

Example naming: `workflow_settings_2025-10-19_SD01.json`

---

## Updates & Maintenance

### To update the HTML file:
1. Make edits to `wilderness_workflow_spec.html`
2. Test locally
3. Export current settings first (backup)
4. Replace file on server
5. Import settings back

### Version control workflow:
```bash
git add refs/wilderness_workflow_spec.html
git commit -m "Updated camera specs for Ronin 4D"
git push
# GitHub Pages auto-deploys
```

---

**Last Updated:** 2025-10-19
**Version:** 1.0
