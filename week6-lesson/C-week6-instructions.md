# Week 6: Real Project Setup
## Complete UX Repository - The Final Integration

### What You'll Accomplish

By the end of this lesson, you'll have:
- A production-ready UX project repository
- Complete documentation structure
- Collaboration workflow established
- Team guidelines in place
- A template for all future projects

**Time needed:** 30-40 minutes

**This is it:** Everything you've learned, applied to a real project.

---

## The Complete Workflow

**What you're building:**

```
Complete UX Project
├── Proper Git structure (Week 3)
├── GitHub backup (Week 4)
├── Branch workflow (Week 5)
├── Professional documentation (Week 1-2)
├── Team collaboration ready (Week 5)
└── Decision tracking (Weeks 1-5)
```

**This becomes your template for every project going forward.**

---

## Part 1: Create the Repository (5 minutes)

### On GitHub

**1. Create new repository:**
- Go to github.com
- Click + → New repository
- Name: `ux-project-template` (or your actual project name)
- Description: "Complete UX project with documentation and collaboration workflow"
- **Private** (recommended for work projects)
- **DO NOT** initialize with README, .gitignore, or license
- Click "Create repository"

**2. Copy the repository URL:**
```
https://github.com/yourusername/ux-project-template.git
```

---

### On Your Computer

**3. Create local folder and initialize:**
```bash
cd ~/Desktop
mkdir ux-project-template
cd ux-project-template
git init
```

**4. Create initial structure:**
```bash
# Create main folders
mkdir docs src analysis tests handoff

# Create nested doc folders
mkdir -p docs/discovery
mkdir -p docs/requirements
mkdir -p docs/design
mkdir -p docs/architecture

# Create analysis subfolders
mkdir -p analysis/data
mkdir -p analysis/scripts
mkdir -p analysis/cost-benefit-analysis
```

**5. Connect to GitHub:**
```bash
git remote add origin https://github.com/yourusername/ux-project-template.git
```

**6. Verify connection:**
```bash
git remote -v
```

Should show your repository URL for fetch and push.

---

## Part 2: Create Core Documentation (10 minutes)

### Create README.md

```bash
touch README.md
code .
```

**Add this content:**

```markdown
# [Project Name]

Brief one-sentence description of what this project is.

## Quick Start

### For Stakeholders/Leadership
- [PRD](docs/PRD.md) - Product requirements and vision
- [Decision Log](docs/decision-log.md) - Key project decisions
- [Cost-Benefit Analysis](analysis/cost-benefit-analysis/) - Business case

### For Developers
- [PLATFORM.md](PLATFORM.md) - Tech stack and setup
- [Component Specs](docs/architecture/component-specs.md) - Implementation details
- [Prototype](src/) - Runnable code

### For UX Team
- [Discovery](docs/discovery/) - Research findings
- [Design](docs/design/) - Wireframes, mockups, design decisions
- [Testing](tests/usability/) - Usability test plans and results

## Project Status

**Current Phase:** [Discovery / Definition / Design / Testing / Handoff]

**Timeline:** [Start date] - [Target completion]

## Team

- Product Lead: [Name]
- UX Lead: [Name]
- Dev Lead: [Name]

## How to Contribute

See [CONTRIBUTING.md](CONTRIBUTING.md) for collaboration guidelines.

## Repository Structure

See [STRUCTURE.md](STRUCTURE.md) for detailed folder organization.

Last updated: [Date]
```

**Save the file.**

---

### Create PLATFORM.md

```bash
touch PLATFORM.md
```

**Add content:**

```markdown
# Platform Information

## Tech Stack

[To be determined / Current stack]

## Setup Instructions

### Prerequisites
- [List required tools]

### Installation
```bash
# Setup commands here
```

## Dependencies

[List dependencies or state "None yet"]

## Development

### Running Locally
```bash
# Commands to run prototype
```

### Building
```bash
# Build commands if applicable
```

## Environment Variables

[List any configuration needed]

Last updated: [Date]
```

**Save.**

---

### Create Decision Log

```bash
touch docs/decision-log.md
```

**Add template:**

```markdown
# Decision Log

Track key decisions, scope changes, and pivots. Newest entries first.

---

## [DATE]: [Decision Title]

**Context:** [What led to this decision?]

**Decision:** [What did we decide?]

**Impact:** [Timeline/scope changes]

**Owner:** [Who made this decision]

**References:** [Links to related docs]

---

## Example Entry

### 2025-01-16: Established Git workflow for team

**Context:** Team needs consistent way to collaborate on UX documentation and track changes over time.

**Decision:** Adopted Git/GitHub with feature branch workflow. All changes go through pull requests.

**Impact:** Improved collaboration, better version control, clearer decision history.

**Owner:** [Your name]

**References:** This repository structure

---
```

**Save.**

---

### Create PRD Template

```bash
touch docs/PRD.md
```

**Add structure:**

```markdown
# Product Requirements Document

## Overview

[High-level description of what we're building and why]

## Objectives

[What we're trying to achieve]

## Success Metrics

[How we'll measure success]

## Requirements

### Must Have
- [ ] Requirement 1
- [ ] Requirement 2

### Should Have
- [ ] Requirement 3

### Nice to Have
- [ ] Requirement 4

## User Stories

As a [user type], I want [goal] so that [benefit].

## Out of Scope

[What we're explicitly not doing]

## Timeline

[Key milestones and dates]

## Risks and Mitigations

[Potential issues and how we'll address them]

Last updated: [Date]
```

**Save.**

---

### Create .gitignore

```bash
touch .gitignore
```

**Add patterns:**

```
# Mac system files
.DS_Store
.AppleDouble
.LSOverride

# Temporary files
*.tmp
*.temp
*.bak

# Editor files
*.swp
*~
.vscode/settings.json

# Large design files (link instead)
*.psd
*.sketch

# Sensitive information
secrets.txt
api-keys.txt
.env

# Build output
dist/
build/

# Dependencies
node_modules/

# Log files
*.log
```

**Save.**

---

## Part 3: Initial Commit (3 minutes)

### Commit the Structure

```bash
# Stage everything
git add .

# Check what's staged
git status

# Commit
git commit -m "Initial project structure with documentation templates"

# Push to GitHub
git push -u origin main
```

**Verify on GitHub:**
- Refresh repository page
- You should see all folders and files
- README displays automatically

**Your foundation is now on GitHub!**

---

## Part 4: Create Collaboration Guidelines (5 minutes)

### Create CONTRIBUTING.md

```bash
git checkout -b docs/add-contributing-guide
touch CONTRIBUTING.md
code CONTRIBUTING.md
```

**Add guidelines:**

```markdown
# Contributing Guide

## How We Work

This project uses Git and GitHub for collaboration. Here's how to contribute.

## Workflow

### 1. Get Latest Changes
```bash
git checkout main
git pull
```

### 2. Create Feature Branch
```bash
git checkout -b feature/your-feature-name
```

Branch naming: `feature/`, `fix/`, `docs/`, `update/`

### 3. Make Changes

Edit files, test your work.

### 4. Commit Changes
```bash
git add .
git commit -m "Descriptive message"
```

### 5. Push Branch
```bash
git push -u origin feature/your-feature-name
```

### 6. Create Pull Request

- Go to GitHub repository
- Click "Pull requests" → "New pull request"
- Fill out PR template
- Request review

### 7. Address Feedback

Make requested changes, commit, push. PR updates automatically.

### 8. Merge

After approval, merge the PR and delete the branch.

## Pull Request Template

```markdown
## What Changed
[Brief description]

## Why
[Reasoning]

## Testing
[How you verified it works]

## Screenshots
[If applicable]
```

## Code Review Guidelines

### As Author
- Respond to all comments
- Make requested changes
- Keep PR updated

### As Reviewer
- Be constructive
- Be specific
- Approve when satisfied

## Commit Message Guidelines

**Good:**
- "Added user personas from Q4 research"
- "Fixed broken link in navigation doc"
- "Updated decision log with scope change"

**Bad:**
- "updates"
- "changes"
- "wip"

## Questions?

Contact [your name/team channel]
```

**Save, commit, push:**

```bash
git add .
git commit -m "Added contributing guidelines"
git push
```

---

### Create Pull Request for Contributing Guide

**On GitHub:**
1. Create PR from `docs/add-contributing-guide` to `main`
2. Title: "Add contributing guidelines"
3. Description: "Establishes team collaboration workflow"
4. Create PR
5. Review and approve it
6. Merge it
7. Delete branch

**On your computer:**
```bash
git checkout main
git pull
git branch -d docs/add-contributing-guide
```

**You just used the workflow you documented!**

---

## Part 5: Add Team Members (Optional - 5 minutes)

### If You Have Teammates

**1. Invite collaborators on GitHub:**
- Repository → Settings → Collaborators
- Click "Add people"
- Enter their GitHub username or email
- Choose permission level:
  - **Read:** View only
  - **Write:** Can push and create PRs
  - **Admin:** Full control

**2. Send them the repository URL:**
```
https://github.com/yourusername/ux-project-template
```

**3. They clone it:**
```bash
git clone https://github.com/yourusername/ux-project-template.git
```

**4. Now you can collaborate using the workflow!**

---

## Part 6: Practice the Full Workflow (10 minutes)

### Real-World Scenario

**Simulate adding research findings:**

**1. Create feature branch:**
```bash
git checkout main
git pull
git checkout -b docs/add-user-research
```

**2. Add content:**
```bash
mkdir -p docs/discovery
touch docs/discovery/user-research.md
```

Edit the file with sample research findings:

```markdown
# User Research Findings

## Research Overview
- Method: User interviews
- Participants: 8 users
- Date: January 2025

## Key Findings

### Finding 1: Navigation Confusion
Users struggled to find account settings.

### Finding 2: Search Expectations
80% expected a search bar in the top navigation.

### Finding 3: Mobile Experience
Mobile users had different expectations than desktop users.

## Recommendations
1. Redesign navigation structure
2. Add prominent search feature
3. Optimize mobile experience

## Next Steps
- Create wireframes based on findings
- Plan usability testing for new design
```

**3. Commit and push:**
```bash
git add .
git commit -m "Added Q1 2025 user research findings"
git push -u origin docs/add-user-research
```

**4. Create PR, review, merge**

**5. Update local:**
```bash
git checkout main
git pull
git branch -d docs/add-user-research
```

**6. Update decision log:**
```bash
git checkout -b docs/update-decision-log
code docs/decision-log.md
```

Add entry:
```markdown
## 2025-01-16: Added user research findings

**Context:** Completed Q1 user research with 8 participants.

**Decision:** Documented findings in discovery folder for team reference.

**Impact:** Research will inform navigation redesign.

**Owner:** [Your name]

**References:** [docs/discovery/user-research.md](docs/discovery/user-research.md)
```

**7. Commit, push, PR, merge, clean up**

**You just completed a full real-world workflow!**

---

## Part 7: Document the Structure (5 minutes)

### Create STRUCTURE.md

```bash
git checkout -b docs/add-structure-guide
touch STRUCTURE.md
```

**Add explanation:**

```markdown
# Repository Structure Guide

## Overview

This repository follows a standard UX project structure that works well with developer workflows.

## Directory Layout

```
ux-project-template/
├── README.md              # Project overview (start here)
├── PLATFORM.md            # Technical details
├── CONTRIBUTING.md        # How to contribute
├── STRUCTURE.md           # This file
├── .gitignore             # Files to exclude from Git
│
├── docs/                  # All documentation
│   ├── PRD.md             # Product requirements (north star)
│   ├── decision-log.md    # Decision history
│   ├── discovery/         # Research findings
│   ├── requirements/      # Personas, journeys, requirements
│   ├── design/            # Design decisions, wireframes
│   └── architecture/      # Component specs for developers
│
├── src/                   # Prototype code
├── analysis/              # Data and analysis
│   ├── data/              # Research data
│   ├── scripts/           # Analysis scripts
│   └── cost-benefit-analysis/
│
├── tests/                 # Usability testing
│   └── usability/
│
└── handoff/               # Final deliverables for developers
    ├── design-assets/
    └── component-specs/
```

## File Naming Conventions

- Use lowercase
- Use hyphens for spaces: `user-research.md` not `User Research.md`
- Be descriptive: `persona-power-user.md` not `persona1.md`
- Add dates for time-sensitive docs: `research-findings-2025-01.md`

## When to Create New Folders

- When you have 5+ related files
- When organizing by type makes sense
- When team agrees it adds clarity

## What Goes Where

### docs/discovery/
- User research
- Competitive analysis
- Stakeholder interviews
- Market research

### docs/requirements/
- Personas
- User journeys
- Problem statements
- Functional requirements

### docs/design/
- Wireframes
- Design decisions
- Information architecture
- Links to Figma files

### docs/architecture/
- Component specifications
- Technical requirements
- API documentation (if applicable)

### analysis/
- Raw data (CSV, JSON)
- Python/R scripts for analysis
- Cost-benefit analyses
- Statistical reports

### src/
- Working prototype code
- Can be run and tested
- Not final production code

### tests/usability/
- Test plans
- Test results
- Participant notes
- Video links

### handoff/
- Final assets for developers
- Exported images, icons
- Component specs
- Style tokens

## Maintenance

- Keep structure consistent
- Update this guide if structure changes
- Delete empty folders
- Archive old content rather than delete

## Questions?

Contact [team lead] or discuss in [team channel]
```

**Save, commit, push, PR, merge.**

---

## Completion Checklist

You're done when you have:

- [ ] Created complete folder structure
- [ ] README with navigation
- [ ] PLATFORM.md with tech info
- [ ] Decision log with template
- [ ] PRD template
- [ ] Proper .gitignore
- [ ] Contributing guidelines
- [ ] Structure documentation
- [ ] Sample content in docs
- [ ] Completed at least 2 full PR cycles
- [ ] Repository backed up on GitHub
- [ ] Team members invited (if applicable)

**Bonus:**
- [ ] Used the workflow on actual project content
- [ ] Helped teammate through first PR
- [ ] Customized structure for your specific needs
- [ ] Confident you can recreate this for new projects

---

## What You've Built

**A complete, production-ready UX project system:**

- Version controlled
- Cloud backed up
- Collaboration ready
- Professionally structured
- Well documented
- Team guidelines established
- Scalable and maintainable

**This is what professional UX teams use.**

---

## Using This Template

### For New Projects

**1. Clone your template:**
```bash
git clone https://github.com/yourusername/ux-project-template.git new-project-name
cd new-project-name
```

**2. Update remote:**
```bash
# Create new repository on GitHub first
git remote set-url origin https://github.com/yourusername/new-project-name.git
git push -u origin main
```

**3. Customize:**
- Update README with project details
- Modify PRD for project specifics
- Add initial decision log entries
- Start working!

**Your template is now reusable for every project.**

---

## Tools to Help You

**Absolutely use any resource:**

### When Setting Up Projects

**Google:**
- "GitHub repository best practices"
- "UX documentation templates"
- "Git workflow for design teams"

**AI Assistants:**
- "Help me write a README for a UX project"
- "What should go in a PRD template?"
- "How do I structure UX documentation?"

### Ongoing

- GitHub documentation
- Team discussions
- Iteration based on what works
- Continuous improvement

---

## Best Practices Going Forward

### Daily Workflow

**Morning:**
```bash
git pull  # Get team's work
```

**During work:**
- Create feature branch for each task
- Commit progress regularly
- Push at least daily

**Before significant changes:**
- Pull latest
- Create branch
- Work independently

**When done:**
- Create PR
- Request review
- Merge when approved
- Delete branch

---

### Documentation Habits

**Keep docs current:**
- Update decision log when decisions happen
- Revise PRD as scope evolves
- Document design decisions as you make them
- Don't let docs get stale

**Make it findable:**
- Consistent naming
- Clear folder organization
- Good README navigation
- Link between related docs

**Make it useful:**
- Write for your future self
- Assume reader has no context
- Include why, not just what
- Screenshots for visual context

---

## Customization Ideas

### Adapt to Your Needs

**This template is a starting point. Consider:**

**For research-heavy projects:**
- Expand analysis/ folder
- Add methodologies/ folder
- Create findings-database/

**For design-focused projects:**
- Expand design/ folder
- Add design-systems/
- Create iterations/

**For collaborative projects:**
- Add meeting-notes/
- Create stakeholder-feedback/
- Add timeline-tracking/

**Make it yours while keeping the foundation.**

---

## Troubleshooting

### Common Setup Issues

**"Can't push - authentication failed"**
- Verify personal access token is current
- Check repository permissions
- Regenerate token if needed

**"Collaborator can't push"**
- Verify they have Write permission
- Check they're using correct repository URL
- Ensure they've cloned (not just viewing)

**"Too many merge conflicts"**
- Pull more frequently
- Work on separate files when possible
- Communicate about who's editing what

**"Don't know where to put something"**
- Ask team
- Make a decision and document it
- Consistency matters more than perfection

---

## Next Steps After Week 6

### Immediate (This Week)

1. Use this template on a real project
2. Make your first real PRs
3. Get comfortable with daily workflow
4. Teach a teammate

### Near-Term (This Month)

1. Refine template based on real use
2. Establish team conventions
3. Build muscle memory with workflow
4. Handle real collaboration scenarios

### Long-Term (Ongoing)

1. Contribute to team knowledge base
2. Help onboard new team members
3. Improve processes based on experience
4. Stay current with Git/GitHub features

---

## Measuring Success

### You'll Know It's Working When:

- Setting up new projects takes 10 minutes
- Team uses PRs naturally
- Documentation stays current
- No one asks "where's the latest version?"
- Decisions are tracked automatically
- Collaboration feels smooth
- You've taught others the workflow
- You don't think about Git - you just use it

---

## Encouragement

**You did it.**

Six weeks ago:
- Terminal was scary
- Git was mysterious
- GitHub was confusing
- Branches made no sense
- Pull requests seemed complex

**Now:**
- You navigate Terminal confidently
- You understand version control
- You push to GitHub daily
- You create branches naturally
- You collaborate professionally

**That's real growth.**

---

## The Bigger Picture

**What you've actually learned:**

Not just Git commands.

**You learned:**
- Professional collaboration workflows
- Version control thinking
- Documentation best practices
- Team coordination systems
- Industry-standard tooling

**These skills transfer:**
- Any tech company
- Any collaborative project
- Any modern workflow
- Any version-controlled system

**You're ready for real work.**

---

## Final Thoughts

**This template is living:**
- Iterate on it
- Improve based on experience
- Customize for your needs
- Share with your team

**The workflow is learned:**
- Daily practice builds fluency
- Mistakes are learning opportunities
- Teaching others deepens understanding
- Confidence comes with repetition

**You have the foundation:**
- Six weeks of building skills
- Complete system for UX work
- Template for future projects
- Confidence to execute

**Now go use it.**

---

## Questions or Stuck?

**Resources:**
- All previous week materials
- This complete repository as reference
- Team channel: [your channel]
- Office hours: [day/time]
- GitHub documentation
- Your own experience from Weeks 1-5

**You have everything you need.**

---

## Congratulations

**You completed all 6 weeks.**

**You now have:**
- Terminal proficiency
- VS Code expertise
- Git knowledge
- GitHub collaboration skills
- Branch workflow mastery
- Complete project template

**You're no longer learning Git.**

**You're using Git.**

**Go build great things.**
