# Lesson 4: GitHub & Remote Repos
## 5-Minute Hands-On Lesson

### What You'll Learn

By the end of this lesson, you'll:
- Create a repository on GitHub
- Connect your local repo to GitHub
- Push your commits to the cloud
- Pull changes from GitHub
- Clone existing repositories
- Resolve a simple merge conflict

**Time needed:** 20-25 minutes

**Important:** Have your GitHub account ready and be signed in.

---

## The Core Concept

**Lesson 3:** Git on your computer (local)
**Lesson 4:** Git in the cloud (remote = GitHub)

**The connection:**
```
Your Computer          →  push  →          GitHub
(local repository)                      (remote repository)

Your Computer          ←  pull  ←          GitHub
```

You make commits locally, then push them to GitHub. Others can pull them down.

---

## Part 1: Create Repository on GitHub (3 minutes)

### Step-by-Step

**1. Go to GitHub:**
- Open browser
- Go to [github.com](https://github.com)
- Sign in

**2. Create New Repository:**
- Click the **+** icon (top right)
- Select "New repository"

**3. Configure Repository:**

**Repository name:** `ux-practice-lesson04`
(Use lowercase with hyphens)

**Description (optional):** "Practice repository for learning GitHub"

**Visibility:**
- Select **Private** (only you can see it)

**Initialize options:**
- **DO NOT** check "Add a README file"
- **DO NOT** add .gitignore
- **DO NOT** choose a license

(We already have files locally)

**4. Click "Create repository"**

**What you see:**
GitHub shows you setup instructions. We'll use the "push an existing repository" section.

---

## Part 2: Connect Local Repo to GitHub (3 minutes)

### Get the Repository URL

On the GitHub page you just created, find the repository URL:

**It looks like:**
```
https://github.com/yourusername/ux-practice-lesson04.git
```

**Click the copy button** next to it.

---

### Add Remote Connection

**Navigate to your Lesson 3 practice folder:**
```bash
cd ~/Desktop/lesson03-practice
```

**Verify you have commits:**
```bash
git log --oneline
```

You should see your commits from Lesson 3.

**Add GitHub as a remote:**
```bash
git remote add origin https://github.com/yourusername/ux-practice-lesson04.git
```

Replace `yourusername` with your actual GitHub username.

**What this does:**
- Creates a connection named "origin"
- "origin" is the standard name for your main GitHub repo
- Points to your GitHub repository URL

**Verify the connection:**
```bash
git remote -v
```

**You should see:**
```
origin  https://github.com/yourusername/ux-practice-lesson04.git (fetch)
origin  https://github.com/yourusername/ux-practice-lesson04.git (push)
```

**Success check:** Remote is connected

---

## Part 3: Push to GitHub (5 minutes)

### Authentication Setup (First Time Only)

GitHub needs to verify it's really you before you can push.

**When you try to push, you'll be prompted for:**
- Username: Your GitHub username
- Password: **NOT your GitHub password** - use a Personal Access Token

### Create Personal Access Token

**This is one-time setup:**

1. Go to GitHub → Settings (your profile, not repository)
2. Scroll down to "Developer settings" (bottom of left sidebar)
3. Click "Personal access tokens" → "Tokens (classic)"
4. Click "Generate new token" → "Generate new token (classic)"
5. Give it a name: "Git CLI access"
6. Expiration: 90 days (or whatever you prefer)
7. Select scopes: Check **"repo"** (gives full repo access)
8. Click "Generate token" at bottom
9. **Copy the token immediately** - you can't see it again!

**Save this token somewhere safe** (password manager, notes app)

---

### Push Your Commits

**Push to GitHub:**
```bash
git push -u origin main
```

**Breakdown:**
- `git push` = send commits
- `-u` = set upstream (remember this branch)
- `origin` = the remote we connected (GitHub)
- `main` = the branch name

**You'll be prompted:**
- Username: Your GitHub username
- Password: Paste your **personal access token** (not your password)

**After authentication succeeds:**
```
Counting objects: 15, done.
Delta compression using up to 8 threads.
Compressing objects: 100% (12/12), done.
Writing objects: 100% (15/15), 1.23 KiB | 1.23 MiB/s, done.
Total 15 (delta 3), reused 0 (delta 0)
To https://github.com/yourusername/ux-practice-lesson04.git
 * [new branch]      main -> main
Branch 'main' set up to track remote branch 'main' from 'origin'.
```

**What just happened:**
- All your local commits uploaded to GitHub
- Your entire Git history is now in the cloud
- GitHub is now synchronized with your computer

**Verify on GitHub:**
1. Refresh your repository page on GitHub
2. You should see your files
3. Click "commits" to see your commit history
4. Everything from Lesson 3 is now on GitHub!

**Success check:** Your files are visible on GitHub

---

## Part 4: Make Changes and Push Again (3 minutes)

### The Regular Workflow

Now that setup is done, this is your daily workflow.

**1. Make a change locally:**

```bash
cd ~/Desktop/lesson03-practice
code .
```

Open any file in VS Code and make an edit. Save it.

**2. Check status:**
```bash
git status
```

Should show the file as modified.

**3. Stage and commit:**
```bash
git add .
git commit -m "Updated file after connecting to GitHub"
```

**4. Push to GitHub:**
```bash
git push
```

No need for `-u origin main` anymore - Git remembers!

**5. Verify on GitHub:**
Refresh your repository page. New commit appears!

**This is the cycle you'll use constantly.**

---

## Part 5: Clone a Repository (3 minutes)

### What is Cloning?

Cloning = downloading an entire repository from GitHub to your computer.

**Use cases:**
- Getting a teammate's repository
- Working from a different computer
- Contributing to open source projects

### Clone Your Own Repository

**Navigate to a different location:**
```bash
cd ~/Desktop
mkdir github-clones
cd github-clones
```

**Get the clone URL from your GitHub repository:**
1. Go to your repository on GitHub
2. Click the green "Code" button
3. Copy the HTTPS URL

**Clone the repository:**
```bash
git clone https://github.com/yourusername/ux-practice-lesson04.git
```

**What happens:**
```
Cloning into 'ux-practice-lesson04'...
remote: Enumerating objects: 18, done.
remote: Counting objects: 100% (18/18), done.
remote: Compressing objects: 100% (15/15), done.
Receiving objects: 100% (18/18), done.
```

**Verify:**
```bash
cd ux-practice-lesson04
ls
git log --oneline
```

You should see all your files and commit history!

**What you have:**
- Original folder: `~/Desktop/lesson03-practice`
- Cloned folder: `~/Desktop/github-clones/ux-practice-lesson04`
- Both have same commits
- Both connected to same GitHub repo

**Success check:** Cloned repository has all your files and history

---

## Part 6: Pull Changes (2 minutes)

### What is Pulling?

Pulling = downloading new commits from GitHub to your computer.

**Use case:** Someone else pushed changes (or you pushed from another computer).

### Simulate This

**Make a change directly on GitHub:**

1. Go to your repository on GitHub
2. Click on any markdown file
3. Click the pencil icon (Edit)
4. Make any change to the file
5. Scroll down
6. Commit message: "Updated file directly on GitHub"
7. Click "Commit changes"

**Now GitHub has a commit your local computer doesn't have.**

**Pull the change:**
```bash
cd ~/Desktop/lesson03-practice
git pull
```

**You should see:**
```
remote: Enumerating objects: 5, done.
remote: Counting objects: 100% (5/5), done.
Updating abc123..def456
Fast-forward
 filename.md | 2 +-
 1 file changed, 1 insertion(+), 1 deletion(-)
```

**Check the file:**
Open the file you edited on GitHub. The change is now on your computer!

**This is how you get others' changes.**

**Success check:** Changes made on GitHub are now in your local files

---

## Part 7: Simple Merge Conflict (5 minutes)

### What is a Merge Conflict?

A conflict happens when:
- You change a file locally
- Someone changes the same file on GitHub
- Both try to edit the same lines
- Git doesn't know which version to keep

**Don't panic.** These are easy to resolve.

### Create a Conflict

**1. Edit locally (don't commit yet):**

```bash
cd ~/Desktop/lesson03-practice
code 03-lesson03-practice-repository.md
```

Add this line at the very top:
```
LOCAL CHANGE: This was added on my computer
```

Save but DON'T commit yet.

**2. Edit on GitHub:**

1. Go to your repository on GitHub
2. Open the same file: `03-lesson03-practice-repository.md`
3. Click Edit (pencil icon)
4. Add this at the very top:
```
GITHUB CHANGE: This was added on GitHub
```
5. Commit the change: "Added line on GitHub"

**3. Now commit your local change:**
```bash
git add .
git commit -m "Added line locally"
```

**4. Try to push:**
```bash
git push
```

**You'll see an error:**
```
! [rejected]        main -> main (fetch first)
error: failed to push some refs
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
```

**Translation:** GitHub has commits you don't have. You need to pull first.

**5. Pull to get GitHub's changes:**
```bash
git pull
```

**Now you'll see a conflict:**
```
Auto-merging 03-lesson03-practice-repository.md
CONFLICT (content): Merge conflict in 03-lesson03-practice-repository.md
Automatic merge failed; fix conflicts and then commit the result.
```

### Resolve the Conflict

**Open the file in VS Code:**

**You'll see something like:**
```markdown
<<<<<<< HEAD
LOCAL CHANGE: This was added on my computer
=======
GITHUB CHANGE: This was added on GitHub
>>>>>>> abc123
```

**This is a conflict marker showing both versions.**

**VS Code makes this easy with buttons:**
- "Accept Current Change" (your local version)
- "Accept Incoming Change" (GitHub's version)
- "Accept Both Changes" (keep both)

**For this exercise, click "Accept Both Changes"**

**Or manually edit to:**
```markdown
LOCAL CHANGE: This was added on my computer
GITHUB CHANGE: This was added on GitHub
```

**Remove all the conflict markers** (`<<<<<<<`, `=======`, `>>>>>>>`)

**Save the file.**

**Mark as resolved:**
```bash
git add 03-lesson03-practice-repository.md
git commit -m "Resolved merge conflict"
git push
```

**Success!** Conflict resolved and pushed to GitHub.

**This is all there is to resolving conflicts. Most of the time:**
- Read both versions
- Decide what to keep
- Remove conflict markers
- Commit the resolution

**Deep breath. You can do this. These happen, and you just handled one.**

---

## Tools to Help You

**Absolutely use any resource:**

### When Stuck

**Google:**
- "git push rejected"
- "how to resolve merge conflict git"
- "git pull vs git fetch"
- "github personal access token"

**AI Assistants:**
- "I'm trying to push to GitHub but getting rejected, what does this mean?"
- "How do I create a personal access token for GitHub?"
- "Explain git pull in simple terms"

### GitHub Documentation

- [GitHub Guides](https://guides.github.com)
- [Git Handbook](https://guides.github.com/introduction/git-handbook/)
- [Resolving Merge Conflicts](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/addressing-merge-conflicts)

### VS Code Git Integration

**VS Code helps with conflicts:**
- Shows conflict markers clearly
- Provides "Accept" buttons
- Highlights differences visually
- Makes resolution easier

**But learn the Terminal commands first** so you understand what's happening.

---

## Common Issues

### "Authentication failed"

**Problem:** Wrong username or token

**Fix:**
- Verify GitHub username is correct
- Make sure you're using personal access token, not password
- Check token has "repo" permissions
- Generate new token if needed

---

### "Repository not found"

**Problem:** URL is wrong or repo is private and you're not authenticated

**Fix:**
- Double-check repository URL
- Make sure you're signed into GitHub
- Verify repository exists on GitHub
- Check spelling of username and repo name

---

### "Failed to push some refs"

**Problem:** GitHub has commits you don't have locally

**Fix:**
```bash
git pull
# Resolve any conflicts if they appear
git push
```

**Always pull before pushing if you get this error.**

---

### "Working tree not clean"

**Problem:** You have uncommitted changes

**Fix:**
```bash
git status  # See what's changed
git add .   # Stage changes
git commit -m "Commit message"
git push    # Now push
```

**Or if you don't want the changes:**
```bash
git restore .  # Discard all changes
```

---

## Completion Checklist

You're done when you can:

- [ ] Create a repository on GitHub
- [ ] Connect local repo to GitHub (git remote add)
- [ ] Push commits to GitHub (git push)
- [ ] View your repository and commits on GitHub
- [ ] Clone a repository (git clone)
- [ ] Make changes locally and push them
- [ ] Make changes on GitHub and pull them
- [ ] Resolve a simple merge conflict
- [ ] Understand the push/pull workflow

**Bonus:**
- [ ] Created personal access token for authentication
- [ ] Can explain difference between local and remote
- [ ] Understand when to pull vs when to push
- [ ] Feel comfortable with conflict resolution

---

## What You Accomplished

**You just:**
- Put your version control in the cloud
- Enabled collaboration with teammates
- Created automatic backup of your work
- Learned the push/pull synchronization workflow
- Resolved your first merge conflict

**This is real GitHub usage.** Developers do exactly this every day.

---

## The Daily Workflow

**Going forward, this is your routine:**

**Morning (start of work):**
```bash
git pull  # Get latest changes
```

**During work (after making changes):**
```bash
git status
git add .
git commit -m "Description of what you did"
```

**End of day (or when ready to share):**
```bash
git push  # Send your commits to GitHub
```

**This cycle repeats endlessly.**

---

## Before Next Week

**Practice this workflow daily:**

1. Make a change to any file
2. Commit it locally
3. Push to GitHub
4. Verify it appears on GitHub

**Do this 5 times over the week.**

By Lesson 5, pushing to GitHub will feel as natural as saving a file.

---

## Next Week Preview

**Lesson 5: Collaboration Workflow**
- Working with branches
- Creating pull requests
- Reviewing others' work
- Team collaboration patterns
- Handling real-world conflicts

**Preparation:**
- Make sure push/pull feels comfortable
- Practice resolving conflicts
- Invite a teammate to your practice repo (optional)

---

## Understanding Branches (Preview)

You've been working on the "main" branch this whole time.

**Next lesson, you'll learn:**
- Creating feature branches
- Working on branches independently
- Merging branches
- Why teams use this workflow

**For now:** Just know that "main" is the primary branch, and there can be others.

---

## Encouragement

If merge conflicts felt scary, that's normal.

**Reality check:**
- Most conflicts are simple (like the one you just resolved)
- VS Code makes them visual and easy
- With practice, they take 30 seconds to resolve
- Complex conflicts are rare

**You handled one successfully. You can handle them all.**

---

## Security Reminder

**Never commit:**
- Passwords
- API keys
- Personal access tokens
- Private keys
- Sensitive user data

**Use .gitignore to exclude:**
- `.env` files
- `secrets.txt`
- `api-keys.txt`
- Any file with credentials

**If you accidentally commit secrets:**
1. Remove them from the file
2. Commit the removal
3. Rotate/change the secret immediately
4. See troubleshooting guide for history cleanup

---

## Questions or Stuck?

**Resources:**
- Solution files showing expected workflow
- GitHub documentation
- Team channel: [your channel]
- Office hours: [day/time]

**Authentication issues are the most common problem.** Don't struggle - ask for help with tokens.

---

## Final Thought

**You now have the cloud.**

Your work is backed up. Your team can access it. You can work from anywhere.

This is the foundation of modern collaborative development.

Next lesson: You'll learn how teams actually use this for real projects.

Excellent work. See you in Lesson 5.
