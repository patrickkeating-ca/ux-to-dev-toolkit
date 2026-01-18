# Lesson 1: Terminal & Markdown Basics
## 5-Minute Hands-On Lesson

### Before You Start

**You can't break anything permanently.** This is a practice exercise in a safe space. If something goes wrong, you can always start over.

**Time needed:** 5-10 minutes  
**What you'll learn:** Basic terminal navigation and markdown editing

---

## Prerequisites Check

Before starting this lesson, verify you have:

**Required:**
- [ ] Visual Studio Code installed
- [ ] GitHub account created
- [ ] Terminal app (comes with Mac)

**To check VS Code:**
1. Open Spotlight (⌘ + Space)
2. Type "Visual Studio Code"
3. You should see it in results

**If you don't see VS Code:** Download from [code.visualstudio.com](https://code.visualstudio.com)

**To check Homebrew (optional but recommended):**

**Note:** In Terminal, you can be in any directory to check things like this. You don't need to be on the Desktop. If you're in a project folder, this will still work.

```bash
brew --version
```

**If you see a version number:** You're good  
**If you see "command not found":** You'll need to install Homebrew

**Installing Homebrew (if needed):**
1. Go to [brew.sh](https://brew.sh)
2. Copy the install command
3. Paste in Terminal and press Enter
4. Follow the prompts (might take 5-10 minutes)

---

## Today's Goal

By the end of this lesson, you'll:
- Navigate folders using Terminal commands
- Create and edit files from the command line
- Fix broken markdown formatting
- Preview markdown in VS Code

**Note**
Terminal is persnickety. Case matters. Desktop and desktop are two different things to Terminal. If something's not working, double check the spelling and case.

---

## Part 1: Terminal Navigation (2 minutes)

### Exercise: Find Your Way Around

**Open Terminal:**
- Spotlight (⌘ + Space) → type "Terminal" → Enter

**Try these commands one at a time:**

```bash
# Where am I?
pwd

# What's here?
ls

# Go to Desktop
cd ~/Desktop

# Make a practice folder
mkdir lesson01-practice

# Go into it
cd lesson01-practice

# Confirm you're there
pwd
```

**You should see:** `/Users/YourName/Desktop/lesson01-practice`

**Success Check:** You created a folder and navigated into it.

---
	
## Part 2: Create Practice Files (1 minute)

**While still in `lesson01-practice` folder:**

```bash
# Create a markdown file
touch my-first-markdown.md

# Create a text file
touch notes.txt

# See what you made
ls
```

**You should see:** Both files listed

**Success Check:** You created files from Terminal.

---

## Part 3: Fix Broken Markdown (2 minutes)

### The Challenge

There's a file called `practice-broken-markdown.md` with formatting problems. Your job: fix it!

**Setup:**
1. Download `practice-broken-markdown.md` (in this lesson folder)
2. Move it to your `lesson01-practice` folder (on your desktop)
3. Open the entire folder in VS Code:

```bash
code .
```

The `.` means "current folder"

**In VS Code:**
1. Click `practice-broken-markdown.md` in the sidebar
2. Open preview: Click the preview icon (top right) OR press ⌘ + Shift + V
3. Split view: ⌘ + K then V (edit left, preview right)

**What's broken:**
- Headers need # symbols
- Lists need proper formatting
- Links are incomplete
- Some bold/italic is wrong

**Your task:** Fix the formatting so the preview looks correct.

**Compare to:** `solution-fixed-markdown.md` when you're done

**Success Check:** Your preview matches the solution file's preview.

**Save your progress**

---

## Tools to Help You

**Absolutely use any resource available:**

### Google/Search
- "markdown syntax cheat sheet"
- "how to make bold text in markdown"
- "markdown list format"

### AI Assistants
**Ask ChatGPT/Claude/Copilot:**
- "How do I create a heading in markdown?"
- "What's the syntax for a link in markdown?"
- "Show me how to make a bulleted list in markdown"

### VS Code
- Hover over text to see suggestions
- Right-click → "Format Document"
- Use Command Palette (⌘ + Shift + P) → search "markdown"

### Quick Reference
- [Markdown Guide](https://www.markdownguide.org/basic-syntax/)
- [GitHub Markdown Tutorial](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)

**Remember:** Developers Google things constantly. You should too!

---

## When You're Stuck

**If Terminal feels confusing:**
- Type `pwd` to see where you are
- Type `cd ~` to go back home
- Close Terminal and start fresh

**If VS Code won't open:**
- Try: File → Open Folder → select `lesson01-practice`
- Or: Drag the folder onto VS Code icon

**If markdown won't preview:**
- Make sure file ends in `.md`
- Try closing and reopening the file
- Install "Markdown All in One" extension

**If nothing makes sense:**
- Take a break
- Try again tomorrow
- Ask in [team channel]
- This IS hard the first time - that's normal

---

## Completion Checklist

You're done when you can check all these:

- [ ] Opened Terminal without fear
- [ ] Used `pwd`, `ls`, `cd` commands
- [ ] Created a folder with `mkdir`
- [ ] Created files with `touch`
- [ ] Opened a folder in VS Code using `code .`
- [ ] Fixed the broken markdown file
- [ ] Saw markdown preview render correctly
- [ ] Compared your solution to the answer

**Bonus:**
- [ ] Googled a markdown syntax question
- [ ] Asked an AI assistant for help
- [ ] Feel slightly less terrified of Terminal

---

## What You Accomplished

**You just:**
- Navigated your file system without Finder
- Created files without clicking
- Edited markdown with live preview
- Used VS Code like a developer

**This feels hard because it IS hard the first time.**

After Lesson 2, these commands will feel natural. After Lesson 4, you'll do them without thinking.

---

## Before Next Week

**Practice (5 minutes total):**
1. Open Terminal and navigate to a different folder
2. Create a new markdown file
3. Write something in it (your name, a list, anything)
4. Preview it in VS Code

**The more you do it, the less scary it gets.**

---

## Next Week Preview

**Lesson 2: VS Code Setup & Workflow**
- Installing essential extensions
- Keyboard shortcuts that save time
- Working with multiple files
- Using integrated terminal

**Preparation:** None needed - just complete this lesson's exercise.

---

## Encouragement

You're learning skills that took developers years to feel comfortable with. You're doing this in weeks.

Give yourself credit. Ask for help. Use every tool available.

**You've got this.**

---

## Questions or Stuck?

**Resources:**
- Lesson files: Check `solution-fixed-markdown.md`
- Team channel: [Your team Slack/channel]
- Office hours: [Day/Time]
- Troubleshooting: See main guide

**Remember:** There are no stupid questions. Everyone started exactly where you are.
