# Lesson 6 Express: Real Project Setup
## 20-Minute Quick Start

Create a professional UX project repository. Fast version.

---

## Goal

Set up a real, portfolio-ready UX project repository with proper structure. Skip the extended explanations.

**Time commitment:** 20-30 minutes for initial setup

**Note:** This creates the foundation. You'll populate it with real content over time.

---

## Part 1: Create Project Structure (10 minutes)

### Basic Setup

**Create and navigate to project:**
```bash
cd ~/Desktop
mkdir ux-project-name
cd ux-project-name
git init
```

**Create essential folders:**
```bash
mkdir docs
mkdir docs/discovery
mkdir docs/requirements
mkdir docs/design
mkdir research
mkdir design
mkdir handoff
```

**Create core files:**
```bash
touch README.md
touch .gitignore
touch docs/PRD.md
```

---

### Essential .gitignore

**Create .gitignore with this content:**
```bash
cat > .gitignore << 'EOF'
# Mac system files
.DS_Store

# Temporary files
*.tmp
*.temp

# Large design files (link to these instead)
*.psd
*.fig

# Sensitive information
secrets.txt
api-keys.txt
EOF
```

---

### Minimal README

**Create README.md with this template:**
```bash
cat > README.md << 'EOF'
# Project Name

Brief description of the UX project.

## Quick Start

- **Research findings:** [docs/discovery/](docs/discovery/)
- **Requirements:** [docs/requirements/](docs/requirements/)
- **Design files:** [design/](design/)
- **Handoff materials:** [handoff/](handoff/)

## Project Status

In progress - [Current phase]

## Team

- **UX Lead:** Your Name
- **Stakeholder:** Name

## Last Updated

[Date]
EOF
```

---

### Minimal PRD

**Create docs/PRD.md:**
```bash
cat > docs/PRD.md << 'EOF'
# Product Requirements Document

## Project Overview

[Brief description of what you're building/designing]

## Goals

1. Goal one
2. Goal two
3. Goal three

## Success Metrics

- Metric 1
- Metric 2

## Timeline

- Start: [Date]
- Target completion: [Date]

## Stakeholders

- Primary: [Name]
- Secondary: [Names]
EOF
```

---

## Bridging the Gap: Converting Ideas to Structure

### The UX-to-Dev Translation Challenge

As a UX professional working with developers, you'll often receive unstructured notes, meeting transcripts, or stakeholder feedback that needs to be organized into clear requirements.

**AI can help you structure this information professionally.**

### Using AI to Create PRDs

**The scenario:**
You have hodgepodge notes from meetings, stakeholder emails, and your own ideas. You need a structured Product Requirements Document (PRD).

**AI Prompt to use:**
```
I have the following notes from a project [paste your unorganized notes].

Please organize this into a structured PRD (Product Requirements Document) with:
- Clear project overview
- User stories in the format "As a [role], I want to [action] so that [benefit]"
- Acceptance criteria for each requirement
- Success metrics
- Timeline considerations

Make it professional and ready to share with developers.
```

**What you'll get:**
- Organized requirements
- Proper user story format
- Clear acceptance criteria (AC)
- Ready-to-share documentation

**Practice this workflow:**
1. Collect messy notes from meetings/research
2. Use AI to structure them into PRD format
3. Review and refine the output
4. Commit the PRD to your repository
5. Share with team via GitHub

**This is the bridge:** Taking UX insights and translating them into developer-ready documentation.

---

## Part 2: Initial Commit (3 minutes)

**Add everything:**
```bash
git add .
git status
```

Verify files are staged (green).

**Commit:**
```bash
git commit -m "Initial project setup - folder structure and documentation"
```

---

## Part 3: Push to GitHub (5 minutes)

### Create GitHub Repository

1. GitHub → **+** → New repository
2. Name it same as your project folder
3. **Private**
4. **Don't** initialize with anything
5. Create repository

### Connect and Push

```bash
git remote add origin https://github.com/YOUR-USERNAME/ux-project-name.git
git push -u origin main
```

**Enter:**
- Username: Your GitHub username
- Password: Your personal access token

**Verify on GitHub:** Files should appear.

---

## Part 4: Your First Feature Branch (5 minutes)

**Add some real content:**

```bash
git checkout -b docs/add-research-plan
```

**Create a research plan:**
```bash
cat > docs/discovery/research-plan.md << 'EOF'
# Research Plan

## Research Questions

1. Question one
2. Question two
3. Question three

## Methods

- User interviews (n=8)
- Usability testing (n=6)

## Timeline

- Recruiting: Lesson 1
- Sessions: Lesson 2-3
- Analysis: Lesson 4
EOF
```

**Commit and push:**
```bash
git add .
git commit -m "Added initial research plan"
git push -u origin docs/add-research-plan
```

**Create PR on GitHub:**
1. Go to repository
2. "Compare & pull request"
3. Create, review, merge
4. Delete branch on GitHub

**Update local:**
```bash
git checkout main
git pull
git branch -d docs/add-research-plan
```

**Your project is live and you've practiced the workflow!**

---

## Your Project Structure

```
ux-project-name/
├── README.md
├── .gitignore
├── docs/
│   ├── PRD.md
│   ├── discovery/
│   │   └── research-plan.md
│   ├── requirements/
│   └── design/
├── research/
├── design/
└── handoff/
```

**Ready to populate with real work.**

---

## What You're Skipping

The full Lesson 6 lesson includes:
- Extended folder structure
- Detailed README templates
- Team collaboration setup
- GitHub Issues and Projects
- PLATFORM.md documentation
- Decision log setup
- Comprehensive examples

**Come back when you need these.**

---

## When to Return to Full Lesson 6

Return to comprehensive version when:
- You're setting up a real team project
- You need GitHub project boards
- You want detailed documentation templates
- You're presenting to stakeholders

**For now, you have a working repository.**

---

## Next Steps

### Populate Your Repository

**Add real content over time:**

1. **Research findings** → `docs/discovery/`
2. **User personas** → `docs/requirements/`
3. **Wireframes** (links or small files) → `design/`
4. **Handoff specs** → `handoff/`

**Use the branch workflow for each addition:**
```bash
git checkout -b feature/add-personas
# Add content
git add .
git commit -m "Added user personas"
git push -u origin feature/add-personas
# Create PR, merge
```

---

### Maintain the Repository

**Update README.md regularly:**
- Current project status
- Recent additions
- Next milestones

**Commit often:**
- After completing research
- After design decisions
- After stakeholder meetings

**Keep it current:**
- Living documentation
- Always up-to-date
- Portfolio-ready

---

## AI Prompt for Custom Learning

Ask ChatGPT/Claude/Copilot:

```
I'm setting up a UX project repository on GitHub. I have 30 minutes. 
What folder structure should I use for UX documentation, research, 
and design files? What essential files do I need (README, etc.)? 
Give me a minimal but professional setup.
```

---

## Cheat Sheet

```bash
# Start new project
mkdir project-name
cd project-name
git init

# Create structure
mkdir docs research design handoff

# Initial commit
git add .
git commit -m "Initial setup"

# Push to GitHub
git remote add origin URL
git push -u origin main

# For each addition:
git checkout -b feature/name
# Add content
git add .
git commit -m "description"
git push -u origin feature/name
# PR on GitHub, merge
git checkout main && git pull
```

---

## Critical Understanding

**You now have:**
- Professional UX project structure
- Version controlled documentation
- Collaborative workflow
- Portfolio piece

**Continue:**
- Add real work to the repository
- Practice the branch workflow
- Keep documentation current
- Share with stakeholders via GitHub URL

---

## Completion

**Congratulations!** You've completed the express version of all 6 lessons.

**Total time investment:** ~75-90 minutes vs. 15-20 hours for full program

**You can now:**
- Use Terminal basics
- Work in VS Code
- Track files with Git
- Collaborate via GitHub
- Use branches and PRs
- Maintain professional repositories

**What's next:**
- Practice daily
- Apply to real work
- Return to full lessons when needed
- Help others learn

**Time saved: ~13-18 hours**

**Trade-off:** Less depth, more practice needed, return for details when required

---

## When to Take Full Program

Consider the comprehensive 6-lesson program if:
- You want deep understanding
- You're training a team
- You need to troubleshoot issues
- You want portfolio-ready skills
- You have 15-20 hours available
- You prefer thorough learning

**Express version gets you functional. Full program makes you proficient.**

Both are valuable depending on your goals and time constraints.

---

## The Full Picture: Why You Learned the Basics First

### You Made It To The End - Now Use AI

**Important realization:**
We took you all the way through Git, GitHub, branches, and PRs manually for a reason: **You need to understand the basics before letting AI do it for you.**

### Why Learn the Hard Way?

**AI will do all of this for you**, but you need to:
- **Supervise:** Make sure the AI is doing the right thing
- **Troubleshoot:** Fix issues when AI makes mistakes
- **Judge quality:** Know when AI's suggestion is good vs. bad
- **Work faster:** Sometimes manual is quicker than explaining to AI

**You can't manage what you don't understand.**

### How to Use AI for Git Workflows

Now that you understand the fundamentals, here are AI prompts to speed up your work:

#### Git Commands

**Ask AI to:**
```
"Show me the Git command to [create a new branch / merge branches / view commit history / undo last commit]"

"Explain what this Git command does: git rebase -i HEAD~3"

"I want to [describe what you want]. What Git commands do I need?"
```

#### Commit Messages

**Ask AI to:**
```
"Here are my changes [paste git diff output]. Write a clear, professional commit message."

"Review these commit messages and suggest improvements: [paste git log output]"
```

#### Branching Strategy

**Ask AI to:**
```
"I'm working on [describe project]. What branching strategy should I use? I'm a solo developer / on a team of 5."

"Should I create a branch for this change: [describe change]? Or commit directly to main?"
```

#### Documentation

**Ask AI to:**
```
"Generate a README for my project based on these files: [list files and brief description]"

"Create a Pull Request description for these changes: [paste git diff or describe changes]"

"Explain this Git error message and how to fix it: [paste error]"
```

#### Learning and Troubleshooting

**Ask AI to:**
```
"Explain [Git concept] in simple terms with a real-world analogy"

"I'm trying to [task] but getting [error]. What's wrong and how do I fix it?"

"What's the difference between git merge and git rebase?"

"Show me 5 Git commands every developer should know with examples"
```

### Git Command Quick Reference

**Common commands AI can help you remember:**

```bash
# Branch operations
git branch                     # List branches
git branch feature-name        # Create branch
git checkout feature-name      # Switch to branch
git checkout -b feature-name   # Create and switch in one command
git merge feature-name         # Merge branch into current branch
git branch -d feature-name     # Delete branch

# Viewing history
git log --oneline              # Compact history
git log --graph                # Visual branch history
git show abc123                # Show specific commit
git diff                       # Show unstaged changes

# Undoing changes
git restore file.txt           # Discard changes to file
git reset --soft HEAD~1        # Undo commit, keep changes staged
git reset --hard HEAD~1        # Undo commit, discard changes (careful!)
git revert abc123              # Create new commit that undoes abc123

# Remote operations
git remote -v                  # View remote connections
git fetch                      # Download remote changes (don't merge)
git pull                       # Fetch and merge remote changes
git push                       # Upload local commits to remote
git push -u origin branch-name # Push and set upstream tracking

# Status and info
git status                     # Current state
git log                        # Commit history
git remote show origin         # Show remote details
```

**Instead of memorizing, ask AI when you need a command.**

### The Efficient Workflow

**1. Understand the concept** (you did this in Weeks 1-6)
**2. Use AI for syntax and commands** (do this going forward)
**3. Review AI's suggestions** (using your knowledge from this course)
**4. Build your own reference** (save useful prompts and commands)

### What You Should and Shouldn't Delegate to AI

**✅ Good to ask AI:**
- Command syntax and flags
- Explaining error messages
- Generating documentation templates
- Suggesting commit messages from diffs
- Best practices for your specific scenario
- Alternative approaches to problems

**⚠️ Be careful with AI:**
- Destructive operations (reset --hard, force push)
- Commands you don't understand (read the explanation first)
- Security-related decisions (.gitignore for secrets)
- Team workflow changes (discuss with team first)

### Your Next Steps

**Continue learning:**
1. **Practice daily** with real projects
2. **Use AI as a pair programmer** to speed up your work
3. **Read AI explanations** to deepen understanding
4. **Experiment safely** knowing you can always revert
5. **Help others** by explaining concepts you've learned

**Remember:** The goal isn't to memorize commands. The goal is to understand version control concepts and know how to find the commands you need (via AI, docs, or reference materials).

### Final Encouragement

**You now have:**
- ✅ Terminal proficiency
- ✅ VS Code skills
- ✅ Git fundamentals
- ✅ GitHub collaboration experience
- ✅ Branch workflow knowledge
- ✅ Professional project setup abilities
- ✅ Understanding to effectively use AI tools

**What this means:**
You can contribute to developer projects, manage UX documentation professionally, and collaborate using industry-standard tools.

**Time investment:** 75-90 minutes for express track
**Value:** Career-changing skills that bridge UX and development

**Welcome to the dev workflow. You belong here.**

---

## Questions or Want to Go Deeper?

**Full program available:**
If you want deeper understanding of any topic, return to the comprehensive version:
- `C-week*-instructions.md` files have 1-3 hour detailed lessons
- Practice exercises in `D-*` and `E-*` files
- Solutions in `F-*` files for reference

**Community resources:**
- GitHub Discussions: Ask questions, share progress
- Office hours: [schedule if applicable]
- Team channel: [team communication link]

**Keep learning:**
Your Git journey doesn't end here. Every project will teach you something new.

Good luck, and happy versioning!
