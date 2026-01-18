# Week 3: Git Basics (Local)
## 5-Minute Hands-On Lesson

### What You'll Learn

By the end of this lesson, you'll:
- Initialize a Git repository
- Stage and commit changes
- Check the status of your files
- View commit history
- Understand what Git is actually doing

**Time needed:** 15-20 minutes

**Important:** This week is local Git only. Everything stays on your computer. No GitHub, no internet needed.

---

## The Five Essential Commands

This entire lesson uses just 5 commands:

1. `git init` - Start tracking a folder
2. `git status` - See what's changed
3. `git add` - Stage changes for commit
4. `git commit` - Save a snapshot
5. `git log` - View history

**That's it. Master these 5 and you understand Git.**

---

## Part 1: Understanding Git's Mental Model (2 minutes)

### Before You Type Anything

Think of Git like a photographer taking pictures of your project:

**Traditional saving:**
- "File → Save" overwrites the file
- You lose the previous version
- To keep old versions, you make copies with different names

**Git saving:**
- Each commit is a photograph of your entire project
- All photos are stored in one place (the `.git` folder)
- You can look at any photo anytime
- Files don't multiply - you just have one set of files plus the photo album

**Key insight:** Git doesn't create `file_v1.md`, `file_v2.md`, `file_v3.md`. It keeps ONE version of each file, plus a complete history of every change.

---

## Part 2: Initialize Your First Repository (2 minutes)

### What "Initialize" Means

Initializing tells Git "start tracking changes in this folder."

### Do This

**Open Terminal and navigate to your practice folder:**
```bash
cd ~/Desktop/week3-practice
```

**Initialize Git:**
```bash
git init
```

**You should see:**
```
Initialized empty Git repository in /Users/YourName/Desktop/week3-practice/.git/
```

**What just happened:**
- Git created a hidden `.git` folder
- This folder stores all the history and snapshots
- Your folder is now a "repository" (repo for short)

**Verify:**
```bash
ls -la
```

You should see `.git` in the list (the `-a` flag shows hidden files).

**Success check:** You see "Initialized empty Git repository" message

---

## Part 3: Check Status (1 minute)

### The Most Important Command

`git status` tells you what Git sees. Use it constantly.

**Check status:**
```bash
git status
```

**You should see:**
```
On branch main

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        03-week3-practice-repository.md
        04-week3-practice-gitignore.txt
        05-week3-solution-history.md

nothing added to commit but untracked files present (use "git add" to track)
```

**Translation:**
- "Untracked files" = Git sees these files but isn't tracking them yet
- You need to explicitly tell Git which files to track

**Git status is your friend.** Run it before and after every command while learning.

---

## Part 4: Stage Changes (2 minutes)

### The Two-Step Process

Git requires two steps to save changes:
1. **Stage** (git add) - "I want to include these changes"
2. **Commit** (git commit) - "Save these staged changes permanently"

**Why two steps?** Control. You can stage some files but not others, creating logical commits.

### Stage a File

**Stage one file:**
```bash
git add 03-week3-practice-repository.md
```

**Check what happened:**
```bash
git status
```

**You should see:**
```
Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   03-week3-practice-repository.md

Untracked files:
        04-week3-practice-gitignore.txt
        05-week3-solution-history.md
```

**Translation:**
- Green text = staged (ready to commit)
- Red text = not staged yet

**Stage all remaining files:**
```bash
git add .
```

The `.` means "everything in current folder"

**Check status again:**
```bash
git status
```

All files should now be green (staged).

**Success check:** All files show as "Changes to be committed" in green

---

## Part 5: Make Your First Commit (2 minutes)

### What is a Commit?

A commit is a snapshot of your project at this moment, plus a message explaining what you did.

### Commit the Staged Files

**Create your first commit:**
```bash
git commit -m "Initial commit - added practice files"
```

The `-m` flag lets you write the message in the same command.

**You should see:**
```
[main (root-commit) abc123] Initial commit - added practice files
 3 files changed, 150 insertions(+)
 create mode 100644 03-week3-practice-repository.md
 create mode 100644 04-week3-practice-gitignore.txt
 create mode 100644 05-week3-solution-history.md
```

**What just happened:**
- Git took a snapshot of all staged files
- Assigned it a unique ID (abc123)
- Stored it permanently in the `.git` folder
- Attached your message to it

**Check status:**
```bash
git status
```

**You should see:**
```
On branch main
nothing to commit, working tree clean
```

**Translation:** Everything is committed. No changes since last commit.

**Success check:** Status says "working tree clean"

---

## Part 6: Make Changes and Commit Again (3 minutes)

### The Daily Workflow

Now practice the cycle you'll use constantly: edit → stage → commit

### Edit a File

**Open VS Code:**
```bash
code .
```

**Open `03-week3-practice-repository.md` and make any change:**
- Add a line
- Change some text
- Whatever you want

**Save the file** (Command + S)

### See What Git Noticed

**In Terminal:**
```bash
git status
```

**You should see:**
```
On branch main
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   03-week3-practice-repository.md

no changes added to commit (use "git add" and/or "git commit -a")
```

**Translation:** Git noticed you changed the file, but it's not staged yet.

### See Exactly What Changed

**View the changes:**
```bash
git diff 03-week3-practice-repository.md
```

**You'll see:**
- Lines you removed (in red with -)
- Lines you added (in green with +)

Press `q` to exit the diff view.

**This is powerful:** Git shows you exactly what changed line-by-line.

### Stage and Commit the Change

**Stage:**
```bash
git add 03-week3-practice-repository.md
```

**Commit:**
```bash
git commit -m "Updated practice repository file with additional notes"
```

**Check status:**
```bash
git status
```

Should say "working tree clean" again.

**Success check:** You made a change, staged it, and committed it successfully

---

## Part 7: View History (2 minutes)

### See All Your Commits

**View commit history:**
```bash
git log
```

**You should see something like:**
```
commit def456... (HEAD -> main)
Author: Your Name <your.email@company.com>
Date:   Thu Jan 16 14:32:00 2025

    Updated practice repository file with additional notes

commit abc123...
Author: Your Name <your.email@company.com>
Date:   Thu Jan 16 14:20:00 2025

    Initial commit - added practice files
```

**Translation:**
- Each commit has a unique ID (abc123, def456)
- Shows who made it
- Shows when
- Shows the commit message

**Press `q` to exit log view.**

### Prettier History View

**One-line format:**
```bash
git log --oneline
```

**You should see:**
```
def456 Updated practice repository file with additional notes
abc123 Initial commit - added practice files
```

Much easier to read! This shows just the ID and message.

**Success check:** You can see your commit history

---

## Part 8: The .gitignore File (3 minutes)

### Why .gitignore Matters

Some files shouldn't be tracked by Git:
- System files (.DS_Store on Mac)
- Temporary files
- Large files
- Files with sensitive data

**.gitignore tells Git to ignore these files.**

### Create .gitignore

**In Terminal:**
```bash
touch .gitignore
```

**Open in VS Code:**
```bash
code .gitignore
```

**Add these lines:**
```
# Mac system files
.DS_Store

# Temporary files
*.tmp
*.temp

# Log files
*.log

# Large Sketch files
*.sketch

# Sensitive data
secrets.txt
api-keys.txt
```

Lines starting with `#` are comments explaining what you're ignoring.

**Save the file** (Command + S)

### Commit .gitignore

```bash
git add .gitignore
git commit -m "Added .gitignore to exclude system and temp files"
```

**Now Git will ignore those file types automatically.**

**Test it:**
```bash
touch .DS_Store
git status
```

You shouldn't see .DS_Store in the status - Git is ignoring it!

**Success check:** .gitignore file committed and working

---

## Part 9: Understanding the Three States (2 minutes)

### Files Can Be in Three States

**1. Modified (Working Directory)**
- You changed the file
- Git noticed
- Not staged yet
- **Color in status:** Red

**2. Staged (Staging Area)**
- You ran `git add`
- Changes are ready to commit
- Not committed yet
- **Color in status:** Green

**3. Committed (Repository)**
- You ran `git commit`
- Changes are saved permanently
- **Status:** "working tree clean"

### The Flow

```
Edit file → Modified (red)
↓
git add → Staged (green)
↓
git commit → Committed (clean)
```

**This is the cycle you'll repeat hundreds of times.**

---

## Part 10: Practice Exercise (5 minutes)

### The Challenge

Complete these steps without looking at instructions:

1. Create a new file called `notes.md`
2. Add some content to it
3. Check Git status (should show untracked file)
4. Stage the file
5. Commit with message "Added notes file"
6. Edit the file (add more content)
7. Check Git status (should show modified)
8. View what changed with `git diff`
9. Stage and commit the changes
10. View your commit history

**Use `git status` between every step.**

### Self-Check

After completing the exercise:

```bash
git log --oneline
```

You should see at least 4 commits:
1. Initial commit
2. Updated practice repository
3. Added .gitignore
4. Added notes file
5. (Your edit to notes.md)

**If you have these commits, you did it correctly!**

---

## Tools to Help You

**Absolutely use any resource:**

### When Stuck

**Google:**
- "git basics tutorial"
- "what does git add do"
- "git status explained"

**AI Assistants:**
- "Explain git commit in simple terms"
- "What's the difference between git add and git commit?"
- "Why do I need to stage files in git?"

### Command Help

**Built-in help:**
```bash
git help status
git help commit
git help log
```

**Or online:**
- [Git Documentation](https://git-scm.com/doc)
- [GitHub Git Handbook](https://guides.github.com/introduction/git-handbook/)

### VS Code Git Integration

**VS Code shows Git status visually:**
- Click Source Control icon in sidebar (branch icon)
- See changed files
- Click files to see diffs
- Can stage/commit from UI

**But learn Terminal first.** Understanding the commands helps you troubleshoot.

---

## Common Mistakes

### "I forgot to commit"

**You made changes but didn't commit.**

**How to tell:**
```bash
git status
```

If it shows modified files, you forgot to commit.

**Fix:**
```bash
git add .
git commit -m "Your message"
```

---

### "I committed to the wrong message"

**Last commit has typo or wrong message.**

**Fix (if not pushed to GitHub yet):**
```bash
git commit --amend -m "Corrected message"
```

This replaces the last commit message.

---

### "What did I just commit?"

**Show last commit:**
```bash
git show
```

Shows exactly what changed in the most recent commit.

---

### "I want to uncommit"

**Undo last commit but keep changes:**
```bash
git reset --soft HEAD~1
```

Changes go back to staged state.

**Undo last commit and discard changes:**
```bash
git reset --hard HEAD~1
```

**Warning:** `--hard` deletes your changes. Use carefully.

---

## Completion Checklist

You're done when you can:

- [ ] Initialize a Git repository (`git init`)
- [ ] Check status (`git status`)
- [ ] Stage files (`git add`)
- [ ] Commit changes (`git commit -m "message"`)
- [ ] View history (`git log`)
- [ ] Understand modified vs. staged vs. committed
- [ ] Create and use .gitignore
- [ ] Make multiple commits showing progression
- [ ] Explain what a commit is in your own words

**Bonus:**
- [ ] Use `git diff` to see changes
- [ ] Use `git log --oneline` for clean history
- [ ] Committed at least 4-5 times during practice
- [ ] Feel comfortable with the stage → commit workflow

---

## What You Accomplished

**You just:**
- Learned version control fundamentals
- Created a Git repository from scratch
- Made meaningful commits with messages
- Tracked your changes over time
- Set up proper file exclusions

**This is real Git.** Developers use these exact commands daily.

---

## Critical Understanding

**Before moving on, make sure you understand:**

**Q: What's the difference between staging and committing?**
A: Staging (`git add`) prepares changes. Committing (`git commit`) saves them permanently.

**Q: Why stage first?**
A: Control. You can commit some changes but not others, creating logical groupings.

**Q: Can I see old versions?**
A: Yes! Every commit is a snapshot you can return to.

**Q: Where is the history stored?**
A: In the hidden `.git` folder. Don't delete it!

**If these make sense, you're ready for Week 4.**

---

## Before Next Week

**Daily practice (3 minutes):**

1. Navigate to any project folder
2. Make a change to a file
3. `git status` to see it
4. `git add` to stage it
5. `git commit -m "message"` to save it

**Do this once a day for 5 days.**

By Week 4, this workflow will be automatic.

---

## Next Week Preview

**Week 4: GitHub & Remote Repos**
- Connect your local repo to GitHub
- Push your commits to the cloud
- Pull changes from GitHub
- Clone repositories
- Handle merge conflicts (the simple kind)

**Preparation:**
- Make sure this week's commands feel natural
- Practice the stage → commit workflow
- Get comfortable with `git status` and `git log`

---

## The Mindset Shift

**Traditional thinking:** "I need to keep all my old versions"
**Git thinking:** "I have one file, Git remembers everything"

**This mental shift is the hardest part.**

Once it clicks, you'll never want to work without version control again.

---

## Encouragement

If this week felt confusing, that's completely normal.

**Git is:**
- A fundamentally different paradigm
- Invisible (you don't "see" the snapshots)
- Abstract (commits are conceptual, not visible files)

**Give it time.**

By Week 5, when you're collaborating with teammates and can see the full power, it'll all make sense.

**Week 3 is the conceptual hump. You just climbed it.**

---

## Questions or Stuck?

**Resources:**
- Solution files showing expected git log output
- Pro Git book (free): [git-scm.com/book](https://git-scm.com/book/en/v2)
- Team channel: [your channel]
- Office hours: [day/time]

**Remember:** Everyone struggles with Git at first. Ask for help.

The concepts are strange because they're powerful.

---

## Final Thought

**You now understand version control.**

This puts you ahead of many people who work with computers professionally.

Next week, you'll put this power in the cloud with GitHub.

Great work. See you in Week 4.
