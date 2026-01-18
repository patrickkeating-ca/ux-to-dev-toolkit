# Collaboration Guide - Feature Branch Practice

## Purpose

This file helps you practice working on feature branches. You'll create branches, make changes, and merge them through pull requests.

---

## What Are Feature Branches?

**Feature branch = temporary branch for specific work**

**Common uses:**
- Adding a new feature
- Fixing a bug
- Updating documentation
- Redesigning a section
- Experimenting with ideas

**Key principle:** One branch per feature/task

---

## Branch Naming Guide

### Good Branch Names

**Pattern: type/brief-description**

**Types:**
- `feature/` - New features
- `fix/` - Bug fixes
- `docs/` - Documentation updates
- `redesign/` - Design changes
- `update/` - Content updates

**Examples:**
- `feature/add-user-personas`
- `fix/broken-navigation-link`
- `docs/update-research-findings`
- `redesign/improve-wireframes`
- `update/refresh-team-contacts`

### Bad Branch Names

**Avoid:**
- `test` - Too vague
- `my-branch` - Not descriptive
- `new-stuff` - Unclear what it does
- `patrick-work` - Use feature name, not person name
- `final-version` - Meaningless

**Rule:** Name should explain what the branch does

---

## Practice Exercise 1: Create Your First Feature

### Scenario

You need to add a "Best Practices" section to this document.

**Steps:**

1. **Create branch:**
   ```bash
   git checkout -b feature/add-best-practices
   ```

2. **Verify you're on the branch:**
   ```bash
   git branch
   ```
   Should show asterisk next to `feature/add-best-practices`

3. **Make changes:**
   Add a new section below with best practices for UX collaboration

4. **Commit:**
   ```bash
   git add .
   git commit -m "Added best practices section for UX teams"
   ```

5. **Push branch:**
   ```bash
   git push -u origin feature/add-best-practices
   ```

6. **Create PR on GitHub**

7. **Merge PR**

8. **Clean up:**
   ```bash
   git checkout main
   git pull
   git branch -d feature/add-best-practices
   ```

---

## Practice Exercise 2: Multiple Branches

### Scenario

You're working on two things simultaneously:
- Updating team member list
- Adding project timeline

**Instead of mixing them, use separate branches.**

**Branch 1:**
```bash
git checkout main
git checkout -b update/team-members
# Add team members section
git add .
git commit -m "Updated team member list"
git push -u origin update/team-members
# Create PR, but don't merge yet
```

**Branch 2:**
```bash
git checkout main
git checkout -b feature/project-timeline
# Add timeline section
git add .
git commit -m "Added project timeline"
git push -u origin feature/project-timeline
# Create PR
```

**Now you have two PRs open simultaneously.**

**Merge them one at a time:**
1. Review and merge first PR
2. Update local main: `git checkout main && git pull`
3. Review and merge second PR
4. Clean up both branches

**This is how teams work on multiple features at once.**

---

## Understanding Branch Isolation

### Experiment Safely

**Branches let you try things without risk:**

```bash
git checkout -b experiment/new-layout
# Try radical redesign
# If it works: merge it
# If it doesn't: delete branch, no harm done
```

**Main branch stays safe the whole time.**

---

## Working with Branches Daily

### Morning Routine

**Start of day:**
```bash
# Get latest from team
git checkout main
git pull

# Start new work
git checkout -b feature/todays-task
```

### During Work

**Make commits as you go:**
```bash
git add .
git commit -m "Progress on feature"
# Continue working
git add .
git commit -m "Completed first part"
# More work
git add .
git commit -m "Feature complete"
```

### End of Day

**Push for backup:**
```bash
git push -u origin feature/todays-task
```

**Even if not done, your work is backed up on GitHub.**

**Tomorrow:**
```bash
git checkout feature/todays-task
# Continue where you left off
```

---

## Branch Lifecycle

### Complete Flow

1. **Create** - Branch from main
2. **Work** - Make commits on branch
3. **Push** - Backup to GitHub
4. **PR** - Request to merge
5. **Review** - Team feedback
6. **Update** - Address feedback
7. **Merge** - Integrate to main
8. **Delete** - Clean up branch

**Most branches live 1-3 days.**

Some longer for complex features, some shorter for quick fixes.

---

## Switching Between Branches

### The Rules

**Before switching:**
1. Commit your changes OR
2. Stash them (advanced) OR
3. Discard them

**You can't switch with uncommitted changes.**

**Example:**
```bash
git checkout feature/branch-a
# Make changes
git add .
git commit -m "Checkpoint"
# Now you can switch
git checkout feature/branch-b
# Work on something else
git checkout feature/branch-a
# Back to first task
```

---

## Common Scenarios

### Scenario 1: Wrong Branch

**Oops, you committed to main instead of feature branch:**

```bash
# Don't panic
# Create branch from current state
git checkout -b feature/the-work-i-did

# Reset main to before your commits
git checkout main
git reset --hard origin/main

# Your work is safe on the feature branch
```

---

### Scenario 2: Branch is Out of Date

**Your feature branch is old, main has new commits:**

```bash
git checkout feature/old-branch
git pull origin main
# Resolve any conflicts
git add .
git commit -m "Merged latest main"
git push
```

**Now your branch has latest from main plus your changes.**

---

### Scenario 3: Need to Switch Mid-Work

**You're working but need to switch to urgent task:**

**Option 1 - Commit work in progress:**
```bash
git add .
git commit -m "WIP: Partial progress on feature"
git checkout main
git checkout -b fix/urgent-fix
# Do urgent work
# Come back later
git checkout feature/original-work
```

**Option 2 - Stash (advanced):**
```bash
git stash
git checkout main
git checkout -b fix/urgent-fix
# Do urgent work
git checkout feature/original-work
git stash pop
```

---

## Pull Request Tips

### Small PRs Are Better

**Good PR:**
- 1-3 files changed
- 50-200 lines of code
- Single clear purpose
- Easy to review in 10 minutes

**Bad PR:**
- 20 files changed
- 1000+ lines
- Multiple unrelated changes
- Takes hours to review

**Break big work into small PRs.**

---

### Writing PR Descriptions

**Template:**

```markdown
## What Changed
Brief summary of what you did.

## Why
Explain the reasoning or context.

## Testing Done
How you verified it works.

## Screenshots
[If visual changes - especially for UX work]

## Questions
Anything you're unsure about or want feedback on.
```

**Good descriptions get faster reviews.**

---

## Review Etiquette

### As PR Author

**Do:**
- Respond to all comments
- Explain your decisions
- Make requested changes promptly
- Thank reviewers
- Keep PR updated

**Don't:**
- Get defensive about feedback
- Ignore comments
- Argue unnecessarily
- Let PR sit for days

---

### As Reviewer

**Do:**
- Be constructive
- Suggest alternatives
- Explain reasoning
- Approve when satisfied
- Review promptly

**Don't:**
- Just say "looks bad" without explanation
- Nitpick trivial things
- Block without good reason
- Delay reviews unnecessarily

---

## Branch Protection

### On Real Projects

**Teams often protect main branch:**
- Can't push directly to main
- Must use pull requests
- Requires approval before merge
- Automated tests must pass

**This prevents accidents and ensures quality.**

**In your practice repos:**
- You can push to main
- But practice using PRs anyway
- Builds good habits

---

## Merging Strategies

### Fast-Forward Merge (Simple)

**When:**
- No new commits on main since branch created
- Clean, linear history

**What it does:**
- Moves main pointer forward
- No merge commit
- Simple history

---

### Merge Commit (Standard)

**When:**
- Main has new commits
- Merging a feature branch

**What it does:**
- Creates a merge commit
- Preserves branch history
- Shows when feature was integrated

**This is what happens with GitHub PRs by default.**

---

### Squash and Merge (Clean)

**What it does:**
- Combines all branch commits into one
- Cleaner main history
- Loses individual commit history

**Good for:**
- Many small "WIP" commits on branch
- Want clean main history
- Feature makes sense as single commit

**GitHub PR offers this option.**

---

## Troubleshooting

### "Can't switch branches - uncommitted changes"

**Solution:**
```bash
# Commit them
git add .
git commit -m "Checkpoint before switching"

# Or discard them
git restore .

# Then switch
git checkout other-branch
```

---

### "Branch diverged from main"

**Solution:**
```bash
git checkout your-branch
git pull origin main
# Resolve conflicts
git add .
git commit -m "Merged main"
git push
```

---

### "Deleted branch but need it back"

**If you just deleted it:**
```bash
git reflog
# Find the commit ID where branch was
git checkout -b branch-name commit-id
```

**If you deleted on GitHub too:**
- Might be gone
- Lesson: Don't delete until sure you're done

---

## Completion Checklist

Practice and check off:

- [ ] Created feature branch
- [ ] Made commits on feature branch
- [ ] Pushed feature branch to GitHub
- [ ] Created pull request
- [ ] Added PR description
- [ ] Reviewed own PR
- [ ] Merged PR
- [ ] Deleted branch locally
- [ ] Deleted branch on GitHub
- [ ] Pulled merged changes to main

**Advanced:**
- [ ] Worked on 2 branches simultaneously
- [ ] Switched between branches
- [ ] Merged main into feature branch
- [ ] Resolved conflict in a PR

---

## Real-World Examples

### UX Team Scenarios

**Persona update:**
```bash
git checkout -b update/personas-q1-2025
# Update persona documents
# Commit, push, PR, merge
```

**Research findings:**
```bash
git checkout -b docs/user-research-findings
# Add research documents
# Commit, push, PR, merge
```

**Wireframe revision:**
```bash
git checkout -b redesign/checkout-flow
# Update wireframes
# Commit, push, PR, merge
```

**Each task gets its own branch.**

---

## Best Practices Summary

1. **Branch from main** - Always start from latest
2. **One feature per branch** - Keep focused
3. **Commit often** - Save progress
4. **Push daily** - Backup work
5. **Small PRs** - Easier to review
6. **Good descriptions** - Context for reviewers
7. **Respond to feedback** - Be collaborative
8. **Merge when ready** - Don't delay
9. **Delete after merge** - Keep clean
10. **Pull main regularly** - Stay current

---

## Resources

**Commands reference:**
```bash
git branch                     # List branches
git branch branch-name         # Create branch
git checkout branch-name       # Switch to branch
git checkout -b branch-name    # Create and switch
git push -u origin branch-name # Push new branch
git branch -d branch-name      # Delete local branch
git push origin --delete name  # Delete remote branch
```

**GitHub PR workflow:**
1. Push branch
2. Go to repository on GitHub
3. "Pull requests" → "New pull request"
4. Select branches
5. Create PR
6. Review and merge

---

## Reflection

After completing these exercises:

**What I learned about branches:**
[Add notes]

**What surprised me:**
[Add notes]

**What I still find confusing:**
[Add questions]

**How I'll use this in real work:**
[Add plans]

---

## Next Steps

**After mastering branches:**
1. Use them on real projects
2. Teach a teammate the workflow
3. Practice daily for 2 weeks
4. Contribute to team repository
5. Help review others' PRs

**The goal:** Branches become second nature.

---

**Remember:** Branches are freedom. They let you experiment, work independently, and collaborate cleanly. Use them liberally!
