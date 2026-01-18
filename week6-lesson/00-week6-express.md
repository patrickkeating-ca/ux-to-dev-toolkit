# Week 6 Express: Real Project Setup
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
*.sketch

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

- Recruiting: Week 1
- Sessions: Week 2-3
- Analysis: Week 4
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

The full Week 6 lesson includes:
- Extended folder structure
- Detailed README templates
- Team collaboration setup
- GitHub Issues and Projects
- PLATFORM.md documentation
- Decision log setup
- Comprehensive examples

**Come back when you need these.**

---

## When to Return to Full Week 6

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

**Congratulations!** You've completed the express version of all 6 weeks.

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

Consider the comprehensive 6-week program if:
- You want deep understanding
- You're training a team
- You need to troubleshoot issues
- You want portfolio-ready skills
- You have 15-20 hours available
- You prefer thorough learning

**Express version gets you functional. Full program makes you proficient.**

Both are valuable depending on your goals and time constraints.
