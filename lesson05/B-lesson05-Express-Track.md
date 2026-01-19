# Lesson 5 Express: Collaboration Workflow
## 15-Minute Quick Start

Learn branches and pull requests - how teams actually work together.

---

## Goal

Understand the professional workflow: branches for features, pull requests for review. Minimal version.

**Time commitment:** 15-20 minutes

**Note:** This is how developers collaborate. It feels weird at first but becomes essential.

---

## Part 1: Why Branches? (2 minutes)

**Without branches:**
- Everyone works on `main`
- Changes mix together
- Hard to separate work
- Risky to experiment

**With branches:**
- `main` stays stable
- Each feature gets its own branch
- Work independently
- Merge when ready

**Think:** Branches are parallel timelines. Main is the official timeline.

---

## Part 2: The Only 3 Branch Commands You Need (5 minutes)

### Create and Switch to Branch

```bash
git checkout -b feature/my-feature
```

Creates new branch AND switches to it.

### Switch Between Branches

```bash
git checkout main
git checkout feature/my-feature
```

Jump between branches anytime.

### Delete a Branch

```bash
git branch -d feature/my-feature
```

After merging, clean up old branches.

**That's it for branches.**

---

## Part 3: Quick Branch Practice (5 minutes)

**Navigate to your test project:**
```bash
cd ~/Desktop/test-project
git checkout main
```

**Create feature branch:**
```bash
git checkout -b feature/add-description
```

**Make a change:**
```bash
echo "## Description" >> notes.md
echo "This is a test project for learning Git" >> notes.md
```

**Commit on the branch:**
```bash
git add .
git commit -m "Added description section"
```

**Push the branch to GitHub:**
```bash
git push -u origin feature/add-description
```

**Switch back to main:**
```bash
git checkout main
```

**Check the file:**
```bash
cat notes.md
```

**Your changes aren't there!** They're only on the feature branch.

**Switch back to feature branch:**
```bash
git checkout feature/add-description
cat notes.md
```

**Changes are back!**

**This is branch isolation.**

---

## Part 4: Pull Request on GitHub (5 minutes)

### Create Pull Request

**On GitHub:**
1. Go to your repository
2. You should see a yellow banner: "feature/add-description had recent pushes"
3. Click "Compare & pull request"

**Or manually:**
1. Click "Pull requests" tab
2. Click "New pull request"
3. Base: main
4. Compare: feature/add-description
5. Click "Create pull request"

**Fill out:**
- Title: "Add description section"
- Description: "Added a description to explain what this project is"
- Click "Create pull request"

---

### Review and Merge

**On the PR page:**
1. Go to "Files changed" tab
2. See what's different (green = added lines)
3. Click "Review changes" button
4. Add comment: "Looks good!"
5. Select "Approve"
6. Click "Submit review"

**Back on Conversation tab:**
1. Click "Merge pull request"
2. Click "Confirm merge"
3. Click "Delete branch" (cleans up)

**Your feature is now in main!**

---

### Update Local Main

**On your computer:**
```bash
git checkout main
git pull
```

**Check the file:**
```bash
cat notes.md
```

**The changes are now in main!**

**Delete local feature branch:**
```bash
git branch -d feature/add-description
```

**You just completed the professional workflow.**

---

## The Professional Cycle

```
1. git checkout -b feature/my-work (create branch)
2. Make changes, commit them
3. git push -u origin feature/my-work (push branch)
4. Create pull request on GitHub
5. Review, approve, merge
6. git checkout main && git pull (update local)
7. Delete feature branch
8. Repeat for next feature
```

**This is how every professional team works.**

---

## What You're Skipping

The full Lesson 5 lesson includes:
- Multiple branches simultaneously
- Branch naming conventions
- Resolving conflicts in PRs
- Pull request best practices
- Code review etiquette
- Advanced collaboration patterns

**Learn these when working with a team.**

---

## When to Return to Full Lesson 5

Return to comprehensive version if:
- You're collaborating with teammates
- PRs have conflicts
- You need branch naming standards
- You want code review best practices

**For now, you understand the workflow.**

---

## Common Confusion

**"Why not just commit to main?"**
- Professional teams protect main
- Requires review before merge
- Prevents broken code in main
- Allows parallel work

**"When do I create a branch?"**
- For every feature or change
- One branch per task
- Small, focused branches

**"Can I have multiple branches?"**
- Yes! As many as you need
- Work on multiple things
- Switch between them freely

---

## AI Prompt for Custom Learning

Ask ChatGPT/Claude/Copilot:

```
I'm learning Git branches and pull requests for team collaboration. 
I have 20 minutes. Explain the minimum I need to know about creating 
branches, pushing them to GitHub, and making pull requests. Keep it 
simple and focused on the essential workflow.
```

---

## Cheat Sheet

```bash
# Create and switch to branch
git checkout -b feature/name

# Switch branches
git checkout branch-name

# Push branch to GitHub
git push -u origin branch-name

# After merging on GitHub:
git checkout main
git pull
git branch -d feature/name
```

**On GitHub: Pull request → Review → Merge → Delete branch**

---

## Critical Understanding

**Before moving to Lesson 6, make sure you can:**
- Create a feature branch
- Commit to that branch
- Push branch to GitHub
- Create a pull request
- Merge the pull request
- Update local main

**If you've done this once successfully, you understand the workflow.**

---

## Next Step

Lesson 6 Express will put everything together into a real UX project setup.

**Time saved: ~60-75 minutes**

**Important:** Branches are the key to professional Git usage. Practice this workflow 2-3 times to build muscle memory.
