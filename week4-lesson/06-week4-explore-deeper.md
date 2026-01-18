# Week 4: Explore Deeper - Advanced GitHub Collaboration

**Optional material for mastering remote Git workflows**

---

## When to Use This

Return to this file when:
- You've completed the main Week 4 exercises
- You're collaborating with a team
- You encounter merge conflicts
- You need troubleshooting help
- You want to understand the theory deeper

**This is NOT required.** The basics are sufficient for most work.

---

## Understanding Push/Pull in Depth

### The Three Locations

**Working Directory:**
- Files you can see and edit
- Your actual files on disk
- Where you do your work

**Local Repository (.git folder):**
- Hidden folder in your project
- Stores all commits
- Your computer's version history

**Remote Repository (GitHub):**
- Copy on GitHub's servers
- Team's shared version
- Backup and collaboration point

---

### How Push Works Internally

**When you run `git push`:**

1. **Git checks:** Do I have commits that aren't on GitHub?
2. **Git verifies:** Is GitHub ahead of me?
3. **If yes:** Reject push, tell you to pull first
4. **If no:** Upload your new commits
5. **GitHub receives:** Adds your commits to its history
6. **Both synchronized:** Local and remote match

**Visual:**
```
Before push:
Local:  A -> B -> C -> D
Remote: A -> B -> C

After push:
Local:  A -> B -> C -> D
Remote: A -> B -> C -> D
```

---

### How Pull Works Internally

**When you run `git pull`:**

1. **Fetch:** Download new commits from GitHub
2. **Check:** Can these merge cleanly?
3. **If yes:** Automatically merge into your branch
4. **If no:** Report conflict, ask you to resolve
5. **Update:** Your working directory shows merged result

**Visual:**
```
Before pull:
Local:  A -> B -> C
Remote: A -> B -> C -> D -> E

After pull:
Local:  A -> B -> C -> D -> E
Remote: A -> B -> C -> D -> E
```

---

## Synchronization Strategies

### Always Pull Before Starting Work

**Best practice workflow:**
```bash
# Start of day
git checkout main
git pull

# Start new feature
git checkout -b feature/my-work
# Work, commit, push
```

**Why:** Ensures you're building on latest code.

---

### Push Frequently

**Recommended frequency:**
- After completing a logical chunk
- Before lunch break
- Before meetings
- End of day
- Before switching tasks

**Benefits:**
- Backup on GitHub
- Team sees your progress
- Reduces merge conflicts
- Easy to recover if computer fails

---

### The "Pull -> Work -> Commit -> Push" Cycle

**Ideal workflow:**
```bash
git pull                      # Get latest
# Make changes
git add .
git commit -m "Description"
git push                      # Share changes
```

**Repeat frequently throughout the day.**

---

## Handling Common Scenarios

### Scenario: You Forgot to Push

**Situation:**
- You commited Friday afternoon
- Left without pushing
- Computer died over weekend
- Work is lost

**Prevention:**
```bash
# Before leaving for the day
git push

# Or create an alias:
git config --global alias.done '!git add . && git commit -m "End of day" && git push'

# Then just run:
git done
```

---

### Scenario: You Forgot to Pull

**Situation:**
- Teammate pushed changes
- You made changes without pulling
- Try to push
- Get rejected

**Error message:**
```
! [rejected]        main -> main (fetch first)
error: failed to push some refs to 'github.com/user/repo.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
```

**Solution:**
```bash
git pull    # Merge their changes with yours
git push    # Now push combined changes
```

**If there's a conflict:** See merge conflict section below.

---

### Scenario: Multiple People Editing Same File

**Situation:**
- You edit README.md lines 1-10
- Teammate edits README.md lines 50-60
- Different parts of same file

**What happens:**
- Git is smart enough to merge automatically
- Both changes get combined
- No conflict!

**When it fails:**
- You both edit the same lines
- Git can't decide which version to keep
- You get a merge conflict

---

## Merge Conflicts

### What is a Merge Conflict?

**Happens when:**
- You and teammate edit same lines
- You both commit your versions
- One person pushes
- Other person pulls
- Git can't auto-merge

**Example:**
You changed line 5 to: "Contact: alice@example.com"
Teammate changed line 5 to: "Contact: bob@example.com"

Git doesn't know which email to keep.

---

### Recognizing a Conflict

**When you pull, you see:**
```
Auto-merging README.md
CONFLICT (content): Merge conflict in README.md
Automatic merge failed; fix conflicts and then commit the result.
```

**Git status shows:**
```
Unmerged paths:
  (use "git add <file>..." to mark resolution)
        both modified:   README.md
```

---

### Resolving a Conflict

**Step 1: Open the conflicted file**

You'll see conflict markers:
```markdown
# Project Title

<<<<<<< HEAD
Contact: alice@example.com
=======
Contact: bob@example.com
>>>>>>> origin/main
```

**What this means:**
- `<<<<<<< HEAD` - Your version starts
- `=======` - Separator
- `>>>>>>> origin/main` - Their version ends

---

**Step 2: Decide what to keep**

Options:
1. Keep your version (delete theirs and markers)
2. Keep their version (delete yours and markers)
3. Keep both (delete markers)
4. Write something new (delete both and markers)

**Example resolution:**
```markdown
# Project Title

Contact: alice@example.com, bob@example.com
```

---

**Step 3: Mark as resolved**

```bash
git add README.md
git commit -m "Resolved merge conflict in contact info"
git push
```

**Done!** Conflict resolved.

---

### Avoiding Conflicts

**Best practices:**
1. **Pull often** - Stay up to date
2. **Push often** - Share changes early
3. **Communicate** - Tell team what you're editing
4. **Small changes** - Easier to merge
5. **Work on different files** - No overlap

**Can't always avoid them**, but can minimize.

---

## Advanced Pull Strategies

### Pull vs Fetch

**Git pull = Fetch + Merge**

**Fetch only:**
```bash
git fetch
```
- Downloads commits from GitHub
- Doesn't merge them
- Let's you review before merging

**Then merge when ready:**
```bash
git merge origin/main
```

**Use case:** Want to see what changed before integrating.

---

### Pull with Rebase

**Normal pull (merge):**
```bash
git pull
```

**Pull with rebase:**
```bash
git pull --rebase
```

**Difference:**
- Merge: Creates a merge commit
- Rebase: Replays your commits on top of theirs

**Rebase creates cleaner history**, but changes commit IDs.

**For UX work:** Merge is fine. Rebase is optional.

---

## Remote Repository Details

### Viewing Remote Info

**See all remotes:**
```bash
git remote -v
```

**Output:**
```
origin  https://github.com/user/repo.git (fetch)
origin  https://github.com/user/repo.git (push)
```

**See more details:**
```bash
git remote show origin
```

Shows branches, fetch/push URLs, tracking info.

---

### Multiple Remotes

**Scenario:** You forked someone's repo

**You have:**
- `origin` - Your fork
- `upstream` - Original repo

**Setup:**
```bash
git remote add upstream https://github.com/original-owner/repo.git
```

**Pull from original:**
```bash
git pull upstream main
```

**Push to your fork:**
```bash
git push origin main
```

**Common in open source**, less common in team projects.

---

### Changing Remote URL

**If repo URL changes:**
```bash
git remote set-url origin NEW_URL
```

**Verify:**
```bash
git remote -v
```

---

## Tracking and Upstream Branches

### What is Upstream?

**When you run:**
```bash
git push -u origin feature-branch
```

**The `-u` flag:**
- Sets up "tracking"
- Links local branch to remote branch
- Future `git push` doesn't need arguments

**After `-u` is set:**
```bash
git push    # Automatically knows where to push
git pull    # Automatically knows where to pull from
```

---

### Checking Tracking

**See all branches and their upstreams:**
```bash
git branch -vv
```

**Output:**
```
  main            abc123 [origin/main] Latest commit message
* feature-branch  def456 [origin/feature-branch] My feature
```

**Branch without upstream:**
```
  new-branch      ghi789 New branch (no upstream)
```

Must use `git push -u origin new-branch` first time.

---

## Checking Synchronization Status

### Are You Ahead or Behind?

**Check status:**
```bash
git status
```

**Output examples:**

**In sync:**
```
Your branch is up to date with 'origin/main'.
```

**Ahead (you have unpushed commits):**
```
Your branch is ahead of 'origin/main' by 2 commits.
  (use "git push" to publish your local commits)
```

**Behind (GitHub has commits you don't):**
```
Your branch is behind 'origin/main' by 1 commit, and can be fast-forwarded.
  (use "git pull" to update your local branch)
```

**Diverged (both have different commits):**
```
Your branch and 'origin/main' have diverged,
and have 1 and 1 different commits each, respectively.
  (use "git pull" to merge the remote branch into yours)
```

---

### Seeing Unpushed Commits

**What commits are local only?**
```bash
git log origin/main..HEAD
```

**Shows commits you haven't pushed yet.**

---

### Seeing Unpulled Commits

**What's on GitHub that you don't have?**
```bash
git fetch    # Download latest info
git log HEAD..origin/main
```

**Shows commits you haven't pulled yet.**

---

## Authentication Deep Dive

### Personal Access Tokens

**Why tokens instead of passwords?**
- More secure
- Can be revoked
- Scope-limited permissions
- Required by GitHub (passwords deprecated)

**Token expiration:**
- Set expiration when creating
- Get email warnings before expiry
- Can regenerate anytime

---

### Storing Credentials

**First push asks for username/token every time?**

**Solution - Credential helper:**

**Mac:**
```bash
git config --global credential.helper osxkeychain
```

**Stores token in Mac's Keychain** - auto-fills next time.

**Verify:**
```bash
git config --global credential.helper
```

Should show: `osxkeychain`

---

### SSH Keys (Alternative to Tokens)

**More advanced auth method:**
- Generate SSH key pair
- Add public key to GitHub
- No password/token prompts

**Setup:**
```bash
ssh-keygen -t ed25519 -C "your.email@example.com"
cat ~/.ssh/id_ed25519.pub
```

**Copy output, add to GitHub:**
- Settings → SSH and GPG keys → New SSH key

**Clone with SSH URL:**
```bash
git clone git@github.com:user/repo.git
```

**Benefit:** No password prompts, more secure.

---

## Cloning Repositories

### What is Cloning?

**Clone = Download entire repository**

**When to clone:**
- Joining existing project
- Contributing to open source
- Working on different computer
- Starting from template

**Command:**
```bash
git clone URL
```

---

### Cloning Workflow

**Clone a repo:**
```bash
cd ~/Desktop
git clone https://github.com/user/repo.git
cd repo
```

**You now have:**
- Full commit history
- All branches
- Connected remote (origin)
- Ready to work

**Make changes:**
```bash
# Edit files
git add .
git commit -m "My changes"
git push
```

**Same workflow as before!**

---

### Cloning Your Own Repos

**Scenario:** New computer, need your project

**On new computer:**
```bash
git clone https://github.com/YOUR-USERNAME/your-repo.git
cd your-repo
# Continue working
```

**All history preserved.**

---

## Best Practices for Teams

### Communication Protocols

**Before starting work:**
- Check team chat: "Working on feature X"
- Claim task/issue
- Avoid duplicating work

**While working:**
- Push frequently (share progress)
- Comment on your commits
- Update team on blockers

**After completing:**
- Push final version
- Create pull request (Week 5)
- Notify team for review

---

### Commit Message Standards

**Good messages:**
```bash
git commit -m "Add user research findings from Jan 2025"
git commit -m "Update persona based on stakeholder feedback"
git commit -m "Fix broken link in navigation doc"
```

**Bad messages:**
```bash
git commit -m "stuff"
git commit -m "changes"
git commit -m "asdfasdf"
```

**Format:** Start with verb, be specific, explain why if not obvious.

---

### When to Push to main

**Small team, informal:**
- Push to main anytime
- Trust teammates
- Quick and simple

**Larger team, formal:**
- Never push to main directly
- Use feature branches (Week 5)
- Pull requests for review
- Protected main branch

**Your team decides which approach.**

---

## Troubleshooting Guide

### "Repository not found"

**Causes:**
1. Typo in URL
2. Repository deleted
3. You don't have access (private repo)
4. Authentication failed

**Fix:**
- Verify URL on GitHub
- Check repository still exists
- Confirm you have access
- Try re-authenticating

---

### "Permission denied"

**Causes:**
1. Wrong credentials
2. Token expired
3. No write access to repo
4. SSH key not added

**Fix:**
- Regenerate token
- Check repo permissions
- Verify authentication method

---

### "Connection refused"

**Causes:**
1. No internet connection
2. GitHub down
3. Firewall blocking
4. Wrong URL

**Fix:**
- Check internet
- Visit status.github.com
- Try different network
- Verify URL

---

### "Merge conflict" (detailed)

**See conflict section above for full guide.**

**Quick fix:**
1. Open conflicted file
2. Find `<<<<<<`, `=======`, `>>>>>>>`
3. Edit to resolve
4. Remove conflict markers
5. `git add file`
6. `git commit`
7. `git push`

---

### "Diverged branches"

**You and GitHub both have unique commits.**

**Fix:**
```bash
git pull    # Merge their changes with yours
# Resolve any conflicts
git push    # Push combined history
```

**Or with rebase:**
```bash
git pull --rebase
git push
```

---

### "Detached HEAD state"

**What:** You're not on a branch

**How it happens:**
- Checked out a specific commit
- Checked out a tag

**Fix:**
```bash
git checkout main
```

Gets you back to a branch.

---

## Advanced Scenarios

### Working from Multiple Computers

**Workflow:**

**Computer 1 (morning):**
```bash
git pull
# Work
git add .
git commit -m "Progress on feature"
git push
```

**Computer 2 (afternoon):**
```bash
git pull    # Gets work from Computer 1
# Continue working
git add .
git commit -m "More progress"
git push
```

**Back on Computer 1 (next day):**
```bash
git pull    # Gets work from Computer 2
# Keep working
```

**Key:** Always pull first!

---

### Recovering Pushed Work

**Scenario:** You pushed bad code, want to undo

**Option 1 - Revert (safe):**
```bash
git revert HEAD    # Creates new commit undoing last commit
git push
```

**History preserved**, undo is visible.

**Option 2 - Reset (dangerous):**
```bash
git reset --hard HEAD~1    # Delete last commit locally
git push --force           # Force push (risky!)
```

**History rewritten** - only do if you're sure!

**For teams:** Use revert, not reset.

---

### Stashing Before Pull

**Scenario:** You have uncommitted changes but need to pull

**Error:**
```
error: Your local changes would be overwritten by merge.
Please commit or stash them.
```

**Solution - Stash:**
```bash
git stash               # Temporarily save changes
git pull                # Pull from GitHub
git stash pop           # Restore your changes
```

**Your changes applied on top of pulled commits.**

---

## Monitoring and Logging

### Checking Recent Activity

**See recent commits:**
```bash
git log --oneline -5
```

Shows last 5 commits.

**See who changed what:**
```bash
git log --oneline --author="Name"
```

All commits by that person.

**See commits in date range:**
```bash
git log --since="2 weeks ago"
git log --until="2025-01-01"
```

---

### Viewing Differences

**What's different from last push?**
```bash
git diff origin/main
```

**What changed in last commit?**
```bash
git show HEAD
```

**Compare two commits:**
```bash
git diff abc123 def456
```

---

### Blame (Who Changed What)

**See who wrote each line:**
```bash
git blame filename.md
```

**Shows author and commit for every line.**

**Use in VS Code:**
- Install GitLens extension
- Hover over line
- See blame info inline

---

## Performance and Optimization

### Large Repositories

**If clone/pull is slow:**

**Shallow clone (history limited):**
```bash
git clone --depth 1 URL
```

Gets latest snapshot only, not full history.

**Sparse checkout (files limited):**
- Clone only certain files
- Advanced technique
- Rarely needed for UX repos

---

### Cleaning Up

**Remove deleted branches:**
```bash
git fetch --prune
```

**See disk usage:**
```bash
git count-objects -vH
```

**Garbage collection:**
```bash
git gc
```

Optimizes `.git` folder size.

---

## Resources

### Official Documentation
- [Git Push](https://git-scm.com/docs/git-push)
- [Git Pull](https://git-scm.com/docs/git-pull)
- [Git Remote](https://git-scm.com/docs/git-remote)

### GitHub Docs
- [About Remote Repositories](https://docs.github.com/en/get-started/getting-started-with-git/about-remote-repositories)
- [Resolving Merge Conflicts](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/addressing-merge-conflicts)

### Learning Resources
- [Learn Git Branching](https://learngitbranching.js.org/) - Visual, interactive
- [Oh Shit, Git!?!](https://ohshitgit.com/) - Fixing mistakes

---

## Practice Challenges

### Challenge 1: Simulate Collaboration

**Setup:**
1. Create a test repository
2. Add a file
3. Push to GitHub

**Practice:**
1. Edit file on GitHub, commit
2. Edit same file locally (different lines)
3. Commit locally
4. Try to push (will fail)
5. Pull (should auto-merge)
6. Push successfully

---

### Challenge 2: Create a Conflict

**Setup:**
Same as Challenge 1

**Practice:**
1. Edit line 5 on GitHub to "Version A"
2. Edit line 5 locally to "Version B"
3. Commit both
4. Pull (conflict!)
5. Resolve conflict
6. Push resolution

**Goal:** Comfortable resolving conflicts.

---

### Challenge 3: Multi-Computer Workflow

**If you have two computers:**
1. Clone repo on both
2. Make change on Computer 1, push
3. Pull on Computer 2, verify
4. Make change on Computer 2, push
5. Pull on Computer 1, verify

**Simulates real workflow.**

---

## Mastery Checklist

You've mastered remote Git when you can:

- [ ] Push and pull without thinking
- [ ] Resolve merge conflicts calmly
- [ ] Understand when to pull vs fetch
- [ ] Use tracking branches effectively
- [ ] Troubleshoot common errors independently
- [ ] Work seamlessly across multiple computers
- [ ] Explain push/pull to someone else
- [ ] Check synchronization status quickly
- [ ] Recover from mistakes
- [ ] Collaborate without stepping on toes

**At this point:** You're fluent in remote Git workflows.

---

## Return to Main Course

Continue to Week 5 to learn feature branches and pull requests - the professional collaboration workflow.

**Remember:** Push often, pull first, communicate with your team!
