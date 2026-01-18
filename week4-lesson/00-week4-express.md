# Week 4 Express: GitHub & Remote Repos
## 15-Minute Quick Start

Get your Git repository in the cloud. Fast version.

---

## Goal

Connect your local Git to GitHub, push your work to the cloud. Skip the deep explanations for now.

**Time commitment:** 15-20 minutes (including token setup)

---

## Part 1: Create GitHub Account (5 minutes)

**If you don't have one:**
1. Go to [github.com](https://github.com)
2. Sign up (use your work email if this is for work)
3. Verify your email
4. Choose free plan

**If you already have one:** Sign in.

---

## Part 2: Create Personal Access Token (5 minutes)

**You need this to push to GitHub:**

1. GitHub → Click your profile picture (top right)
2. Settings
3. Scroll down → Developer settings (bottom left)
4. Personal access tokens → Tokens (classic)
5. Generate new token → Generate new token (classic)
6. Note: "Git CLI access"
7. Expiration: 90 days (or whatever you prefer)
8. Check the box: **repo** (gives full repo access)
9. Scroll down → Generate token
10. **COPY THE TOKEN IMMEDIATELY** - you won't see it again.
11. Save it somewhere safe (password manager, secure notes)

**This token is your password when pushing to GitHub.**

---

## Part 3: Push Existing Project to GitHub (8 minutes)

### Create Repository on GitHub

1. GitHub → Click **+** (top right) → New repository
2. Name: `test-project` (or whatever you want)
3. **Private** (only you can see it)
4. **DON'T** check "Initialize with README"
5. Create repository

**GitHub shows setup instructions. Ignore them - follow these instead:**

---

### Connect Your Local Git to GitHub

**Navigate to your git-test folder from Week 3:**
```bash
cd ~/Desktop/git-test
```

**Connect to GitHub:**
```bash
git remote add origin https://github.com/YOUR-USERNAME/test-project.git
```

Replace `YOUR-USERNAME` with your actual GitHub username.

**Verify connection:**
```bash
git remote -v
```

Should show your GitHub URL.

---

### Push to GitHub

```bash
git push -u origin main
```

**You'll be prompted:**
- Username: Your GitHub username
- Password: **Paste your personal access token** (not your GitHub password!)

**Expected output:**
```
Enumerating objects...
Writing objects: 100%...
To https://github.com/YOUR-USERNAME/test-project.git
 * [new branch]      main -> main
```

**Success!**

---

### Verify on GitHub

1. Refresh your repository page on GitHub
2. You should see your files!
3. Click "commits" to see your commit history

**Your local Git is now in the cloud.**

---

## Part 4: The Daily Workflow (2 minutes)

**From now on, after making local commits:**

```bash
git push
```

**That's it. Uploads your commits to GitHub.**

**To get changes from GitHub:**

```bash
git pull
```

**That's it. Downloads commits from GitHub.**

---

## The New Cycle

```
1. Make changes locally
2. git add .
3. git commit -m "message"
4. git push (sends to GitHub)

When others make changes:
5. git pull (gets their changes)
```

---

## What You're Skipping

The full Week 4 lesson includes:
- Cloning repositories
- Resolving merge conflicts
- Understanding remote vs. local
- Multiple remotes
- Troubleshooting push/pull
- Extended practice

**Come back when you need these.**

---

## When to Return to Full Week 4

Return to comprehensive version if:
- You need to clone someone else's repository
- You encounter a merge conflict
- You're collaborating with teammates
- Token authentication confuses you

**For now, you can push and pull. That's enough.**

---

## Common Issues

### "Authentication failed"

**Problem:** Wrong username or token

**Fix:**
- Verify GitHub username is correct
- Make sure you're using the **token** as password, not your GitHub password
- Generate a new token if needed

---

### "Repository not found"

**Problem:** URL is wrong

**Fix:**
- Check spelling of username and repository name
- Verify repository exists on GitHub
- Make sure URL matches exactly

---

### "Push rejected"

**Problem:** GitHub has commits you don't have

**Fix:**
```bash
git pull
git push
```

---

## AI Prompt for Custom Learning

Ask ChatGPT/Claude/Copilot:

```
I need to connect my local Git repository to GitHub. I have 15 minutes. 
Walk me through: creating a GitHub account, setting up authentication, 
and pushing my first repository. Keep it simple - I'm not a developer.
```

---

## Cheat Sheet

```bash
# One-time setup
git remote add origin URL

# Daily workflow  
git push              # Send commits to GitHub
git pull              # Get commits from GitHub

# Check connection
git remote -v
```

---

## Critical Understanding

**Before moving to Week 5, make sure you can:**
- Create a repository on GitHub
- Push local commits to GitHub
- View your commits on GitHub website
- Pull changes from GitHub

**If those work, you're ready.**

---

## Next Step

Week 5 Express will teach you branches and pull requests (how teams collaborate).

**Time saved: ~45-60 minutes**

**Important:** Save your personal access token somewhere safe. You'll need it every time you push from a new computer.
