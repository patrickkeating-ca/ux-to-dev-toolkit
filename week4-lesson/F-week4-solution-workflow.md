# Week 4 Solution - Expected Workflow

## Complete Command Sequence

This file shows the expected commands and their output for Week 4 exercises.

---

## Part 1: Initial Setup

### Create Repository on GitHub

**Actions on GitHub website:**
1. Click + icon → New repository
2. Name: `ux-practice-week4`
3. Private repository
4. Don't initialize with anything
5. Click "Create repository"

**Result:** Empty repository with setup instructions displayed

---

### Connect Local to Remote

**Commands:**
```bash
cd ~/Desktop/week3-practice
git remote add origin https://github.com/yourusername/ux-practice-week4.git
git remote -v
```

**Expected output of `git remote -v`:**
```
origin  https://github.com/yourusername/ux-practice-week4.git (fetch)
origin  https://github.com/yourusername/ux-practice-week4.git (push)
```

---

### First Push

**Commands:**
```bash
git push -u origin main
```

**Expected interaction:**
```
Username: your-github-username
Password: [paste personal access token]
```

**Expected output:**
```
Enumerating objects: 15, done.
Counting objects: 100% (15/15), done.
Delta compression using up to 8 threads.
Compressing objects: 100% (12/12), done.
Writing objects: 100% (15/15), 1.45 KiB | 1.45 MiB/s, done.
Total 15 (delta 3), reused 0 (delta 0), pack-reused 0
To https://github.com/yourusername/ux-practice-week4.git
 * [new branch]      main -> main
Branch 'main' set up to track remote branch 'main' from 'origin'.
```

**What this means:**
- All your Week 3 commits are now on GitHub
- Branch `main` is set to track remote `main`
- Future pushes only need `git push` (no flags)

---

## Part 2: Regular Workflow

### Make Local Change and Push

**Commands:**
```bash
# Edit a file in VS Code
code 03-week3-practice-repository.md
# [make changes, save]

git status
```

**Expected output:**
```
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   03-week3-practice-repository.md

no changes added to commit (use "git add" and/or "git commit -a")
```

**Continue:**
```bash
git add .
git commit -m "Updated practice repository with notes"
git push
```

**Expected output of push:**
```
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads.
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 345 bytes | 345.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0), pack-reused 0
To https://github.com/yourusername/ux-practice-week4.git
   abc1234..def5678  main -> main
```

**What this means:**
- Commit successfully pushed
- Remote updated from commit abc1234 to def5678

---

### Make GitHub Change and Pull

**Actions on GitHub:**
1. Open a file
2. Click Edit (pencil)
3. Make changes
4. Commit: "Updated from GitHub"

**Commands on your computer:**
```bash
git pull
```

**Expected output:**
```
remote: Enumerating objects: 5, done.
remote: Counting objects: 100% (5/5), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), 678 bytes | 678.00 KiB/s, done.
From https://github.com/yourusername/ux-practice-week4
   def5678..ghi9012  main       -> origin/main
Updating def5678..ghi9012
Fast-forward
 03-week3-practice-repository.md | 2 +-
 1 file changed, 1 insertion(+), 1 deletion(-)
```

**What this means:**
- Downloaded commit ghi9012 from GitHub
- Applied changes to your local files
- "Fast-forward" = simple merge, no conflicts

---

## Part 3: Cloning

### Clone Your Repository

**Commands:**
```bash
cd ~/Desktop
mkdir github-clones
cd github-clones
git clone https://github.com/yourusername/ux-practice-week4.git
```

**Expected output:**
```
Cloning into 'ux-practice-week4'...
remote: Enumerating objects: 18, done.
remote: Counting objects: 100% (18/18), done.
remote: Compressing objects: 100% (15/15), done.
remote: Total 18 (delta 3), reused 18 (delta 3), pack-reused 0
Receiving objects: 100% (18/18), 1.78 KiB | 1.78 MiB/s, done.
Resolving deltas: 100% (3/3), done.
```

**Verify:**
```bash
cd ux-practice-week4
ls
git log --oneline
```

**Expected:** All files and commit history are present

---

## Part 4: Merge Conflict Resolution

### Creating the Conflict

**Sequence of events:**

1. **Edit locally (DON'T commit):**
   - Open file, make change
   - Save but don't commit

2. **Edit on GitHub:**
   - Same file, same lines, different change
   - Commit on GitHub

3. **Commit locally:**
   ```bash
   git add .
   git commit -m "Made local changes"
   ```

4. **Try to push:**
   ```bash
   git push
   ```

**Expected error:**
```
To https://github.com/yourusername/ux-practice-week4.git
 ! [rejected]        main -> main (fetch first)
error: failed to push some refs to 'https://github.com/yourusername/ux-practice-week4.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
```

**What this means:** GitHub has commits you don't have. Must pull first.

---

### Resolving the Conflict

**Pull to get GitHub's changes:**
```bash
git pull
```

**Expected conflict message:**
```
Auto-merging [A-F]-week4-practice-conflict.md
CONFLICT (content): Merge conflict in [A-F]-week4-practice-conflict.md
Automatic merge failed; fix conflicts and then commit the result.
```

**Check status:**
```bash
git status
```

**Expected output:**
```
On branch main
Your branch and 'origin/main' have diverged,
and have 1 and 1 different commits each, respectively.
  (use "git pull" to merge the remote branch into yours)

You have unmerged paths.
  (fix conflicts and run "git commit")
  (use "git merge --abort" to abort the merge)

Unmerged paths:
  (use "git add <file>..." to mark resolution)
        both modified:   [A-F]-week4-practice-conflict.md

no changes added to commit (use "git add" and/or "git commit -a")
```

**What this means:**
- File has conflicts
- You need to resolve them
- Then mark as resolved with `git add`
- Then commit the resolution

---

### Inside the Conflicted File

**Open the file in VS Code. You'll see:**

```markdown
**Favorite Tool:** <<<<<<< HEAD
Figma
=======
Sketch
>>>>>>> abc123def456
```

**VS Code shows these options:**
- Accept Current Change (Figma)
- Accept Incoming Change (Sketch)
- Accept Both Changes
- Compare Changes

**After choosing (example: Accept Current Change):**

```markdown
**Favorite Tool:** Figma
```

**All conflict markers removed.**

---

### Mark as Resolved

**Commands:**
```bash
git add [A-F]-week4-practice-conflict.md
git status
```

**Expected output:**
```
On branch main
Your branch and 'origin/main' have diverged,
and have 1 and 1 different commits each, respectively.

All conflicts fixed but you are still merging.
  (use "git commit" to conclude merge)

Changes to be committed:
        modified:   [A-F]-week4-practice-conflict.md
```

**Commit the resolution:**
```bash
git commit -m "Resolved merge conflict in practice file"
```

**Expected output:**
```
[main jkl3456] Resolved merge conflict in practice file
```

**Push the resolution:**
```bash
git push
```

**Expected output:**
```
Enumerating objects: 10, done.
Counting objects: 100% (10/10), done.
Delta compression using up to 8 threads.
Compressing objects: 100% (6/6), done.
Writing objects: 100% (6/6), 678 bytes | 678.00 KiB/s, done.
Total 6 (delta 4), reused 0 (delta 0), pack-reused 0
To https://github.com/yourusername/ux-practice-week4.git
   ghi9012..jkl3456  main -> main
```

**Conflict resolved and pushed successfully!**

---

## Part 5: Checking Sync Status

### Commands to Check Status

**Check if you're in sync:**
```bash
git status
```

**If in sync:**
```
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
```

**If ahead (unpushed commits):**
```
On branch main
Your branch is ahead of 'origin/main' by 2 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
```

**If behind (GitHub has commits you don't):**
```
On branch main
Your branch is behind 'origin/main' by 1 commit.
  (use "git pull" to update your local branch)

nothing to commit, working tree clean
```

**If diverged (both have unique commits):**
```
On branch main
Your branch and 'origin/main' have diverged,
and have 2 and 1 different commits each, respectively.
  (use "git pull" to merge the remote branch into yours)

nothing to commit, working tree clean
```

---

## Common Command Patterns

### Daily Start of Work

```bash
git pull
```

**Expected if no new changes:**
```
Already up to date.
```

**Expected if there are new changes:**
```
Updating abc1234..def5678
Fast-forward
 file.md | 3 ++-
 1 file changed, 2 insertions(+), 1 deletion(-)
```

---

### After Making Changes

```bash
git status        # See what changed
git add .         # Stage all changes
git commit -m "Descriptive message"
git push          # Send to GitHub
```

---

### End of Day

```bash
git status        # Anything uncommitted?
git add .         # Stage it
git commit -m "End of day commit - work in progress"
git push          # Backup to GitHub
```

---

## Expected Git Log After Week 4

**Command:**
```bash
git log --oneline
```

**Expected output (something like):**
```
jkl3456 Resolved merge conflict in practice file
mno7890 Made local changes
ghi9012 Updated from GitHub
def5678 Updated practice repository with notes
abc1234 Added .gitignore to exclude system and temp files
xyz9876 Updated practice repository file with additional notes
uvw5432 Initial commit - added practice files
```

**What this shows:**
- Multiple commits from Week 3
- New commits from Week 4
- Merge conflict resolution
- Complete history of your work

---

## Troubleshooting Common Outputs

### "fatal: not a git repository"

**Cause:** You're not in a Git repository folder

**Fix:**
```bash
cd ~/Desktop/week3-practice
# Now try git command again
```

---

### "fatal: 'origin' does not appear to be a git repository"

**Cause:** Remote not configured

**Fix:**
```bash
git remote add origin https://github.com/yourusername/ux-practice-week4.git
```

---

### "Permission denied (publickey)"

**Cause:** Using SSH but keys not set up, or wrong credentials

**Fix:** Use HTTPS instead or set up SSH keys

---

### "Authentication failed"

**Cause:** Wrong username or token

**Fix:**
- Verify GitHub username
- Use personal access token as password, not GitHub password
- Generate new token if needed

---

## Self-Check: Your Repository Should Have

After completing Week 4:

- [ ] Repository exists on GitHub
- [ ] Local repo connected to GitHub (git remote -v shows origin)
- [ ] Multiple commits pushed to GitHub
- [ ] Can view commits on GitHub website
- [ ] Have pulled changes from GitHub
- [ ] Resolved at least one merge conflict
- [ ] git status shows "up to date" when in sync
- [ ] Can clone the repository to a new location

---

## Success Indicators

**You know Week 4 worked if:**

1. Your repository is visible on github.com
2. Commits from Week 3 appear on GitHub
3. New commits you made locally are on GitHub
4. Changes made on GitHub pulled to your computer
5. You resolved a conflict without panic
6. `git log` matches what you see on GitHub
7. Push and pull feel natural

---

## Next Week Preview

**Week 5 will add:**
- Working with branches
- Creating pull requests
- Code review workflow
- Collaboration with teammates

**Foundation from Week 4:**
- Push/pull is automatic
- Conflicts don't scare you
- GitHub is your backup
- You're ready to collaborate

---

## Final Verification

**Run these commands to verify everything worked:**

```bash
# Check remote connection
git remote -v

# Check you're in sync
git status

# View your history
git log --oneline -10

# Verify on GitHub
# Open browser, go to your repository
# Check commits appear
# Check files are there
```

**If all of these work, Week 4 is complete!**

---

**Congratulations! Your version control is now in the cloud.**
