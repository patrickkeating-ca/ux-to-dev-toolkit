# Prerequisites Check - Lesson 1
## Verify Your Setup Before Starting

### Quick Setup Verification

Before starting Lesson 1's lesson, verify you have the required tools installed.

---

## 1. Visual Studio Code

**Check if installed:**

**Option 1: Spotlight Search**
1. Press Command + Space
2. Type "Visual Studio Code"
3. If it appears, you have it installed

**Option 2: Applications Folder**
1. Open Finder
2. Go to Applications
3. Look for "Visual Studio Code"

**If NOT installed:**
1. Go to [https://code.visualstudio.com](https://code.visualstudio.com)
2. Click "Download for Mac"
3. Open the downloaded file
4. Drag VS Code to Applications folder
5. Open it once to verify it works

**Test that it works:**
```bash
code --version
```

You should see version information. If you see "command not found", see troubleshooting below.

---

## 2. Terminal

**Check if available:**

Terminal comes pre-installed on Mac. You just need to find it.

**How to open:**
- Spotlight (Command + Space) → type "Terminal" → press Enter
- Or: Applications → Utilities → Terminal

**Verify it works:**
```bash
echo "Hello from Terminal"
```

You should see: `Hello from Terminal`

**If this works, you're good to go.**

---

## 3. Homebrew (Recommended)

Homebrew is a package manager for Mac. You'll need it for some developer tools.

**Check if installed:**
```bash
brew --version
```

**If you see a version number:**
Example: `Homebrew 4.2.0`
You're all set.

**If you see "command not found":**
You need to install Homebrew.

**To install Homebrew:**

1. Go to [https://brew.sh](https://brew.sh)
2. Copy the installation command (looks like `/bin/bash -c "$(curl...)"`)
3. Paste it into Terminal
4. Press Enter
5. Follow the prompts
6. Enter your Mac password when asked
7. Wait 5-10 minutes for installation

**After installation, verify:**
```bash
brew --version
```

---

## 4. GitHub Account

**Check if you have one:**
1. Go to [https://github.com](https://github.com)
2. Try to sign in

**If you can sign in:**
You're ready.

**If you don't have an account:**
1. Click "Sign up"
2. Follow the steps
3. Use your work email if this is for work projects
4. Verify your email address

---

## Troubleshooting

### "code --version" says "command not found"

VS Code is installed but Terminal doesn't know where it is.

**Fix:**
1. Open VS Code
2. Press Command + Shift + P (opens Command Palette)
3. Type "shell command"
4. Click "Shell Command: Install 'code' command in PATH"
5. Restart Terminal
6. Try `code --version` again

---

### Homebrew installation fails

**Common issues:**

**"Command Line Tools not installed"**
- Terminal will prompt you to install them
- Click Install and wait (takes 10-15 minutes)
- Then try Homebrew installation again

**Still stuck?**
- Copy the exact error message
- Google it
- Or ask in Mac Team channel

---

### Can't find Terminal

**Alternative way to open:**
1. Finder
2. Go to Applications
3. Open Utilities folder
4. Double-click Terminal

**Bookmark it:**
- Drag Terminal to your Dock for easy access

---

## Checklist

Before starting Lesson 1 lesson, verify:

- [ ] VS Code installed and opens
- [ ] Terminal opens
- [ ] `code --version` works in Terminal
- [ ] Homebrew installed (or installation in progress)
- [ ] GitHub account created and you can sign in

**If all checked:**
You're ready for Lesson 1!

**If missing items:**
Complete the setup steps above, then proceed to the lesson.

---

## Optional But Helpful

**Create a projects folder:**

It's helpful to have one place for all your practice work.

```bash
cd ~/Desktop
mkdir ux-github-practice
cd ux-github-practice
```

Now you have a dedicated space for these lessons.

**Note:** You'll see a new folder on your Desktop called ux-github-practice

---

## Time Expectations

**VS Code installation:** 5 minutes  
**Homebrew installation:** 10-15 minutes  
**GitHub account creation:** 5 minutes  
**Total setup time:** 20-30 minutes

This is one-time setup. Future lessons won't require this.

---

## Getting Help

**If stuck on setup:**
- IT department (for company computers)
- Team Slack channel
- Google the exact error message
- Ask an AI assistant: "How do I install VS Code on Mac?"

**Remember:** Setup is often the hardest part. Once this is done, the actual lessons are easier.

---

## Ready?

Once you've completed this checklist, proceed to `lesson01-instructions.md` to start the hands-on lesson.

You've got this.
