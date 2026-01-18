# Feature Branch Practice

## Purpose

Practice working on feature branches - the professional workflow for team collaboration.

---

## What Are Feature Branches?

**Feature branch = separate workspace for specific work**

**Why use them:**
- Main branch stays stable
- Work independently
- Easy to review before merging
- Can experiment safely

**Key principle:** One branch per feature or task

---

## Branch Naming

**Good pattern:** `type/brief-description`

**Examples:**
- `feature/add-personas`
- `fix/broken-link`
- `docs/update-research`

**Avoid:**
- `test`, `my-branch`, `new-stuff` (too vague)

---

## Practice Exercise 1: Create Your First Feature

**Task:** Add a "My Notes" section to this document using a feature branch

**Steps:**

1. **Create and switch to branch:**
   ```bash
   git checkout -b feature/add-notes
   ```

2. **Make your change:** Add your notes in the section at the bottom of this file

3. **Commit:**
   ```bash
   git add .
   git commit -m "Added personal notes section"
   ```

4. **Push branch to GitHub:**
   ```bash
   git push -u origin feature/add-notes
   ```

5. **On GitHub:**
   - Go to your repository
   - Click "Compare & pull request"
   - Create pull request
   - Review and merge
   - Delete branch on GitHub

6. **Back on your computer:**
   ```bash
   git checkout main
   git pull
   git branch -d feature/add-notes
   ```

**Success!** You completed the full branch workflow.

---

## Practice Exercise 2: Work on Multiple Branches

**Scenario:** You need to work on two separate tasks

**Task 1 - Create first branch:**
```bash
git checkout main
git checkout -b docs/update-team
```

Add a team member to the "Team Members" section below, then:
```bash
git add .
git commit -m "Added team member"
git push -u origin docs/update-team
```

Create PR on GitHub (but don't merge yet!)

**Task 2 - Create second branch:**
```bash
git checkout main
git checkout -b feature/add-timeline
```

Add a project date to the "Project Timeline" section below, then:
```bash
git add .
git commit -m "Added timeline entry"
git push -u origin feature/add-timeline
```

Create PR on GitHub

**Now merge both PRs one at a time on GitHub**

**Clean up locally:**
```bash
git checkout main
git pull
git branch -d docs/update-team
git branch -d feature/add-timeline
```

**This is how professionals work on multiple tasks!**

---

## The Complete Workflow

**Every time you start new work:**

1. `git checkout main` - Switch to main
2. `git pull` - Get latest changes
3. `git checkout -b type/description` - Create feature branch
4. Make changes, commit
5. `git push -u origin branch-name` - Push to GitHub
6. Create pull request on GitHub
7. Review, merge, delete branch
8. `git checkout main && git pull` - Update main
9. `git branch -d branch-name` - Clean up local branch

---

## Team Members Section

**Current team:**
- [Add team members here as part of Exercise 2]

---

## Project Timeline Section

**Key dates:**
- [Add project dates here as part of Exercise 2]

---

## My Notes Section

[Add your personal notes here as part of Exercise 1]

---

## Completion Checklist

- [ ] Created a feature branch
- [ ] Made changes on the branch
- [ ] Committed changes
- [ ] Pushed branch to GitHub
- [ ] Created a pull request
- [ ] Merged the pull request
- [ ] Deleted remote branch
- [ ] Updated local main
- [ ] Deleted local branch
- [ ] Worked on 2+ branches simultaneously
- [ ] Understand the complete workflow

---

## Quick Reference

```bash
# Create and switch to branch
git checkout -b feature/name

# Switch between branches
git checkout branch-name
git checkout main

# Push new branch
git push -u origin branch-name

# After merging PR on GitHub:
git checkout main
git pull
git branch -d feature/name
```

---

## When You're Stuck

**Can't switch branches?**
- Commit your changes first
- Or stash them: `git stash`

**Don't see your branch on GitHub?**
- Did you push? `git push -u origin branch-name`

**Merge conflict in PR?**
- See Week 4 explore deeper for conflict resolution

---

## What's Next

After mastering branches, you're ready for real team collaboration! Week 6 brings it all together into a complete UX project setup.

**Practice the workflow 3-5 times** until it feels natural.
