# Lesson 2: VS Code Setup & Workflow
## 5-Minute Hands-On Lesson

### What You'll Learn

By the end of this lesson, you'll:
- Install Live Server extension for HTML/web development
- Use keyboard shortcuts to work faster
- Manage multiple files efficiently
- Use the integrated terminal
- Master markdown preview features

**Time needed:** 10-15 minutes

---

## Part 1: Install One Essential Extension (3 minutes)

VS Code comes with powerful built-in features for markdown editing. We'll add just one extension for working with HTML and dynamic content.

### Opening Extensions Panel

**Three ways:**
1. Click the Extensions icon in left sidebar (looks like blocks)
2. Press Command + Shift + X
3. View menu → Extensions

### The One Extension You Need

**Live Server**
- Search for: "Live Server"
- Publisher: Ritwick Dey
- Click "Install"
- **Why:** Preview HTML and dynamic content in real-time with auto-reload
- **Future use:** Essential for Angular, React, and other web development frameworks

### Verify Installation

1. Click Extensions icon again
2. You should see "INSTALLED" section
3. Live Server should be listed there

**Success check:** Live Server installed without errors

### Built-in VS Code Features

**For markdown editing, you don't need extensions!** VS Code includes:
- Markdown preview (Command + Shift + V)
- Side-by-side editing (Command + K, then V)
- Syntax highlighting
- Auto-completion
- Keyboard shortcuts

**Philosophy:** Use built-in features first. Only add extensions when you need specific functionality VS Code doesn't provide.

---

## Part 2: Open Your Practice Folder (1 minute)

### The Right Way to Open Projects

**From Terminal:**
```bash
cd ~/Desktop/lesson02-practice
code .
```

**Or from VS Code:**
1. File → Open Folder
2. Navigate to Desktop → lesson02-practice
3. Click "Open"

**What you should see:**
- Left sidebar shows folder contents
- All practice files visible
- Bottom status bar shows folder name

**Why this matters:** Opening a folder (not individual files) gives you full VS Code features.

---

## Part 3: Essential Keyboard Shortcuts (3 minutes)

### Practice These Shortcuts

Open `E-lesson02-practice-shortcuts.md` and follow along.

**Basic Navigation:**

| Shortcut | Action | Try It |
|----------|--------|--------|
| Command + P | Quick Open (find any file) | Press it, type a filename |
| Command + Shift + P | Command Palette | Opens all VS Code commands |
| Command + B | Toggle sidebar | Make more room for editing |
| Command + J | Toggle terminal | Show/hide terminal panel |
| Control + ` | Also toggles terminal | Backtick key (left of 1) |

**Editing:**

| Shortcut | Action | Try It |
|----------|--------|--------|
| Command + S | Save file | Save after every edit |
| Command + W | Close file | Close current tab |
| Command + / | Comment/uncomment | Toggle markdown comments |
| Command + D | Select next match | Multi-cursor magic |
| Option + Up/Down | Move line | Reorder lines quickly |

### Practice Exercise

1. Open `E-lesson02-practice-shortcuts.md`
2. Try each shortcut as you read about it
3. Don't memorize - just try them
4. The ones you use will stick naturally

**Success check:** You tried at least 5 shortcuts and they worked

---

## Part 4: Working with Multiple Files (2 minutes)

### Split View

**Open two files side by side:**

1. Open `D-lesson02-practice-document.md`
2. Drag the tab to the right side of the editor
3. Or: Right-click tab → "Split Right"
4. Or: Command + \ (backslash)

**Now you can:**
- Edit one file while viewing another
- Compare before/after versions
- Reference one document while writing another

### Quick File Switching

**Command + P then type filename**
- Faster than clicking through file tree
- Fuzzy search works (type "prac" finds "practice-document")

**Command + Tab**
- Switch between recently used files
- Like Alt+Tab for files instead of apps

**Practice:**
1. Open 3 different files
2. Use Command + P to jump between them
3. Try split view with two files

**Success check:** You can navigate between files without using mouse

---

## Part 5: Integrated Terminal (2 minutes)

### Why Use Integrated Terminal

Instead of switching between Terminal app and VS Code:
- Terminal lives inside VS Code
- Already in the right directory
- See code and terminal output together

### Opening Terminal

**Three ways:**
1. Control + ` (backtick)
2. Command + J
3. View → Terminal

**What you see:**
- Terminal panel appears at bottom
- Already in your project folder
- Same commands as Terminal app

### Try It

**With terminal open in VS Code:**
```bash
# Check where you are
pwd

# List files
ls

# Create a new file
touch test-from-terminal.md

# See it appear in sidebar immediately
```

**The file appears in VS Code's file tree instantly.**

### Multiple Terminals

1. Click the + icon in terminal panel
2. Opens new terminal tab
3. Useful for running server + using git simultaneously

**Practice:**
1. Open integrated terminal
2. Run `ls` to see your files
3. Create a test file with `touch`
4. Watch it appear in sidebar

**Success check:** Terminal works inside VS Code

---

## Part 6: Markdown Preview Mastery (2 minutes)

### Preview Options

**Built-in preview:**
- Command + Shift + V: Preview in new tab
- Command + K then V: Side-by-side preview

Both shortcuts use VS Code's built-in markdown preview - no extensions needed!

### Side-by-Side Editing

**Best workflow:**
1. Open your markdown file
2. Command + K then V (side-by-side preview)
3. Edit on left, see live preview on right
4. Changes update instantly

**Try it with `D-lesson02-practice-document.md`:**
1. Open the file
2. Command + K, V
3. Make an edit (add bold text)
4. Watch preview update

### Preview Scroll Sync

**Both sides scroll together:**
- Edit at top, preview shows top
- Scroll preview, edit pane follows
- Makes long documents easier to work with

**Practice:**
1. Open any markdown file
2. Enable side-by-side preview
3. Add a heading
4. Make some text bold
5. Create a list
6. Watch it all render live

**Success check:** You can edit with live preview and it updates as you type

---

## Part 7: Customizing Settings (2 minutes)

### Open Settings

**Command + ,** (Command + comma)

Or: Code → Settings → Settings

### Useful Settings to Change

**Search for each and adjust:**

**Auto Save:**
- Search: "auto save"
- Change to: "afterDelay"
- **Why:** Saves automatically after you stop typing

**Font Size:**
- Search: "font size"
- Adjust to your preference (default is 12)
- **Why:** Make text comfortable to read

**Word Wrap:**
- Search: "word wrap"
- Change to: "on"
- **Why:** Long lines wrap instead of scrolling

**Format on Save:**
- Search: "format on save"
- Check the box
- **Why:** Auto-formats when you save (works with built-in formatters)

### Apply Settings

Changes take effect immediately. Try opening a markdown file to see word wrap working.

**Practice:**
1. Open settings (Command + ,)
2. Enable auto save
3. Make text bigger or smaller
4. Turn on word wrap
5. Close settings

**Success check:** Settings changed and you can see the difference

---

## Part 8: Practice Exercise - Edit the Document (3 minutes)

### The Challenge

Open `D-lesson02-practice-document.md` and improve it using what you learned:

**Tasks:**
1. Open file with side-by-side preview
2. Fix any formatting issues
3. Use keyboard shortcuts (not mouse) for:
   - Making text bold
   - Creating headings
   - Saving file
4. Use Command + P to switch files at least once
5. Use integrated terminal to check file still exists

**Requirements:**
- Preview must be open while editing
- Use at least 3 keyboard shortcuts
- File should look professional when done

**Compare your result to `F-lesson02-solution-document.md`**

Don't worry about matching exactly - focus on using the tools.

**Success check:** You used VS Code features (not just typing) to improve the document

---

## Tools to Help You

**Absolutely use any resource:**

### For VS Code Questions

**Google:**
- "VS Code keyboard shortcuts Mac"
- "VS Code markdown preview"
- "VS Code built-in features"

**AI Assistants:**
- "What's the keyboard shortcut for [action] in VS Code?"
- "How do I split the editor in VS Code?"
- "How do I use VS Code's built-in markdown preview?"

### For Markdown

**Use built-in features:**
- VS Code adds auto-complete for markdown
- Type `#` for headings
- Type `-` or `*` for lists
- Use preview to verify formatting

**Command Palette (Command + Shift + P):**
- Type what you want to do
- VS Code finds the command
- Example: Type "format" to find formatting options

### Quick Reference

**VS Code Shortcuts:**
[https://code.visualstudio.com/shortcuts/keyboard-shortcuts-macos.pdf](https://code.visualstudio.com/shortcuts/keyboard-shortcuts-macos.pdf)

**Markdown Guide:**
[https://www.markdownguide.org/basic-syntax/](https://www.markdownguide.org/basic-syntax/)

**Remember:** Developers constantly look up shortcuts and commands. So should you.

---

## When You're Stuck

**Extension won't install:**
- Check internet connection
- Restart VS Code
- Try installing again

**Shortcut doesn't work:**
- Make sure you're focused in the right panel (click in editor first)
- Some shortcuts need a file open
- Check if another app is using the same shortcut

**Preview not showing:**
- Make sure file ends in `.md`
- Try closing and reopening preview
- Use Command + Shift + V for built-in preview

**Terminal won't open:**
- Try View → Terminal
- Check if another panel is maximized (double-click to restore)
- Restart VS Code

**Can't remember shortcuts:**
- That's normal! Use Command Palette (Command + Shift + P) instead
- Type what you want, it'll show the shortcut
- You'll memorize the ones you use often

---

## Completion Checklist

You're done when you can:

- [ ] Install VS Code extensions
- [ ] Open a folder (not just files) in VS Code
- [ ] Use Command + P to find files quickly
- [ ] Open integrated terminal with Control + `
- [ ] Enable side-by-side markdown preview
- [ ] Use at least 5 keyboard shortcuts
- [ ] Split editor to view two files
- [ ] Change VS Code settings
- [ ] Edit markdown with live preview
- [ ] Feel more comfortable in VS Code than a basic text editor

**Bonus:**
- [ ] Customized settings to your preference
- [ ] Tried all shortcuts in the practice document
- [ ] Used Command Palette to discover new commands
- [ ] Can work without touching mouse for 30 seconds

---

## What You Accomplished

**You just:**
- Transformed VS Code into a markdown powerhouse
- Learned shortcuts that save hours over time
- Set up a professional editing environment
- Integrated terminal into your workflow

**This lesson's theme:** Tools make the work easier.

Next lesson, these tools become automatic and you'll focus on Git itself.

---

## Before Next Week

**Daily practice (2 minutes):**
1. Open VS Code
2. Use Command + P to open a file
3. Edit something using keyboard shortcuts
4. Save with Command + S
5. Close with Command + W

**Do this for 5 days straight.**

The shortcuts will become muscle memory.

---

## Next Week Preview

**Lesson 3: Git Basics (Local)**
- Initialize a repository
- Make commits
- Check status
- View history
- Understand what Git is actually doing

**Preparation:** 
- Make sure this lesson's shortcuts feel natural
- Practice terminal navigation from Lesson 1
- Get comfortable working in VS Code

---

## Encouragement

Keyboard shortcuts feel awkward at first. Your hand will reach for the mouse. That's normal.

By Lesson 4, you'll be flying through files without thinking about it.

Give yourself time. Use the Command Palette when you forget shortcuts.

**You're building skills that compound.**

---

## Questions or Stuck?

**Resources:**
- Solution files in lesson folder
- VS Code documentation: [code.visualstudio.com/docs](https://code.visualstudio.com/docs)
- Team channel: [your channel]
- Office hours: [day/time]

**Don't struggle alone.** These tools have learning curves. Ask for help.

---

## Final Note

**You now have a professional text editor setup.**

Many developers use this exact configuration. You're working with real tools, not training-wheel versions.

That's worth celebrating.

See you next lesson for Git!
