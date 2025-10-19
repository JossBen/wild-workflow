# How to Add This Project to GitHub

Follow these steps to add the wild-workflow project to GitHub.

## Prerequisites

1. **GitHub Account**: Create one at [github.com](https://github.com) if you don't have one
2. **Git Installed**: Check if git is installed:
   ```bash
   git --version
   ```
   If not installed, download from [git-scm.com](https://git-scm.com)

---

## Step 1: Initialize Git Repository

Open Terminal and navigate to your project:

```bash
cd /Users/benjoss/Desktop/code/wild-workflow
```

Initialize git repository:

```bash
git init
```

You should see: `Initialized empty Git repository in /Users/benjoss/Desktop/code/wild-workflow/.git/`

---

## Step 2: Add Files to Git

Add all files to git:

```bash
git add .
```

Check what will be committed:

```bash
git status
```

You should see files in green (ready to commit).

---

## Step 3: Create Initial Commit

Commit the files with a message:

```bash
git commit -m "Initial commit - Wilderness workflow specification tool"
```

You should see a summary of files added.

---

## Step 4: Create GitHub Repository

### Option A: Via GitHub Website (Easiest)

1. Go to [github.com](https://github.com)
2. Click the **+** icon in top right → **New repository**
3. Fill in details:
   - **Repository name**: `wild-workflow`
   - **Description**: `Interactive workflow specification tool for film production`
   - **Visibility**: Choose **Public** or **Private**
   - **DO NOT** check "Initialize with README" (we already have one)
   - **DO NOT** add .gitignore or license
4. Click **Create repository**

### Option B: Via GitHub CLI (Advanced)

If you have GitHub CLI installed:

```bash
gh repo create wild-workflow --public --description "Interactive workflow specification tool for film production"
```

---

## Step 5: Connect Local Repository to GitHub

After creating the repo on GitHub, you'll see instructions. Use these commands:

**Replace `YOUR-USERNAME` with your actual GitHub username:**

```bash
git remote add origin https://github.com/YOUR-USERNAME/wild-workflow.git
```

Verify the remote was added:

```bash
git remote -v
```

You should see the GitHub URL.

---

## Step 6: Push to GitHub

Push your code to GitHub:

```bash
git branch -M main
git push -u origin main
```

You might be asked for your GitHub username and password/token.

**Success!** Your code is now on GitHub.

---

## Step 7: Enable GitHub Pages (Optional)

To make the HTML accessible via a public URL:

1. Go to your repository on GitHub
2. Click **Settings** (top menu)
3. Scroll down to **Pages** (left sidebar)
4. Under **Source**:
   - Branch: Select `main`
   - Folder: Select `/ (root)`
5. Click **Save**

Wait 1-2 minutes, then your site will be live at:
```
https://YOUR-USERNAME.github.io/wild-workflow/refs/wilderness_workflow_spec.html
```

---

## Complete Terminal Commands (All-in-One)

Here's the complete sequence if you want to copy/paste:

```bash
# Navigate to project
cd /Users/benjoss/Desktop/code/wild-workflow

# Initialize git
git init

# Add all files
git add .

# Commit
git commit -m "Initial commit - Wilderness workflow specification tool"

# Add remote (REPLACE YOUR-USERNAME!)
git remote add origin https://github.com/YOUR-USERNAME/wild-workflow.git

# Push to GitHub
git branch -M main
git push -u origin main
```

---

## Making Future Updates

After making changes to your files:

```bash
# Check what changed
git status

# Add all changes
git add .

# Commit with descriptive message
git commit -m "Updated camera specifications"

# Push to GitHub
git push
```

---

## Common Issues & Solutions

### Issue 1: "Permission denied (publickey)"

**Solution:** Set up SSH key or use HTTPS with personal access token.

For HTTPS with token:
1. Go to GitHub → Settings → Developer settings → Personal access tokens
2. Generate new token with `repo` permissions
3. Use token as password when pushing

### Issue 2: "Remote already exists"

**Solution:** Remove and re-add the remote:
```bash
git remote remove origin
git remote add origin https://github.com/YOUR-USERNAME/wild-workflow.git
```

### Issue 3: "Failed to push some refs"

**Solution:** Pull first, then push:
```bash
git pull origin main --allow-unrelated-histories
git push -u origin main
```

### Issue 4: Git asks for username/password repeatedly

**Solution:** Configure git credentials:
```bash
git config --global credential.helper osxkeychain
```

---

## Verifying Your Repository

After pushing, verify on GitHub:

1. Go to `https://github.com/YOUR-USERNAME/wild-workflow`
2. You should see all your files
3. README.md will display automatically
4. Click on `refs/wilderness_workflow_spec.html` to view the file

---

## Sharing Your Project

### Share the GitHub Repository:
```
https://github.com/YOUR-USERNAME/wild-workflow
```

### Share the Live Application (after enabling Pages):
```
https://YOUR-USERNAME.github.io/wild-workflow/refs/wilderness_workflow_spec.html
```

### Share Settings Files:
Team members can export/import JSON settings files for collaboration.

---

## Next Steps

1. **Update README.md**: Add your GitHub Pages URL to the README
2. **Create Releases**: Tag important versions
3. **Enable Issues**: Let team members report bugs
4. **Add Collaborators**: Settings → Collaborators → Add people

---

## Git Workflow Diagram

```
Local Changes
     ↓
git add .
     ↓
git commit -m "message"
     ↓
git push
     ↓
GitHub Repository
     ↓
GitHub Pages (if enabled)
     ↓
Live Website
```

---

## Useful Git Commands

```bash
# View commit history
git log --oneline

# Undo last commit (keep changes)
git reset --soft HEAD~1

# See what changed in a file
git diff filename

# Create a new branch
git checkout -b feature-name

# Switch branches
git checkout main

# Merge branch into main
git checkout main
git merge feature-name

# View remote repositories
git remote -v

# Pull latest changes
git pull origin main

# Clone repository to another location
git clone https://github.com/YOUR-USERNAME/wild-workflow.git
```

---

## Best Practices

1. **Commit Often**: Make small, logical commits
2. **Write Good Messages**: Describe what changed and why
3. **Pull Before Push**: Always pull latest changes before pushing
4. **Use Branches**: For experimental features
5. **Export Settings**: Before major changes, export your workflow settings
6. **Tag Releases**: Mark important milestones with version tags

---

## Support

If you encounter issues:
1. Check [GitHub Docs](https://docs.github.com)
2. Search [Stack Overflow](https://stackoverflow.com/questions/tagged/git)
3. Contact your development team

---

**Congratulations!** Your project is now on GitHub! 🎉
