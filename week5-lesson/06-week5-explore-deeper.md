# Week 5: Explore Deeper - Advanced Branching & Pull Requests

**Optional material for mastering professional Git workflows**

---

## When to Use This

Return to this file when:
- You've completed the main Week 5 exercises
- You're working on a team with complex workflows
- You need PR best practices
- You encounter branching issues
- You want to understand advanced strategies

**This is NOT required.** The basics are sufficient for most UX work.

---

## Branch Lifecycle in Detail

### Complete Branch Journey

**Birth:**
```bash
git checkout -b feature/new-feature
```
- Created from main
- Starts with same history as main
- Independent workspace

**Life:**
- Make commits
- Push to GitHub
- Update from main if needed
- Collaborate via PR comments

**Death:**
- Merged into main
- Deleted on GitHub
- Deleted locally
- History preserved in main

**Most branches live 1-5 days.**

---

### Branch States

**Local only:**
- Exists on your computer
- Not backed up
- Nobody else can see it

**Pushed to GitHub:**
- Backed up on GitHub
- Team can see it
- Can create PR

**Merged:**
- Code integrated into main
- Branch no longer needed
- Safe to delete

**Deleted:**
- Branch reference gone
- Commits preserved in main
- Can be recovered if needed

---

## Advanced Branch Naming

### Naming Conventions

**Type prefixes:**
```
feature/    - New functionality
fix/        - Bug fixes
docs/       - Documentation only
refactor/   - Code restructuring
test/       - Adding tests
chore/      - Maintenance tasks
hotfix/     - Urgent production fixes
```

**With ticket numbers:**
```
feature/UX-123-add-personas
fix/UX-456-broken-link
docs/UX-789-update-research
```

**Team-specific conventions:**
- Some teams use `feat/` instead of `feature/`
- Some use `bugfix/` instead of `fix/`
- Follow your team's standard

---

### Descriptive vs. Generic Names

**Good (self-documenting):**
```
feature/add-user-journey-maps
fix/research-findings-broken-images
docs/update-persona-demographics
redesign/improve-wireframe-layout
```

**Bad (requires context):**
```
feature/updates
fix/stuff
docs/changes
my-work
```

**Rule:** Someone else should understand what the branch does from the name alone.

---

## Working with Multiple Branches

### Switching Between Branches

**The golden rule:** Commit before switching

**Safe switch:**
```bash
git add .
git commit -m "Work in progress"
git checkout other-branch
```

**What happens when you switch:**
- Working directory changes
- Files appear/disappear based on branch
- .git folder tracks which branch you're on

---

### Stashing Instead of Committing

**Scenario:** Need to switch but not ready to commit

**Stash your changes:**
```bash
git stash
git checkout other-branch
# Do other work
git checkout original-branch
git stash pop
```

**Stash = temporary storage for uncommitted changes**

**View stashes:**
```bash
git stash list
```

**Apply specific stash:**
```bash
git stash apply stash@{0}
```

---

### Keeping Feature Branches Updated

**Scenario:** Working on long-lived branch, main has new commits

**Option 1 - Merge main into feature:**
```bash
git checkout feature/my-feature
git pull origin main
```

Brings main's changes into your feature branch.

**Option 2 - Rebase feature onto main:**
```bash
git checkout feature/my-feature
git rebase main
```

Replays your commits on top of latest main.

**When to update:**
- Before creating PR (ensure compatibility)
- When main has critical changes you need
- To resolve conflicts early

---

## Pull Request Best Practices

### Creating Excellent PRs

**PR Title:**
```
Good: "Add user persona templates for mobile research"
Bad:  "Updates"
```

**PR Description Template:**
```markdown
## What Changed
Brief summary of the changes in this PR.

## Why
Context: Why was this change needed?

## What to Review
- Check personas match brand voice
- Verify all links work
- Ensure images load correctly

## Screenshots
[If applicable - especially for UX work]

## Testing Done
- Verified markdown renders correctly
- Checked on mobile and desktop GitHub
- All links tested

## Questions
- Should we use different terminology for "user goals"?
- Is this level of detail appropriate?
```

---

### PR Size Guidelines

**Ideal PR:**
- 1-5 files changed
- 50-300 lines
- Single focused change
- Can be reviewed in 15 minutes

**Too large:**
- 20+ files
- 1000+ lines
- Multiple unrelated changes
- Takes hours to review

**Solution for large work:** Break into multiple PRs

**Example:**
Instead of one "Redesign research section" PR:
1. PR 1: Update persona template
2. PR 2: Add journey map examples
3. PR 3: Revise methodology docs
4. PR 4: Update team contacts

**Each PR** can be reviewed and merged independently.

---

### Writing PR Descriptions

**Include:**
1. **Context** - Why this change?
2. **Changes** - What did you do?
3. **Impact** - Who/what does this affect?
4. **Testing** - How did you verify it works?
5. **Questions** - Anything you're unsure about?

**Link related items:**
```markdown
Closes #123
Related to #456
Follows up on PR #789
```

**Tag reviewers:**
```markdown
@sarah please review research methodology
@james please check design terminology
```

---

## Code Review Etiquette

### As PR Author

**Do:**
- Respond to all comments (even if just "👍")
- Thank reviewers for their time
- Make requested changes promptly
- Explain your reasoning if you disagree
- Push updates as new commits (easier to review changes)
- Mark conversations as resolved after addressing

**Don't:**
- Get defensive about feedback
- Ignore comments
- Force push after review started
- Merge before approval
- Let PR go stale

**If you disagree with feedback:**
```markdown
I understand your concern about X. However, I chose Y because [reason].
Would love to discuss alternatives if you feel strongly!
```

---

### As Reviewer

**Do:**
- Be constructive and specific
- Suggest alternatives, don't just criticize
- Acknowledge good work
- Explain your reasoning
- Review promptly (within 24 hours)
- Approve when satisfied

**Don't:**
- Be vague ("this doesn't look right")
- Nitpick minor style issues
- Block without good reason
- Delay reviews unnecessarily
- Be condescending

**Constructive feedback:**
```markdown
❌ "This is wrong"
✅ "I think we should use 'participant' instead of 'user' here
    to match our research terminology guide. What do you think?"

❌ "Too long"
✅ "This section is detailed! Consider breaking it into subsections
    with headers for easier scanning?"
```

---

### Review States

**Comment:**
- General feedback
- Not blocking merge
- Suggestions or questions

**Approve:**
- Changes look good
- Ready to merge
- Trust author to merge

**Request Changes:**
- Must be addressed before merge
- Blocking approval
- Specific issues noted

**Use "Request Changes" sparingly** - only for real problems.

---

## Branch Protection

### What is Branch Protection?

**GitHub feature that restricts who can:**
- Push directly to a branch
- Merge pull requests
- Delete the branch

**Common for `main` branch on team projects.**

---

### Typical Protection Rules

**Require pull requests:**
- Can't push directly to main
- Must create branch and PR
- Enforces review process

**Require approvals:**
- PR needs X approvals before merge
- Usually 1-2 reviewers

**Require status checks:**
- Automated tests must pass
- Linters must succeed
- CI/CD pipeline must complete

**No force pushes:**
- Can't rewrite main branch history
- Prevents accidental data loss

---

### Working with Protected Branches

**You can't do this anymore:**
```bash
git checkout main
# make changes
git commit -m "Quick fix"
git push    # ❌ Rejected!
```

**You must do this:**
```bash
git checkout -b fix/quick-fix
# make changes
git commit -m "Quick fix"
git push -u origin fix/quick-fix
# Create PR on GitHub
# Get approval
# Merge via PR
```

**Protection forces good practices.**

---

## Merge Strategies

### Merge Commit (Default)

**What happens:**
```
main:    A -> B -----------> C
                \           /
feature:         D -> E -> F
```

After merge:
```
main: A -> B -> C -> M
```

**M is a merge commit** that combines changes.

**Pros:**
- Preserves complete history
- Shows when feature was integrated
- Can revert entire feature easily

**Cons:**
- More commits in history
- Graph can get messy

---

### Squash and Merge

**What happens:**
- Combines all feature branch commits into one
- Applies as single commit to main

```
Before:
feature: D -> E -> F -> G

After squash merge:
main: A -> B -> C -> [DEFG combined]
```

**Pros:**
- Clean main history
- Each feature = one commit
- Easy to read git log

**Cons:**
- Loses intermediate commits
- Can't see feature development details

**Good for:**
- Features with many "WIP" commits
- Keeping main history clean

---

### Rebase and Merge

**What happens:**
- Replays feature commits on top of main
- No merge commit

```
Before:
main:    A -> B -> C
feature: A -> D -> E

After rebase merge:
main: A -> B -> C -> D -> E
```

**Pros:**
- Linear history
- No merge commits
- Clean and simple

**Cons:**
- Rewrites commit IDs
- More complex process

**Good for:**
- Teams that want linear history
- Advanced Git users

---

### Which Strategy to Use?

**For UX documentation repos:**
- Squash and merge is usually best
- Keeps main clean
- Each PR = one commit
- Easy to see what changed

**For code repos:**
- Depends on team preference
- Merge commit is safest
- Rebase for clean history

**GitHub lets you choose per-PR** in the merge button dropdown.

---

## Advanced Scenarios

### Scenario: Forgot to Create Branch

**You committed to main instead of feature branch:**

```bash
# Uh oh, committed to main by mistake
git log    # See your commit

# Create branch from current state
git branch feature/my-work

# Reset main to before your commit
git reset --hard origin/main

# Switch to new branch
git checkout feature/my-work

# Your work is safe on the feature branch!
```

---

### Scenario: Wrong Branch Name

**You created `featuer/typo` instead of `feature/typo`:**

**Rename local branch:**
```bash
git branch -m featuer/typo feature/typo
```

**If already pushed:**
```bash
git push origin :featuer/typo           # Delete old name
git push -u origin feature/typo         # Push correct name
```

---

### Scenario: Need to Undo Last Commit

**Committed on branch but want to undo:**

**Keep changes, uncommit:**
```bash
git reset --soft HEAD~1
```
Changes back in working directory, uncommitted.

**Discard changes completely:**
```bash
git reset --hard HEAD~1
```
⚠️ **Destructive** - changes are lost!

**Already pushed?**
```bash
git revert HEAD
git push
```
Creates new commit that undoes the last one.

---

### Scenario: Branch Diverged from Main

**Your feature branch is way behind main:**

**Update feature branch:**
```bash
git checkout feature/my-feature
git pull origin main
# Resolve any conflicts
git push
```

**Or rebase (advanced):**
```bash
git checkout feature/my-feature
git rebase origin/main
# Resolve any conflicts
git push --force-with-lease
```

---

### Scenario: Merge Conflict in PR

**GitHub shows "This branch has conflicts that must be resolved":**

**Fix locally:**
```bash
git checkout feature/my-feature
git pull origin main
# Conflicts!
# Edit files to resolve
git add .
git commit -m "Resolved merge conflicts"
git push
```

**PR updates automatically**, conflicts resolved.

---

## Collaboration Patterns

### Solo UX Practitioner

**Pattern:**
- Create feature branches for each task
- Push to GitHub for backup
- Create PRs to document changes
- Merge yourself after review

**Why still use PRs solo?**
- Forces you to review your own work
- Documents what changed and why
- Practice for team collaboration
- Portfolio evidence of process

---

### Small UX Team (2-5 people)

**Pattern:**
- Each person creates feature branches
- PRs require 1 approval
- Review each other's work
- Discuss via PR comments

**Communication:**
- Tag reviewer in PR description
- Respond to feedback within 1 day
- Sync in standup about blocked PRs

---

### Large Cross-Functional Team

**Pattern:**
- Feature branches with ticket IDs
- PRs require 2 approvals (1 UX, 1 dev)
- CI/CD runs automated checks
- Protected main branch

**Process:**
- Branch naming: `type/TICKET-ID-description`
- PR templates enforce structure
- Review rotation to distribute load
- Merge deadlines for release planning

---

## Troubleshooting

### Can't Switch Branches

**Error:**
```
error: Your local changes would be overwritten by checkout.
Please commit your changes or stash them before you switch branches.
```

**Fix:**
```bash
# Option 1: Commit
git add .
git commit -m "WIP: Partial progress"
git checkout other-branch

# Option 2: Stash
git stash
git checkout other-branch
# Later: git stash pop
```

---

### Can't Delete Branch

**Error:**
```
error: The branch 'feature/x' is not fully merged.
```

**Fix (if branch is actually merged via PR):**
```bash
git branch -D feature/x    # Force delete
```

**Fix (if you want to keep the changes):**
```bash
git merge feature/x    # Merge it first
git branch -d feature/x    # Then delete
```

---

### PR Shows Tons of Commits

**Problem:** PR includes commits from main you didn't write

**Cause:** Branch was created from outdated main

**Fix:**
```bash
git checkout main
git pull
git checkout feature/my-feature
git rebase main
git push --force-with-lease
```

**PR updates to show only your commits.**

---

### Pushed Sensitive Data

**OH NO! API key in commit!**

**Immediate:**
1. Rotate/revoke the exposed credential
2. Don't commit the fix - won't help

**Remove from history (advanced):**
```bash
git filter-branch --force --index-filter \
  "git rm --cached --ignore-unmatch sensitive-file.txt" \
  --prune-empty --tag-name-filter cat -- --all

git push --force --all
```

**Better:** Use `.gitignore` to prevent committing secrets.

---

## Advanced Git Commands for Branching

### Interactive Rebase

**Clean up commits before pushing:**
```bash
git rebase -i HEAD~3
```

Opens editor with:
```
pick abc123 Add personas
pick def456 Fix typo
pick ghi789 Another typo fix
```

**Options:**
- `pick` - keep commit
- `squash` - combine with previous
- `reword` - change message
- `drop` - remove commit

**Use case:** Clean up messy history before creating PR.

---

### Cherry-Pick

**Apply specific commit from another branch:**
```bash
git checkout main
git cherry-pick abc123
```

Copies commit `abc123` to current branch.

**Use case:** Need one commit from feature branch without merging all.

---

### Reflog

**See all recent HEAD positions:**
```bash
git reflog
```

**Recover "lost" commits:**
```bash
git checkout abc123    # From reflog
git branch recovery abc123
```

**Use case:** Undoing a mistaken reset/rebase.

---

## Monitoring and Logging

### See All Branches

**Local branches:**
```bash
git branch
```

**Remote branches:**
```bash
git branch -r
```

**All branches (local + remote):**
```bash
git branch -a
```

**With last commit info:**
```bash
git branch -v
```

---

### Compare Branches

**See differences:**
```bash
git diff main feature/my-feature
```

**See commit differences:**
```bash
git log main..feature/my-feature
```

Shows commits in feature that aren't in main.

---

### Visualize Branch History

**Text-based graph:**
```bash
git log --oneline --graph --all
```

**Shows branching/merging visually in terminal.**

**GUI tools:**
- GitHub network graph
- GitKraken (visual Git client)
- SourceTree
- VSCode GitLens extension

---

## Resources

### Official Documentation
- [Git Branching](https://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell)
- [GitHub Pull Requests](https://docs.github.com/en/pull-requests)
- [Git Branch](https://git-scm.com/docs/git-branch)

### Learning Resources
- [Learn Git Branching](https://learngitbranching.js.org/) - Interactive visualization
- [GitHub Skills](https://skills.github.com/) - Practice repos
- [Conventional Commits](https://www.conventionalcommits.org/) - Commit message standard

### Tools
- [GitHub CLI](https://cli.github.com/) - Create/manage PRs from terminal
- [Hub](https://hub.github.com/) - Extends git with GitHub features

---

## Practice Challenges

### Challenge 1: The Rebase Workflow

1. Create feature branch
2. Make 3 commits
3. Rebase interactive to squash into 1
4. Push to GitHub
5. Create PR

**Goal:** Clean PR with single commit.

---

### Challenge 2: Conflict Resolution

1. Create branch, edit line 5 of file
2. Edit line 5 on GitHub (different text)
3. Pull, get conflict
4. Resolve conflict
5. Push resolution

**Goal:** Comfortable with conflicts.

---

### Challenge 3: Branch Rotation

1. Create `feature/a`
2. Make commits
3. Create `feature/b` from main
4. Make commits
5. Switch back to `feature/a`
6. Continue work
7. Create PRs for both
8. Merge both

**Goal:** Fluent branch switching.

---

## Mastery Checklist

You've mastered branching when you can:

- [ ] Create and delete branches effortlessly
- [ ] Work on multiple branches simultaneously
- [ ] Write clear, focused PRs
- [ ] Review others' PRs constructively
- [ ] Resolve merge conflicts calmly
- [ ] Keep feature branches updated
- [ ] Choose appropriate merge strategy
- [ ] Recover from branching mistakes
- [ ] Explain workflow to teammates
- [ ] Contribute to team workflow discussions

**At this point:** You're operating at a professional level.

---

## Return to Main Course

Continue to Week 6 to put everything together into a complete UX project workflow.

**Remember:** Branches enable fearless experimentation. Use them liberally!
