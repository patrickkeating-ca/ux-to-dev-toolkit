# Prerequisites Check - Week 3
## Git Basics (Local)

### Before Starting This Lesson

Week 3 introduces Git - the version control system that tracks changes to your files. This week focuses on local Git operations (on your computer only, no GitHub yet).

---

## Week 1 & 2 Completion Check

You should have already:

- [ ] Completed Week 1 (Terminal basics, markdown)
- [ ] Completed Week 2 (VS Code setup, shortcuts)
- [ ] Comfortable using Terminal commands
- [ ] Can open folders in VS Code with `code .`
- [ ] Installed VS Code extensions
- [ ] Used keyboard shortcuts successfully

**If you haven't done Weeks 1-2:** Go back and complete them first. Week 3 builds directly on those skills.

---

## Required Setup

### 1. Terminal Comfort Level

**Quick test - can you do these without looking up commands?**

```bash
# Navigate to Desktop
cd ~/Desktop

# Create a folder
mkdir test-folder

# Go into it
cd test-folder

# Create a file
touch test.md

# Go back to Desktop
cd ~/Desktop

# Delete the test folder
rm -r test-folder
```

**If those feel unfamiliar:** Review Week 1 before continuing.

**If those feel natural:** You're ready for Week 3.

---

### 2. VS Code Proficiency

**Quick test:**

- Can you open a folder in VS Code from Terminal? (`code .`)
- Can you use Command + P to find files?
- Can you toggle the integrated terminal? (Control + `)
- Can you preview markdown? (Command + K, V)

**If yes to all:** You're ready.

**If no to any:** Review Week 2 shortcuts before continuing.

---

### 3. Git Installation Check

Git comes pre-installed on Mac, but let's verify it works.

**Check Git version:**
```bash
git --version
```

**Expected result:** Something like `git version 2.39.0` (exact version doesn't matter)

**If you see "command not found":**

Git isn't installed. Install it:

**Option 1: Via Homebrew (recommended)**
```bash
brew install git
```

**Option 2: Via Xcode Command Line Tools**
```bash
xcode-select --install
```

Follow the prompts. This takes 5-10 minutes.

**Verify installation:**
```bash
git --version
```

---

### 4. Git Configuration (First Time Only)

Git needs to know who you are to track who makes changes.

**Set your name:**
```bash
git config --global user.name "Your Name"
```

**Set your email:**
```bash
git config --global user.email "your.email@company.com"
```

Use your real name and work email (same email you'll use for GitHub in Week 4).

**Verify it worked:**
```bash
git config --global user.name
git config --global user.email
```

You should see your name and email printed back.

**This is one-time setup.** You won't need to do this again.

---

### 5. Create Week 3 Practice Folder

```bash
cd ~/Desktop
mkdir week3-practice
cd week3-practice
```

**Verify:**
```bash
pwd
```

You should see: `/Users/YourName/Desktop/week3-practice`

---

## What You'll Learn This Week

This week focuses on **local Git** - everything happens on your computer. No GitHub, no internet needed.

**Topics:**
- What Git actually does (demystifying version control)
- Initializing a repository
- Staging and committing changes
- Checking status
- Viewing commit history
- Understanding the three states of files

**What you won't do yet:**
- Push to GitHub (that's Week 4)
- Work with branches (Week 4)
- Collaborate with others (Week 5)

**Time needed:** 15-20 minutes

---

## Files You Need

For this lesson, download these files to your `week3-practice` folder:

1. `03-week3-practice-repository.md` - File to track with Git
2. `04-week3-practice-gitignore.txt` - Practice creating .gitignore
3. `05-week3-solution-history.md` - What your git log should look like

**How to get them:**
- Download from lesson folder
- Move them to `~/Desktop/week3-practice`

**Verify they're there:**
```bash
cd ~/Desktop/week3-practice
ls
```

---

## Understanding What Git Does

Before starting, understand the basic concept:

**Without Git:**
- `final.md`
- `final_v2.md`
- `final_v3.md`
- `final_ACTUALLY_FINAL.md`
- You have no idea what changed between versions

**With Git:**
- `document.md` (one file)
- Git tracks every change you've ever made
- You can see who changed what and when
- You can go back to any previous version
- You write notes explaining each change

**Git is like a save game system for your files.**

---

## Common Misconceptions

**"Git is complicated"**
- True for advanced features
- Basic Git (this week) is just 5 commands
- You'll use those 5 commands 95% of the time

**"I can break things"**
- Git is designed to prevent data loss
- Almost everything is undoable
- Local Git (this week) can't affect anyone else

**"I need to understand everything"**
- No! You need to understand: init, add, commit, status, log
- That's it for this week

**"Git and GitHub are the same thing"**
- Git = version control software (on your computer)
- GitHub = website for storing Git repositories
- This week: Just Git, no GitHub

---

## Checklist Before Starting

- [ ] Completed Weeks 1 and 2
- [ ] Terminal commands feel natural
- [ ] VS Code shortcuts are comfortable
- [ ] Git is installed (`git --version` works)
- [ ] Git is configured (name and email set)
- [ ] Created `week3-practice` folder
- [ ] Downloaded practice files to the folder
- [ ] Understand Git tracks changes (not creates multiple files)

**All checked?**

Proceed to `02-week3-instructions.md`

---

## If You're Not Ready

**Week 1 or 2 still feels shaky:**
- Spend another few days on those skills
- Git builds directly on Terminal and VS Code
- Come back when you're comfortable

**Git isn't installed:**
- Follow installation steps above
- Don't skip the configuration step
- Verify with `git --version`

**Confused about what Git does:**
- That's normal before starting
- The lesson will make it clear through practice
- Understanding comes from doing

---

## Time Expectations

**If Weeks 1-2 are solid:** 15-20 minutes for Week 3 lesson

**If Weeks 1-2 are shaky:** Review those first, then 20-30 minutes for Week 3

**Git configuration:** 2 minutes (one-time only)

---

## Getting Help

**Resources:**
- Week 1 materials (Terminal review)
- Week 2 materials (VS Code review)
- Team channel: [your channel]
- Office hours: [day/time]

**Remember:** Git feels strange at first because it's a completely new concept. By Week 4, it'll click.

---

## Encouragement

**This is the hardest week conceptually.**

You're learning a fundamentally different way of saving files. Your brain is used to "File → Save" creating multiple versions.

Git works differently. Trust the process. Do the exercises. It'll make sense.

**By next week, you'll wonder how you ever worked without it.**

---

## Ready?

Once you've completed this checklist and verified Git works, proceed to `02-week3-instructions.md` to begin learning local Git operations.

You've got this.
