# Prerequisites Check - Week 5
## Collaboration Workflow

### Before Starting This Lesson

Week 5 teaches you how teams actually use Git and GitHub for collaborative work. You'll learn branches, pull requests, and code review - the professional workflow.

---

## Week 1-4 Completion Check

You should have already:

- [ ] Completed Week 1 (Terminal, markdown)
- [ ] Completed Week 2 (VS Code, shortcuts)
- [ ] Completed Week 3 (Local Git)
- [ ] Completed Week 4 (GitHub, push/pull)
- [ ] Successfully pushed commits to GitHub
- [ ] Successfully pulled changes from GitHub
- [ ] Resolved at least one merge conflict
- [ ] Understand remote vs. local repositories

**If you haven't done Weeks 1-4:** Go back and complete them first. Week 5 assumes you're comfortable with push/pull and basic Git.

---

## Critical Week 4 Skills

### You Must Be Comfortable With:

**GitHub operations:**
```bash
git push       # Upload commits
git pull       # Download commits
git clone      # Copy repository
git remote -v  # Check connections
```

**Quick test - can you do these without hesitation?**

1. Make a change to a file
2. Commit it locally
3. Push to GitHub
4. Verify it appears on GitHub
5. Make a change on GitHub
6. Pull it to your computer

**If those feel natural:** You're ready for Week 5.

**If those feel confusing:** Review Week 4 before continuing. Week 5 builds directly on push/pull skills.

---

## Required Setup

### 1. Active GitHub Repository

**You need:**
- A repository on GitHub (from Week 4)
- Ability to push and pull from it
- Personal access token working

**Verify:**
```bash
cd ~/Desktop/week3-practice
git push
```

**Should work without errors.**

**If authentication fails:** Review Week 4 token setup.

---

### 2. Understanding of Main Branch

**Check your current branch:**
```bash
git branch
```

**You should see:**
```
* main
```

The asterisk shows you're on the `main` branch.

**This is important because Week 5 teaches you to create additional branches.**

---

### 3. Create Week 5 Practice Folder

```bash
cd ~/Desktop
mkdir week5-practice
cd week5-practice
git init
```

**Set up remote connection:**

1. Create new repository on GitHub named `week5-collaboration`
2. Make it private
3. Copy the repository URL
4. Connect it:

```bash
git remote add origin https://github.com/yourusername/week5-collaboration.git
```

**Verify:**
```bash
git remote -v
```

---

## What You'll Learn This Week

Week 5 introduces **professional collaboration workflow:**

**Topics:**
- Creating and switching branches
- Working on features independently
- Creating pull requests (PRs)
- Reviewing others' work
- Merging pull requests
- Collaborative patterns

**New commands:**
- `git branch` - List, create branches
- `git checkout` - Switch branches
- `git merge` - Combine branches
- Pull Request - GitHub web interface

**Time needed:** 25-30 minutes

---

## Understanding Branches

### The Mental Model

**Without branches (what you've done so far):**
- Everyone works on `main`
- Changes mix together
- Hard to work independently
- Risky to experiment

**With branches:**
- `main` stays stable
- Each feature gets its own branch
- Work independently without conflicts
- Easy to experiment safely
- Merge when ready

**Think of it like parallel universes:**
- Main branch = the official reality
- Feature branch = experimental timeline
- When experiment succeeds, merge it into reality

---

## Why Teams Use Branches

**Scenario without branches:**
- You're redesigning personas
- Teammate is updating research findings
- Both editing same files
- Constant conflicts
- Can't work independently

**Scenario with branches:**
- You create `feature/redesign-personas` branch
- Teammate creates `feature/update-research` branch
- Work independently without conflicts
- When done, merge one at a time
- Main branch only gets finished work

**This is how professional teams work.**

---

## Files You Need

For this lesson, download these files to your `week5-practice` folder:

1. `03-week5-practice-feature.md` - File for feature branch practice
2. `04-week5-practice-pr-template.md` - Pull request description template
3. `05-week5-solution-branches.md` - Expected branch workflow

**How to get them:**
- Download from lesson folder
- Move them to `~/Desktop/week5-practice`

**Verify they're there:**
```bash
cd ~/Desktop/week5-practice
ls
```

---

## Pull Request Basics

### What is a Pull Request?

**Pull Request (PR) = Request to merge your branch into main**

**The flow:**
1. Create a branch
2. Make changes on that branch
3. Push the branch to GitHub
4. Open a pull request on GitHub
5. Team reviews your changes
6. Discussion happens
7. Make requested changes
8. PR gets approved
9. Merge into main

**This is how code review works in professional teams.**

---

## Common Concerns

**"Will I break main by creating branches?"**
- No. Branches are separate
- Main is untouched until you merge
- You can delete branches without affecting main

**"What if my branch gets out of date?"**
- Pull latest main
- Merge main into your branch
- Resolve conflicts
- Continue working

**"Do I need permission to create branches?"**
- On your own repos: No
- On team repos: Usually yes, you can create branches
- Some repos restrict who can merge to main

**"Can I have multiple branches?"**
- Yes! As many as you want
- Work on multiple features simultaneously
- Switch between them anytime

---

## Checklist Before Starting

- [ ] Completed Weeks 1-4
- [ ] Push/pull to GitHub feels natural
- [ ] Resolved at least one merge conflict successfully
- [ ] Understand what a commit is
- [ ] Have working GitHub repository from Week 4
- [ ] Created `week5-practice` folder and initialized Git
- [ ] Connected to new GitHub repository
- [ ] Downloaded practice files
- [ ] Understand the concept of branches (separate timelines)

**All checked?**

Proceed to `02-week5-instructions.md`

---

## If You're Not Ready

**Week 4 still feels uncertain:**
- Practice push/pull for another week
- Make 10+ commits and push them
- Try pulling from GitHub daily
- Get comfortable before adding branches

**Merge conflicts still scary:**
- Resolve 2-3 more practice conflicts
- Use VS Code's visual tools
- Get confident before Week 5

**Don't have a working GitHub repository:**
- Go back to Week 4
- Complete the setup
- Verify you can push/pull successfully

**Not sure what branches are for:**
- Read the "Understanding Branches" section above
- Think: separate workstreams that merge later
- The lesson will make it concrete

---

## Time Expectations

**If Week 4 is solid:** 25-30 minutes for Week 5 lesson

**If Week 4 is shaky:** Review Week 4 first (30 min), then 30-40 min for Week 5

**Pull Request creation:** 5 minutes

**Branch workflow practice:** 15-20 minutes

---

## Getting Help

**Resources:**
- Week 4 materials (push/pull review)
- GitHub pull request documentation: [docs.github.com/pull-requests](https://docs.github.com/pull-requests)
- Team channel: [your channel]
- Office hours: [day/time]

**Branch questions are common.** Don't struggle - ask for help understanding the workflow.

---

## What This Unlocks

After Week 5, you'll be able to:
- Work on features without affecting main
- Submit work for team review
- Review others' pull requests
- Collaborate professionally
- Use the same workflow as developers
- Contribute to any GitHub project

**This is the complete collaborative workflow.**

---

## Vocabulary Preview

**Terms you'll learn this week:**

- **Branch:** Separate line of development
- **Feature branch:** Branch for specific feature/change
- **Pull Request (PR):** Request to merge your branch
- **Code review:** Team reviews your PR
- **Approve:** PR is good to merge
- **Request changes:** PR needs fixes before merge
- **Merge:** Combine branch into main
- **Delete branch:** Remove branch after merging

**Don't memorize these.** The lesson will make them clear through practice.

---

## The Professional Workflow

**What you'll learn this week is how real teams work:**

1. Developer creates feature branch
2. Works on feature independently
3. Opens pull request when ready
4. Team reviews code
5. Discussion happens in PR
6. Changes are made if requested
7. PR gets approved
8. Merged into main
9. Branch is deleted
10. Repeat for next feature

**This is standard in tech companies worldwide.**

---

## Encouragement

**Week 5 is the culmination of everything you've learned.**

- Week 1: Terminal basics
- Week 2: VS Code setup
- Week 3: Git locally
- Week 4: GitHub remotely
- **Week 5: Professional collaboration**

**The concepts build on each other.**

If Weeks 1-4 feel solid, Week 5 will click. You're learning the workflow that powers modern software development.

**You're almost there.**

---

## Ready?

Once you've completed this checklist and set up your Week 5 practice repository, proceed to `02-week5-instructions.md` to learn professional Git collaboration.

You're about to learn how teams actually work together.

Let's go.
