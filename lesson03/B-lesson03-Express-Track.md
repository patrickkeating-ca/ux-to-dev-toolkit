# Lesson 3 Express: Git Basics (Local)
## 15-Minute Quick Start

**Note:** Lesson 3 is conceptually the hardest. If this feels confusing, consider taking the full lesson. Git is worth understanding properly.

---

## Goal

Understand just enough Git to start tracking your files.

**Time commitment:** 15-20 minutes

---

## Part 1: Configure Git (2 minutes)

**One-time setup - tell Git who you are:**

```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@company.com"
```

Use your real name and email (same one you'll use for GitHub).

**Verify:**
```bash
git config --global user.name
git config --global user.email
```

---

## Part 2: 5 Git Commands (5 minutes)

### The Workflow

**1. Start tracking a folder:**
```bash
git init
```
Run this once per project.

**2. See what changed:**
```bash
git status
```
Run this constantly. Shows what Git sees.

**3. Stage changes:**
```bash
git add .
```
The dot means "everything". Prepares changes for commit.

**4. Save a snapshot:**
```bash
git commit -m "Your message here"
```
Creates a permanent checkpoint.

**5. See your history:**
```bash
git log --oneline
```
Shows all your snapshots.

**That's it. These 5 commands are 90% of what you'll use.**

---

## Part 3: The Mental Model (3 minutes)

**Git is NOT like regular saving:**

**Regular save:**
- Overwrites the file
- Old version is gone
- Need multiple files for versions

**Git:**
- Keeps one file
- Remembers **all** previous versions
- Like a time machine for your files

**Think of it as:**
- Each commit = snapshot of your project
- Git stores all snapshot
- You can view any photo anytime
- One file. Multiple snapshots

---

## Part 4: Quick Practice (8 minutes)

**Create a test project:**
```bash
cd ~/Desktop
mkdir git-test
cd git-test
git init
```

**Create a file:**
```bash
touch notes.md
echo "# My Notes" > notes.md
```

**Check status:**
```bash
git status
```
You should see "Untracked files: notes.md"

**Stage it:**
```bash
git add .
git status
```
Now it says "Changes to be committed" (in green).

**Commit it:**
```bash
git commit -m "Initial commit - added notes file"
```

**See your history:**
```bash
git log --oneline
```
You should see your commit.

**Make a change:**
```bash
echo "This is my second line" >> notes.md
```

**Check what changed:**
```bash
git status
```
Shows "modified: notes.md"

**Commit the change:**
```bash
git add .
git commit -m "Added second line to notes"
git log --oneline
```

**Now you have 2 commits!**

**If you did all that successfully, you understand basic Git.**

---

## The Cycle You'll Repeat Forever

```
1. Make changes to files
2. git status (see what changed)
3. git add . (stage changes)
4. git commit -m "description" (save snapshot)
5. Repeat
```

**This becomes automatic with practice.**

---

## When to Return to Full Lesson 3

The full Lesson 3 lesson includes:
- Understanding the three states (modified, staged, committed)
- Using .gitignore
- Viewing diffs
- Undoing mistakes
- Advanced commit techniques
- Extended practice scenarios

---

## Common Points of Confusion

**"Why two steps (add, then commit)?"**
- Gives you control over what to commit
- You'll appreciate this later
- For now, just use `git add .` to stage everything

**"Where are my old versions?"**
- In the hidden .git folder
- Git manages them invisibly
- Trust that they're there

**"What if I mess up?"**
- Almost everything in Git is recoverable
- Don't worry about breaking things locally
- Lesson 4 covers undoing mistakes

---

## AI Prompt for Custom Learning

Ask ChatGPT/Claude/Copilot:

```
I'm learning Git for version control. I have 20 minutes. Explain the 
absolute minimum I need to know to start tracking files locally. Use 
simple analogies - I'm not a programmer. What are the essential 
commands and concepts?
```

---

## Cheat Sheet

```bash
git init              # Start tracking (once per project)
git status            # What changed? (use constantly)
git add .             # Stage everything
git commit -m "msg"   # Save snapshot
git log --oneline     # See history
```

**Memorize this flow. Everything else is bonus.**

---

## Critical Understanding

**Before moving to Lesson 4, make sure you can:**
- Initialize a Git repository
- Make commits
- View commit history
- Understand commits are snapshots

---

## Next Step

Lesson 4 Express will connect this local Git to GitHub (the cloud).
