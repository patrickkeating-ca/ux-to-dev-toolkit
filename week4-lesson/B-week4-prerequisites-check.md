# Prerequisites Check - Week 4
## GitHub & Remote Repos

### Before Starting This Lesson

Week 4 connects your local Git repository to GitHub - putting your version control in the cloud. This enables backup, collaboration, and sharing your work.

---

## Week 1-3 Completion Check

You should have already:

- [ ] Completed Week 1 (Terminal, markdown)
- [ ] Completed Week 2 (VS Code, shortcuts)
- [ ] Completed Week 3 (Local Git basics)
- [ ] Understand git init, add, commit, status, log
- [ ] Have made multiple commits successfully
- [ ] Comfortable with the stage → commit workflow
- [ ] Understand what a commit is

**If you haven't done Weeks 1-3:** Go back and complete them first. Week 4 builds directly on Week 3's Git knowledge.

---

## Critical Week 3 Skills

### You Must Be Comfortable With:

**Basic Git commands:**
```bash
git status      # Check what's changed
git add .       # Stage changes
git commit -m "message"  # Save snapshot
git log         # View history
```

**Quick test - can you do these without looking?**

1. Navigate to a folder
2. Initialize Git (`git init`)
3. Create a file
4. Stage it (`git add`)
5. Commit it (`git commit -m "message"`)
6. View the commit history (`git log`)

**If those feel natural:** You're ready for Week 4.

**If those feel confusing:** Review Week 3 before continuing.

---

## Required Setup

### 1. Git is Installed and Configured

**Verify Git works:**
```bash
git --version
```

**Check your configuration:**
```bash
git config --global user.name
git config --global user.email
```

**You should see your name and email.**

**If not configured:** Review Week 3 prerequisites.

---

### 2. GitHub Account Created

**You need a GitHub account for this week.**

**Check if you have one:**
1. Go to [github.com](https://github.com)
2. Try to sign in

**If you can sign in:** You're ready.

**If you don't have an account:**
1. Go to [github.com](https://github.com)
2. Click "Sign up"
3. Use your work email (if this is for work)
4. Complete the verification
5. Choose the free plan

**Account creation takes 5 minutes.**

---

### 3. Practice Repository from Week 3

**You should have:**
- A folder from Week 3 with Git initialized
- Several commits in the history
- Files like practice-repository.md

**Verify:**
```bash
cd ~/Desktop/week3-practice
git log --oneline
```

**You should see several commits.**

**If you don't have this:**
- Go back to Week 3
- Complete the exercises
- Make sure you have commits before continuing

---

### 4. Create Week 4 Practice Folder

We'll use your Week 3 folder plus create a new one.

**Create new folder:**
```bash
cd ~/Desktop
mkdir week4-practice
cd week4-practice
```

**Verify:**
```bash
pwd
```

Should show: `/Users/YourName/Desktop/week4-practice`

---

## What You'll Learn This Week

This week connects local Git to GitHub:

**Topics:**
- Creating a repository on GitHub
- Connecting local repo to remote (GitHub)
- Pushing commits to GitHub
- Pulling changes from GitHub
- Cloning repositories
- Resolving simple merge conflicts

**New commands:**
- `git remote` - Manage connections to GitHub
- `git push` - Upload commits to GitHub
- `git pull` - Download commits from GitHub
- `git clone` - Download entire repository

**Time needed:** 20-25 minutes

---

## Understanding Remote vs. Local

### The Mental Model

**Local Repository (your computer):**
- Git tracks changes
- You make commits
- History stored in `.git` folder
- Only you can see it

**Remote Repository (GitHub):**
- Cloud backup of your Git history
- Team members can see it
- Enables collaboration
- URL like `github.com/username/project`

**Connection:**
- You "push" local commits to GitHub
- You "pull" others' commits from GitHub
- They stay synchronized

---

## Files You Need

For this lesson, download these files to your `week4-practice` folder:

1. `[A-F]-week4-practice-collaboration.md` - File for practicing push/pull
2. `[A-F]-week4-practice-conflict.md` - Simple merge conflict to resolve
3. `[A-F]-week4-solution-workflow.md` - Expected commands and output

**How to get them:**
- Download from lesson folder
- Move them to `~/Desktop/week4-practice`

**Verify they're there:**
```bash
cd ~/Desktop/week4-practice
ls
```

---

## Important: Authentication

GitHub requires authentication to push commits.

**Two options:**

### Option 1: HTTPS with Token (Recommended for beginners)
- Uses username and personal access token
- Token = special password for Git
- We'll create this during the lesson

### Option 2: SSH Keys
- More secure, no passwords
- Requires setup
- We'll cover this as optional

**You'll set up authentication during the lesson.** Don't worry about it yet.

---

## Common Concerns

**"Will I break something on GitHub?"**
- Your own repositories: You can delete and recreate
- This week: You're only working with your own repos
- Shared repos: That's Week 5, with safety measures

**"What if I push the wrong thing?"**
- You can delete commits from GitHub
- You can make the repository private
- Worst case: Delete repo and start over
- Nothing is permanent at this stage

**"Do I need internet?"**
- Yes, for this week
- GitHub is cloud-based
- Local Git (Week 3) works offline
- Remote Git (Week 4) needs connection

**"Will my commits show up publicly?"**
- Only if you make the repo public
- We'll create private repos for practice
- You control visibility

---

## Checklist Before Starting

- [ ] Completed Weeks 1-3
- [ ] Git commands (init, add, commit, status, log) feel natural
- [ ] GitHub account created and you can sign in
- [ ] Week 3 practice folder still exists with commits
- [ ] Created `week4-practice` folder
- [ ] Downloaded practice files to the folder
- [ ] Have internet connection
- [ ] Understand difference between local and remote

**All checked?**

Proceed to `[A-F]-week4-instructions.md`

---

## If You're Not Ready

**Week 3 still feels confusing:**
- Git is hard at first
- Spend another week practicing local Git
- Make 5-10 commits on different projects
- Come back when `git add` and `git commit` feel automatic

**Don't have GitHub account:**
- Create one now (5 minutes)
- Use your work email if this is for work
- Verify your email address

**Week 3 folder missing or no commits:**
- Redo Week 3 exercises
- You need existing commits to push to GitHub
- Can't learn push/pull without local commits first

**Not sure what a remote is:**
- Read the "Understanding Remote vs. Local" section above
- Think: Local = your computer, Remote = GitHub's servers
- The lesson will make this concrete

---

## Time Expectations

**If Week 3 is solid:** 20-25 minutes for Week 4 lesson

**If Week 3 is shaky:** Review Week 3 first (30 min), then 25-30 min for Week 4

**GitHub account creation:** 5 minutes (one-time)

**Personal access token setup:** 5 minutes (one-time)

---

## Getting Help

**Resources:**
- Week 3 materials (Git basics review)
- GitHub documentation: [docs.github.com](https://docs.github.com)
- Team channel: [your channel]
- Office hours: [day/time]

**Authentication issues are common.** Don't struggle alone - ask for help with tokens/SSH.

---

## What This Unlocks

After Week 4, you'll be able to:
- Backup your work automatically
- Share repositories with teammates
- Work from multiple computers
- Contribute to open source projects
- Show your work to stakeholders via URL

**This is where Git becomes truly powerful.**

---

## Encouragement

Week 3 taught you Git locally. Week 4 teaches you Git collaboratively.

**The commands are simple:**
- `git push` - upload
- `git pull` - download
- `git clone` - copy entire repo

**The concepts take practice:**
- Local vs. remote
- Push vs. pull
- When to sync

**Give it time.** By the end of this week, pushing to GitHub will feel as natural as saving a file.

---

## Ready?

Once you've completed this checklist, verified your GitHub account, and confirmed Week 3 commits exist, proceed to `[A-F]-week4-instructions.md` to begin connecting Git to GitHub.

You're about to put your version control in the cloud.

Let's go.
