# Lesson 5: Collaboration Workflow
## 5-Minute Hands-On Lesson

### What You'll Learn

By the end of this lesson, you'll:
- Create and switch between branches
- Work on features independently
- Create pull requests on GitHub
- Review and merge pull requests
- Understand professional collaboration workflow
- Delete branches after merging

**Time needed:** 25-30 minutes

**Important:** This is how professional teams collaborate. You're learning industry-standard workflow.

---

## The Core Workflow

**Professional teams don't work directly on main:**

```
main branch (stable, production-ready)
  ↓
feature branch (your work in progress)
  ↓
pull request (request to merge)
  ↓
code review (team feedback)
  ↓
merge to main (feature is live)
  ↓
delete feature branch (cleanup)
```

**This lesson you'll practice this complete cycle.**

---

## Part 1: Understanding Branches (2 minutes)

### What You've Been Doing

**So far:**
- All work happens on `main` branch
- Every commit goes directly to main
- Like everyone editing the same Google Doc simultaneously

**Check current branch:**
```bash
cd ~/Desktop/lesson05-practice
git branch
```

**You should see:**
```
* main
```

The asterisk shows you're currently on main.

---

### Why Branches Matter

**Imagine this scenario:**

You're redesigning the persona template. Halfway through, your manager asks for urgent fix to research doc.

**Without branches:**
- Half-finished persona changes are in the way
- Have to finish or undo to make the fix
- Or create messy "WIP - don't use" commits

**With branches:**
- Create `feature/redesign-personas` for persona work
- Create `hotfix/research-doc` for urgent fix
- Work independently
- Merge the fix immediately
- Finish personas later at your pace

**Branches let you multitask cleanly.**

---

## Part 2: Create Your First Branch (3 minutes)

### The Scenario

You're going to add a new feature: a collaboration guide section.

**Instead of editing main, create a feature branch:**

```bash
git checkout -b feature/add-collaboration-guide
```

**Breakdown:**
- `git checkout` = switch branches
- `-b` = create new branch
- `feature/add-collaboration-guide` = branch name

**You should see:**
```
Switched to a new branch 'feature/add-collaboration-guide'
```

**Verify:**
```bash
git branch
```

**You should see:**
```
* feature/add-collaboration-guide
  main
```

The asterisk moved! You're now on the feature branch.

**What just happened:**
- Created new branch from main
- Switched to that branch
- All changes now happen on this branch
- Main is untouched

---

### Make Changes on the Branch

**Add practice files to your repository:**

```bash
git add D-lesson05-practice-feature.md F-lesson05-solution-branches.md
git commit -m "Added collaboration practice files"
```

**Edit one of the files:**
```bash
code D-lesson05-practice-feature.md
```

Make any change (add text, modify sections). Save it.

**Commit the change:**
```bash
git add .
git commit -m "Updated collaboration guide with examples"
```

**Check your history:**
```bash
git log --oneline
```

You should see your new commits.

**Now check main:**
```bash
git checkout main
git log --oneline
```

**The commits aren't there!** They only exist on the feature branch.

**Switch back to feature branch:**
```bash
git checkout feature/add-collaboration-guide
git log --oneline
```

**The commits are back!**

**This is the power of branches:** Isolated work that doesn't affect main.

---

## Part 3: Push Branch to GitHub (2 minutes)

### Share Your Branch

**Push the feature branch to GitHub:**
```bash
git push -u origin feature/add-collaboration-guide
```

**Expected output:**
```
Enumerating objects: 8, done.
...
To https://github.com/yourusername/lesson05-collaboration.git
 * [new branch]      feature/add-collaboration-guide -> feature/add-collaboration-guide
Branch 'feature/add-collaboration-guide' set up to track remote branch 'feature/add-collaboration-guide' from 'origin'.
```

**What happened:**
- Your feature branch is now on GitHub
- Others can see it
- But it's separate from main
- Main is still unchanged

**Verify on GitHub:**
1. Go to your repository on GitHub
2. Click the "branches" dropdown (says "main" by default)
3. You should see your feature branch listed!

---

## Part 4: Create a Pull Request (5 minutes)

### What is a Pull Request?

**Pull Request (PR) = "Hey team, I'm done with this feature. Please review and merge it to main."**

**It's not actually about "pulling" - it's requesting permission to merge.**

### Create the PR

**On GitHub:**

1. Go to your repository
2. Click "Pull requests" tab
3. Click green "New pull request" button

**Configure the PR:**

**Base:** `main` (what you're merging INTO)
**Compare:** `feature/add-collaboration-guide` (what you're merging FROM)

You should see:
- "Able to merge" (no conflicts)
- List of commits
- Files changed

**Click "Create pull request"**

**Fill out the PR form:**

**Title:** "Add collaboration guide section"

**Description:** Use this template:
```markdown
## What Changed
Added collaboration guide with examples and best practices.

## Why
Helps team understand how to work together using branches and PRs.

## Testing
- Reviewed markdown formatting
- Verified all links work
- Checked for typos

## Screenshots
[If applicable - for UX work, often include design screenshots]
```

**Click "Create pull request"**

**Your PR is now open!**

---

### What You're Looking At

**On the PR page, you see:**

- **Conversation tab:** Discussion, comments, approval
- **Commits tab:** All commits in this PR
- **Files changed tab:** Exactly what changed (like git diff)
- **Checks tab:** Automated tests (if configured)

**Bottom of page shows:**
- Merge button (to merge the PR)
- Close button (to cancel without merging)
- Comment box (for discussion)

---

## Part 5: Review Process (3 minutes)

### Acting as Reviewer

**For practice, review your own PR:**

1. Go to "Files changed" tab
2. Hover over a line of code
3. Click the blue + icon
4. Add a comment: "This section looks good!"
5. Click "Add single comment"

**Leave a review:**

1. Click green "Review changes" button (top right)
2. Add comment: "Looks great, approving!"
3. Select "Approve"
4. Click "Submit review"

**This is what code review looks like.**

In real teams:
- Teammates review your PRs
- They suggest changes
- You discuss in comments
- You make requested changes
- They approve when satisfied

---

### Requesting Changes (Optional Practice)

**To practice the full cycle:**

1. Switch to "Request changes" instead of "Approve"
2. Add comment: "Can you add more examples?"
3. Submit review

**Now you need to address the feedback:**

**On your computer:**
```bash
# Make sure you're on the feature branch
git checkout feature/add-collaboration-guide

# Edit the file
code D-lesson05-practice-feature.md
# Add more examples

# Commit the change
git add .
git commit -m "Added more examples per review feedback"

# Push the update
git push
```

**Check GitHub:**
- Go back to your PR
- The new commit appears automatically!
- PR updates in real-time

**This is the review cycle:**
- Open PR
- Get feedback
- Make changes
- Push updates
- Get approval
- Merge

---

## Part 6: Merge the Pull Request (2 minutes)

### Completing the Cycle

**On GitHub, on your PR page:**

1. Make sure status is "Approved" (from your review)
2. Click green "Merge pull request" button
3. Confirm by clicking "Confirm merge"

**You should see:**
```
Pull request successfully merged and closed
```

**What just happened:**
- Your feature branch merged into main
- All commits are now in main
- Main has the new feature
- PR is closed

**Optional but recommended:**
Click "Delete branch" button that appears

**This cleans up the feature branch since it's no longer needed.**

---

### Verify on Your Computer

**Switch to main and pull:**
```bash
git checkout main
git pull
```

**You should see:**
```
Updating abc123..def456
Fast-forward
 D-lesson05-practice-feature.md | 10 ++++++++++
 1 file changed, 10 insertions(+)
```

**Check your files:**
The changes from your feature branch are now in main!

**Check history:**
```bash
git log --oneline
```

All the commits from the PR are now in main's history.

**The feature is live!**

---

## Part 7: Clean Up Branches (2 minutes)

### Delete Local Branch

**List branches:**
```bash
git branch
```

You might see:
```
  feature/add-collaboration-guide
* main
```

**Delete the feature branch locally:**
```bash
git branch -d feature/add-collaboration-guide
```

**You should see:**
```
Deleted branch feature/add-collaboration-guide (was def456).
```

**Why delete?**
- Branch served its purpose
- Keeps branch list clean
- Prevents confusion
- Can always create new branches

**Verify:**
```bash
git branch
```

Should only show `main` now.

---

## Part 8: Practice the Full Cycle (10 minutes)

### Do It Again From Start to Finish

**Create a new feature:**

1. **Create branch:**
   ```bash
   git checkout -b feature/improve-documentation
   ```

2. **Make changes:**
   - Edit any file
   - Or create a new file
   ```bash
   touch new-feature.md
   echo "# New Feature" > new-feature.md
   ```

3. **Commit:**
   ```bash
   git add .
   git commit -m "Improved documentation structure"
   ```

4. **Push branch:**
   ```bash
   git push -u origin feature/improve-documentation
   ```

5. **Create PR on GitHub:**
   - Go to repository
   - Click "Pull requests"
   - Click "New pull request"
   - Base: main, Compare: feature/improve-documentation
   - Create pull request

6. **Review (self or ask teammate):**
   - Files changed tab
   - Review changes
   - Approve

7. **Merge:**
   - Merge pull request
   - Confirm merge
   - Delete branch on GitHub

8. **Update local:**
   ```bash
   git checkout main
   git pull
   git branch -d feature/improve-documentation
   ```

**You just completed the professional workflow from start to finish!**

---

## Tools to Help You

**Absolutely use any resource:**

### When Stuck

**Google:**
- "git create branch"
- "how to create pull request github"
- "git merge branch"
- "delete branch after merge"

**AI Assistants:**
- "Explain git branches in simple terms"
- "How do I create a pull request on GitHub?"
- "What's the difference between merge and rebase?"
- "Should I delete branches after merging?"

### GitHub Documentation

- [About Branches](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-branches)
- [About Pull Requests](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests)
- [Reviewing Changes](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/reviewing-changes-in-pull-requests)

### VS Code Git Integration

**VS Code shows current branch:**
- Bottom left corner shows branch name
- Click it to switch branches
- Can create branches from UI

**But learn Terminal first** so you understand what's happening.

---

## Common Branch Workflows

### Starting New Work

**Always:**
1. Switch to main
2. Pull latest changes
3. Create new branch from main

```bash
git checkout main
git pull
git checkout -b feature/your-feature-name
```

**This ensures your branch starts from latest main.**

---

### Branch Naming Conventions

**Good patterns:**
- `feature/add-personas`
- `fix/broken-link`
- `docs/update-readme`
- `redesign/navigation`

**Bad patterns:**
- `test` (too vague)
- `my-changes` (not descriptive)
- `asdf` (meaningless)
- `final` (unclear)

**Use descriptive names that explain what the branch does.**

---

### Multiple Branches at Once

**You can have many branches:**

```bash
git checkout -b feature/personas
# Work on personas

git checkout -b feature/research-guide
# Work on research guide

git checkout feature/personas
# Back to personas work
```

**Each branch is independent.**

Switch between them anytime without conflict.

---

## Handling Conflicts in PRs

### When PRs Conflict

**Scenario:**
- You created feature branch from main
- Teammate merged their PR to main
- Now your branch conflicts with main

**GitHub will show:** "This branch has conflicts that must be resolved"

**Solution:**

1. **Update your branch with latest main:**
   ```bash
   git checkout feature/your-branch
   git pull origin main
   ```

2. **Resolve any conflicts** (just like Lesson 4)

3. **Commit the resolution:**
   ```bash
   git add .
   git commit -m "Resolved conflicts with main"
   git push
   ```

4. **PR automatically updates** and conflicts are resolved!

---

## Completion Checklist

You're done when you can:

- [ ] Create a new branch (`git checkout -b`)
- [ ] Switch between branches (`git checkout`)
- [ ] Make commits on a branch
- [ ] Push a branch to GitHub
- [ ] Create a pull request on GitHub
- [ ] Review a pull request (comment, approve)
- [ ] Merge a pull request
- [ ] Delete branches (local and remote)
- [ ] Complete the full cycle independently
- [ ] Understand why teams use this workflow

**Bonus:**
- [ ] Created 2+ feature branches successfully
- [ ] Reviewed and merged 2+ pull requests
- [ ] Resolved conflict in a PR
- [ ] Explained the workflow to someone else

---

## What You Accomplished

**You just:**
- Learned professional Git workflow
- Created feature branches
- Opened pull requests
- Conducted code reviews
- Merged work collaboratively
- Cleaned up after completion

**This is exactly how developers work at top tech companies.**

---

## The Daily Team Workflow

**In a real team:**

**Morning:**
```bash
git checkout main
git pull  # Get everyone's merged work
git checkout -b feature/today-work
```

**During day:**
- Make commits on your branch
- Push regularly for backup

**When ready for review:**
- Push final version
- Open pull request
- Request review from teammates

**After approval:**
- Merge PR
- Delete branch
- Start next feature

**This cycle repeats constantly.**

---

## Best Practices

### PR Best Practices

**Keep PRs small:**
- Easier to review
- Faster to merge
- Less likely to conflict
- Clearer purpose

**Write good descriptions:**
- What changed
- Why it changed
- How to test it
- Screenshots if relevant

**Respond to feedback:**
- Address all comments
- Explain your reasoning
- Make requested changes
- Thank reviewers

---

### Review Best Practices

**Be constructive:**
- Suggest improvements, don't just criticize
- Explain why you're suggesting changes
- Appreciate good work

**Be thorough:**
- Check all files changed
- Look for errors or issues
- Test if possible

**Be timely:**
- Review within 24 hours
- Don't block teammates
- If busy, let them know when you'll review

---

## Before Next Week

**Practice this workflow:**

1. Create a feature branch
2. Make changes
3. Open PR
4. Review it
5. Merge it
6. Delete branch

**Do this 3 times over the week.**

By Lesson 6, this workflow will feel natural.

---

## Next Week Preview

**Lesson 6: Real Project Setup**
- Set up complete UX project repository
- Create proper documentation structure
- Invite collaborators
- Establish team workflow
- Practice all skills together

**Preparation:**
- Make sure branch workflow feels comfortable
- Practice creating PRs
- Get confident with the full cycle

---

## Collaboration Tips

**When working with teammates:**

**Communicate:**
- Tag people in PR comments (@username)
- Explain your changes clearly
- Ask questions if unsure

**Stay organized:**
- One branch per feature
- Delete old branches
- Keep PRs focused

**Be responsive:**
- Address feedback promptly
- Merge when approved
- Don't leave PRs open forever

---

## Encouragement

**This lesson you learned the professional workflow.**

If branches felt confusing at first, that's normal. The concept of parallel work streams takes practice.

**By Lesson 6, you'll be:**
- Creating branches without thinking
- Opening PRs naturally
- Reviewing work constructively
- Collaborating like a pro

**You're using real developer tools the way real teams use them.**

That's worth celebrating.

---

## Questions or Stuck?

**Resources:**
- Solution files showing expected workflow
- GitHub documentation on pull requests
- Team channel: [your channel]
- Office hours: [day/time]

**Branch confusion is common.** Visual diagrams help - search "git branch visualization" or ask for help understanding the mental model.

---

## Final Thought

**You now know the complete Git workflow.**

Everything from here is refinement and practice.

Lesson 6 brings it all together into a real UX project setup.

You're ready.

Excellent work. See you in Lesson 6.
