# GitHub Collaboration Practice

## Purpose

Practice the push/pull workflow with GitHub. You'll make changes locally and on GitHub.

---

## Understanding Push and Pull

**Push:** Send your local commits to GitHub
**Pull:** Get commits from GitHub to your computer

---

## Practice Exercise 1: Local to GitHub

**Edit this file and add your information:**

**My Name:** [Your name here]
**Today's Date:** [Date]
**What I Learned This Week:** [Your notes]

**Commit and push:**
```bash
git add 03-week4-practice-collaboration.md
git commit -m "Added my personal information"
git push
```

**Verify:** Go to your repository on GitHub and confirm your changes appear.

---

## Practice Exercise 2: GitHub to Local

**On GitHub:**
1. Navigate to this file in your repository
2. Click the pencil icon to edit
3. Add a note below in the "GitHub Notes" section
4. Commit with message: "Added note from GitHub"

**On your computer:**
```bash
git pull
```

**Verify:** Open this file in VS Code - your GitHub edit should appear!

---

## GitHub Notes Section

[Add notes here when editing on GitHub]

---

## Practice Exercise 3: Multiple Push/Pull Cycles

**Round 1:** Add a bullet point below, commit, and push
**Round 2:** Add another bullet point, commit, and push
**Round 3:** Add a third bullet point, commit, and push

**My Practice Notes:**
- [Add your first point]
- [Add your second point]
- [Add your third point]

**Verify your work:**
```bash
git log --oneline
```

You should see three new commits!

---

## Daily Workflow Reminder

**Morning:** `git pull` (get latest)
**During work:** Make changes, commit often
**End of day:** `git push` (backup your work)

---

## Completion Checklist

- [ ] Made changes locally and pushed to GitHub
- [ ] Made changes on GitHub and pulled to local
- [ ] Completed 3+ push/pull cycles
- [ ] Viewed commits on GitHub
- [ ] Feel comfortable with the workflow

---

## Notes Section

**What I learned:**
[Add reflections]

**Questions I have:**
[Add questions]
