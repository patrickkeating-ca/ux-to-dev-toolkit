# Week 5 Solution - Branch Workflow

## Expected Commands and Flow

This file shows the complete branch workflow you should be able to execute after Week 5.

---

## Part 1: Creating Your First Branch

### Commands

```bash
# Start from main
git checkout main
git pull

# Create and switch to feature branch
git checkout -b feature/add-collaboration-guide
```

### Expected Output

```
Switched to a new branch 'feature/add-collaboration-guide'
```

### Verify

```bash
git branch
```

**Expected:**
```
* feature/add-collaboration-guide
  main
```

The asterisk shows you're on the feature branch.

---

## Part 2: Making Changes on Branch

### Commands

```bash
# Make changes to files
code 03-week5-practice-feature.md
# [edit and save]

# Check status
git status
```

### Expected Output

```
On branch feature/add-collaboration-guide
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   03-week5-practice-feature.md

no changes added to commit (use "git add" and/or "git commit -a")
```

### Commit Changes

```bash
git add .
git commit -m "Added collaboration guide examples"
```

**Expected:**
```
[feature/add-collaboration-guide abc1234] Added collaboration guide examples
 1 file changed, 15 insertions(+)
```

---

## Part 3: Pushing Feature Branch

### Command

```bash
git push -u origin feature/add-collaboration-guide
```

### Expected Output

```
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads.
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 456 bytes | 456.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/yourusername/week5-collaboration.git
 * [new branch]      feature/add-collaboration-guide -> feature/add-collaboration-guide
Branch 'feature/add-collaboration-guide' set up to track remote branch 'feature/add-collaboration-guide' from 'origin'.
```

**What this means:**
- New branch created on GitHub
- Local branch tracking remote branch
- Future pushes on this branch just need `git push`

---

## Part 4: Creating Pull Request

### On GitHub

**Navigate to:**
`https://github.com/yourusername/week5-collaboration`

**You should see:**
Yellow banner: "feature/add-collaboration-guide had recent pushes" with "Compare & pull request" button

**Or:**
1. Click "Pull requests" tab
2. Click "New pull request"
3. Base: main
4. Compare: feature/add-collaboration-guide

**Fill out:**
```
Title: Add collaboration guide section

Description:
## What Changed
Added collaboration guide with team workflows and best practices.

## Why
Team needs documented process for working together on UX projects.

## Testing
- Reviewed markdown formatting
- Verified examples are clear
- Checked all links work
```

**Click:** "Create pull request"

### Expected PR Page

**You should see:**
- Conversation tab (active)
- Commits tab (shows your commits)
- Files changed tab (shows diffs)
- Green "Merge pull request" button (if no conflicts)
- "This branch has no conflicts with the base branch"

---

## Part 5: Reviewing the PR

### Review Process

**Go to "Files changed" tab**

**You should see:**
- Green lines (additions)
- Red lines (deletions)
- Unchanged context
- Can click + on any line to comment

**Add a review comment:**
1. Hover over a line
2. Click the blue + icon
3. Type: "This section explains the workflow clearly!"
4. Click "Add single comment"

**Submit review:**
1. Click green "Review changes" button (top right)
2. Add comment: "Approving this PR - looks great!"
3. Select "Approve"
4. Click "Submit review"

### Expected Review Status

**PR page should show:**
- Green checkmark
- "Approved" status
- "All checks have passed" (if no required checks)
- Green "Merge pull request" button becomes active

---

## Part 6: Merging the PR

### Commands on GitHub

**Click:** "Merge pull request" button

**Expected dialog:**
```
Merge pull request #1 from yourusername/feature/add-collaboration-guide

Add collaboration guide section
```

**Click:** "Confirm merge"

### Expected Result

**You should see:**
```
Pull request successfully merged and closed
```

**Purple "Merged" badge appears**

**Optional but recommended:**
Click "Delete branch" button that appears

### Expected on Branches Page

**Go to repository → Branches**

**You should see:**
- `main` branch (default)
- `feature/add-collaboration-guide` (if not deleted) or
- Deleted branches section (if deleted)

---

## Part 7: Updating Local Repository

### Commands

```bash
# Switch to main
git checkout main
```

**Expected:**
```
Switched to branch 'main'
Your branch is behind 'origin/main' by 2 commits.
  (use "git pull" to update your local branch)
```

```bash
# Pull merged changes
git pull
```

**Expected:**
```
Updating def5678..ghi9012
Fast-forward
 03-week5-practice-feature.md | 15 +++++++++++++++
 1 file changed, 15 insertions(+)
```

### Verify Changes

```bash
# Check history
git log --oneline -5
```

**Expected (something like):**
```
ghi9012 Merge pull request #1 from yourusername/feature/add-collaboration-guide
abc1234 Added collaboration guide examples
xyz7890 Initial commit
```

**The merge commit appears in history!**

---

## Part 8: Cleaning Up

### Delete Local Branch

```bash
git branch -d feature/add-collaboration-guide
```

**Expected:**
```
Deleted branch feature/add-collaboration-guide (was abc1234).
```

### Verify

```bash
git branch
```

**Expected:**
```
* main
```

**Only main branch remains locally.**

---

## Complete Second Cycle

### Full Workflow Again

```bash
# 1. Create branch
git checkout main
git pull
git checkout -b feature/improve-documentation

# 2. Make changes
echo "# Documentation Improvements" > improvements.md
git add .
git commit -m "Added documentation improvements"

# 3. Push
git push -u origin feature/improve-documentation

# 4. Create PR on GitHub
# (navigate to repository, create PR)

# 5. Review and merge PR on GitHub

# 6. Update local
git checkout main
git pull
git branch -d feature/improve-documentation
```

**You should be able to do this without looking at instructions.**

---

## Branch States

### Checking Branch Status

**List all branches:**
```bash
git branch -a
```

**Expected:**
```
* main
  remotes/origin/HEAD -> origin/main
  remotes/origin/main
  remotes/origin/feature/add-collaboration-guide
```

Shows local and remote branches.

---

**Check current branch:**
```bash
git branch
```

**Expected:**
```
* main
```

Asterisk shows current branch.

---

**Check if branch is ahead/behind:**
```bash
git status
```

**When in sync:**
```
On branch main
Your branch is up to date with 'origin/main'.
nothing to commit, working tree clean
```

**When behind:**
```
On branch main
Your branch is behind 'origin/main' by 2 commits.
  (use "git pull" to update your local branch)
```

**When ahead:**
```
On branch feature/my-work
Your branch is ahead of 'origin/feature/my-work' by 1 commit.
  (use "git push" to publish your local commits)
```

---

## Multiple Branches Simultaneously

### Creating Multiple Branches

```bash
# Branch 1
git checkout main
git checkout -b feature/update-personas
# Work on personas
git add .
git commit -m "Updated personas"
git push -u origin feature/update-personas

# Branch 2
git checkout main
git checkout -b feature/add-research
# Work on research
git add .
git commit -m "Added research findings"
git push -u origin feature/add-research

# Branch 3
git checkout main
git checkout -b fix/broken-link
# Fix link
git add .
git commit -m "Fixed broken link"
git push -u origin fix/broken-link
```

### Result

**On GitHub:**
- 3 open branches
- Can create 3 separate PRs
- Review and merge independently
- No interference between branches

**This is how teams work on multiple features simultaneously.**

---

## Expected Git Log After Week 5

### Command

```bash
git log --oneline --graph
```

### Expected Output

```
* mno7890 Merge pull request #2 from yourusername/feature/improve-documentation
|\  
| * jkl3456 Added documentation improvements
|/  
* ghi9012 Merge pull request #1 from yourusername/feature/add-collaboration-guide
|\  
| * abc1234 Added collaboration guide examples
|/  
* xyz7890 Initial commit
```

**The graph shows:**
- Merge commits (the convergence points)
- Feature branch commits (the branches)
- Visual representation of workflow

---

## Troubleshooting Expected Scenarios

### Scenario: Can't Create PR

**Error:** "There isn't anything to compare"

**Cause:** No commits on feature branch, or branch is identical to main

**Solution:**
- Make sure you committed changes
- Verify you're on the feature branch
- Push the branch to GitHub

---

### Scenario: Merge Conflicts

**Status on PR:** "This branch has conflicts that must be resolved"

**Solution on your computer:**
```bash
git checkout feature/your-branch
git pull origin main
# Resolve conflicts in files
git add .
git commit -m "Resolved conflicts with main"
git push
```

**PR automatically updates with resolution.**

---

### Scenario: Can't Delete Branch

**Error:** "error: The branch 'feature/branch-name' is not fully merged"

**Cause:** Branch has commits not in main

**Solutions:**
- If you're sure you want to delete: `git branch -D feature/branch-name` (force delete)
- If you want to keep: merge the branch first

---

## Expected Behavior Checklist

After completing Week 5, this should all work:

- [ ] `git checkout -b` creates new branch
- [ ] `git branch` shows all local branches
- [ ] Commits on feature branch don't appear in main
- [ ] `git push` uploads feature branch to GitHub
- [ ] GitHub shows branch in branches dropdown
- [ ] Can create PR from branch to main
- [ ] PR shows commits and file changes
- [ ] Can review and comment on PR
- [ ] Merging PR integrates changes to main
- [ ] `git pull` on main gets merged changes
- [ ] Can delete branch locally with `git branch -d`
- [ ] Multiple branches can exist simultaneously
- [ ] Switching branches changes file contents

---

## Self-Check Questions

Can you answer these after Week 5?

**1. How do you create a new branch?**
Answer: `git checkout -b branch-name`

**2. How do you switch between branches?**
Answer: `git checkout branch-name`

**3. What happens to main when you commit on a branch?**
Answer: Main is unchanged - commits only go to the current branch

**4. How do you get branch changes into main?**
Answer: Create a pull request and merge it

**5. When should you delete a branch?**
Answer: After it's merged and you're done with it

**6. Can you have multiple feature branches?**
Answer: Yes, as many as you need

**7. What does the asterisk mean in `git branch` output?**
Answer: Shows which branch you're currently on

**8. How do you push a new branch to GitHub?**
Answer: `git push -u origin branch-name`

**If you can answer all these, Week 5 is complete!**

---

## Success Indicators

You know Week 5 worked if:

1. You've created multiple branches
2. Each branch shows different commits
3. You've created at least 2 PRs
4. You've merged PRs successfully
5. Main has merged changes from branches
6. You can switch between branches without hesitation
7. Deleted branches are gone but changes are in main
8. You understand the workflow conceptually
9. You can explain it to someone else
10. It feels natural, not confusing

---

## Next Week Preparation

**Week 6 will combine everything:**
- Set up complete UX project
- Use the full workflow
- Collaborate with teammates (if available)
- Practice on real work

**Make sure before Week 6:**
- Branches feel comfortable
- Pull requests make sense
- You've done the complete cycle 3+ times
- Ready to apply to real projects

---

**Congratulations!**

You now understand the professional collaborative Git workflow. This is exactly how developers work at companies like Google, Meta, Microsoft, and every modern tech organization.

You're ready for Week 6 - putting it all together.
