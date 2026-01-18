# Terminal Navigation Exercise
## Practice Your Command Line Skills

### Goal
Get comfortable navigating your file system using Terminal commands instead of Finder.

---

## Exercise 1: Basic Navigation

**Start fresh:**
1. Open Terminal
2. Type each command below, one at a time
3. Observe what happens after each command

```bash
# 1. Where am I right now?
pwd

# 2. What's in this location?
ls

# 3. Go to your home directory
cd ~

# 4. Confirm you're in your home directory
pwd

# 5. See what's in your home directory
ls
```

**What you should see:**
- `pwd` shows your current path (like /Users/YourName)
- `ls` shows folders like Desktop, Documents, Downloads

---

## Exercise 2: Navigate to Desktop

```bash
# Go to Desktop
cd ~/Desktop

# Confirm
pwd

# See what's there
ls
```

**Expected result:** You should see your Desktop folders and files listed

---

## Exercise 3: Create Practice Structure

Now create a folder structure for practice:

```bash
# Make sure you're on Desktop
cd ~/Desktop

# Create main folder
mkdir terminal-practice

# Go into it
cd terminal-practice

# Confirm location
pwd

# Create some subfolders
mkdir docs
mkdir images
mkdir notes

# See what you made
ls
```

**Expected result:** You should see three folders: docs, images, notes

---

## Exercise 4: Navigate Deeper

```bash
# Go into docs folder
cd docs

# Where are you now?
pwd

# Go back up one level
cd ..

# Where are you now?
pwd

# Go into images folder
cd images

# Go back home
cd ~

# Where are you?
pwd
```

**Practice tip:** Use `pwd` after every `cd` until you get comfortable

---

## Exercise 5: Create Files

```bash
# Go back to your practice folder
cd ~/Desktop/terminal-practice

# Go into docs
cd docs

# Create some files
touch research-notes.md
touch interview-summary.md
touch personas.md

# See your new files
ls

# Create a file in the parent folder without leaving docs
touch ../notes/meeting-notes.txt

# Check that it worked - go to notes and list
cd ../notes
ls
```

**Expected result:** You should see meeting-notes.txt in the notes folder

---

## Exercise 6: Full Path Navigation

```bash
# From anywhere, jump directly to a specific location
cd ~/Desktop/terminal-practice/images

# Confirm
pwd

# Jump to Documents
cd ~/Documents

# Jump back to practice folder
cd ~/Desktop/terminal-practice

# List everything including hidden files
ls -la
```

**Note:** The `-la` flag shows hidden files (those starting with `.`)

---

## Exercise 7: Tab Completion

This is a time-saver:

```bash
# Go home
cd ~

# Type this but DON'T press Enter yet:
cd Des

# Now press Tab
# Terminal should auto-complete to "Desktop"

# Try it with your practice folder
cd ~/Desktop/ter[Tab]
# Should complete to "terminal-practice"
```

**Practice this!** Tab completion saves so much typing.

---

## Exercise 8: Command History

```bash
# Press the Up Arrow key
# You'll see your previous commands

# Keep pressing Up to scroll through history

# Press Down to go forward in history

# When you find a command you want to run again, press Enter
```

**Tip:** This is faster than re-typing commands

---

## Self-Check Quiz

Without looking at the answers, try to answer:

1. What command shows your current location?
2. What command lists files in current folder?
3. How do you go up one folder level?
4. How do you go to your home directory?
5. What command creates a new folder?
6. What command creates a new file?

**Answers:**
1. `pwd`
2. `ls`
3. `cd ..`
4. `cd ~` or `cd`
5. `mkdir [foldername]`
6. `touch [filename]`

---

## Common Mistakes to Avoid

**Mistake 1: Forgetting where you are**
- **Solution:** Use `pwd` constantly at first
- **Tip:** Look at your Terminal prompt - it often shows current location

**Mistake 2: Spaces in folder names**
- `cd my folder` won't work
- `cd my\ folder` or `cd "my folder"` will work
- **Better:** Use hyphens: `my-folder`

**Mistake 3: Case sensitivity**
- `cd Desktop` works
- `cd desktop` does NOT work
- **Remember:** Mac is case-sensitive in Terminal

**Mistake 4: Wrong slashes**
- Use forward slash: `/`
- NOT backslash: `\`

---

## Cleanup (Optional)

When you're done practicing, you can delete the practice folder:

```bash
# Go to Desktop
cd ~/Desktop

# Delete the practice folder and everything in it
rm -r terminal-practice

# Confirm it's gone
ls
```

**Warning:** `rm -r` permanently deletes. There's no undo!

---

## Challenge: Create This Structure

Try to create this folder structure using only Terminal:

```
my-ux-project/
├── docs/
│   ├── discovery/
│   ├── design/
│   └── requirements/
├── src/
└── analysis/
```

**Commands you'll need:**
- `mkdir`
- `cd`
- `touch` (if you want to add files)

**Hint:** Create parent folder first, then navigate into it to create subfolders.

Try it yourself before looking at the solution!

---

## Solution to Challenge

```bash
# Create main folder
mkdir my-ux-project

# Go into it
cd my-ux-project

# Create top-level folders
mkdir docs src analysis

# Go into docs
cd docs

# Create subfolders inside docs
mkdir discovery design requirements

# Go back to main project folder
cd ..

# Or do it all with one command:
mkdir -p my-ux-project/docs/{discovery,design,requirements}
mkdir -p my-ux-project/src
mkdir -p my-ux-project/analysis
```

**Note:** The `-p` flag creates parent directories if needed

---

## Completion Checklist

You've completed this exercise when you can:

- [ ] Navigate to any folder using `cd`
- [ ] Check current location with `pwd`
- [ ] List folder contents with `ls`
- [ ] Create folders with `mkdir`
- [ ] Create files with `touch`
- [ ] Use tab completion
- [ ] Navigate up levels with `cd ..`
- [ ] Go home with `cd ~`

**If you can check all these boxes, you're ready to move forward!**

---

## Time Spent

Recommended: 10-15 minutes

If you need more time, that's completely normal. The goal is comfort, not speed.

---

## Next Practice

Tomorrow, try:
1. Navigate to a real project folder
2. Create a markdown file
3. Open it in VS Code using `code filename.md`

Small daily practice builds muscle memory.

---

## Remember

Every developer started exactly where you are. Terminal feels foreign because it IS foreign.

Give it a week of daily practice. You'll be amazed how natural it becomes.
