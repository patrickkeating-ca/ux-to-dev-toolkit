**Reading these instructions**
If you're viewing this in a text editor, you'll see formatting codes like ```bash that won't appear in a markdown reader.

**Takeaway**
If you see 'bash' or 'zsh', it means it's a 'shell', which is another name for the Terminal.

If you're looking at this in a text editor, this might be a little confusing.

### Example	
```bash
cd ~/Desktop
mkdir ux-github-practice
cd ux-github-practice
```
Important: Don't type ```bash into the terminal. It's just formatting code. When you view this in a markdown reader (instructions provided in VS Code), you'll see a clean highlighted code block instead.

The expectation is that you will enter these into the Terminal one line at a time, not copy and paste everything. 


What it means
```bash
	What it means: In a Terminal, enter the following directions. 
1st step: Type cd ~/Desktop 
	What it means: Navigate (change directory) to your Desktop
2nd step: Type mkdir ux-github-practice
	What it means: You're on the Desktop, make a directory (folder) called ux-github-practice
3rd step: Type cd ux-github-practice 
	What it means: Navigate (change directory) to your new folder.
```
	What it means: This will tell the markdown reader that this is the end of the 'terminal' code.


# Lesson 1 Express: Terminal & Markdown Basics
## 10-Minute Quick Start

Skip the full lesson if you're short on time. Here's the bare minimum to get functional.

---

## Goal

Learn just enough Terminal and Markdown to complete the remaining coursework. You can come back later for the comprehensive version.

**Time commitment:** 10-15 minutes

---

## Part 1: Terminal Essentials (5 minutes)

### The Only 5 Commands You Need Right Now

Open Terminal (Command + Space, type "Terminal", press Enter)

**1. Where am I?**
```bash
pwd
```
Shows your current location.

**2. What's here?**
```bash
ls
```
Lists files and folders.

**3. Go to Desktop**
```bash
cd ~/Desktop
```
Navigate to Desktop (you'll use this constantly).

**4. Create a folder**
```bash
mkdir practice
```
Makes a new folder called "practice".

**5. Go into that folder**
```bash
cd practice
```
Moves you into the folder.

**That's it. You now know enough Terminal for this course.**

---

## Part 2: Markdown Essentials (5 minutes)

### The Only Syntax You Need Right Now

**Headings:**
```markdown
# Big Heading
## Medium Heading
### Small Heading
```

**Bold and Italic:**
```markdown
**bold text**
*italic text*
```

**Lists:**
```markdown
- Item one
- Item two
- Item three
```

**Links:**
```markdown
[Link text](https://url.com)
```

**That's it. 90% of what you'll write uses these.**

---

## Quick Practice (5 minutes)

**Create a test file:**
```bash
cd ~/Desktop
mkdir markdown-test
cd markdown-test
touch test.md
code test.md
```

**In VS Code, type:**
```markdown
# My First Markdown File

This is **bold** and this is *italic*.

## Things I Need to Learn
- Git basics
- GitHub
- Collaboration

[Google](https://google.com)
```

**Save it (Command + S).**

**Preview it:**
- Press Command + Shift + V
- See your formatted document!

**Done. You know enough markdown.**

---

## What You're Skipping

The full Lesson 1 lesson includes:
- More Terminal commands
- File manipulation
- Markdown tables and advanced formatting
- Extended practice exercises
- Troubleshooting guide

**You can come back to these later if needed.**

---

## When to Return to Full Lesson 1

Come back to the comprehensive version if:
- You get stuck in later weeks and need Terminal refresher
- You want to learn more Markdown formatting
- You're creating professional documentation
- You have time to practice properly

**For now, you know enough. Move to Lesson 2.**

---

## AI Prompt for Custom Learning

If you want personalized guidance, ask ChatGPT/Claude/Copilot:

```
I'm a UX professional learning Terminal and Markdown for Git workflows. 
I have 15 minutes total. What are the essential commands and syntax I 
absolutely must know to get started? Give me just the minimum viable 
knowledge to be functional.
```

---

## Next Step

You're ready for Lesson 2 Express. The full lessons are always available when you have more time.

**Time saved: ~20-30 minutes**
