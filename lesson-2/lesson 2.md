# Session 2: Git 101 + GitHub

**Date:** March 31, 2026
**Duration:** ~59 minutes
**Instructors:** Ryan Herubin (Git/GitHub concepts), Maroun Najjar (host)
**Participants:** Lizzie Belgum, Samara Tager, Katelyn Burgin, Janice Pang, Jennifer Garfield, Corinne Sherry, Rafa Socrates, Steve Dziedzic, Akshay Verma, Rowan Rosenthal

---

## What We Covered

This session had two parts: homework demos from Session 1, then Ryan Herubin's introduction to Git and GitHub — the system engineers use to collaborate on code.

### Part 1: Homework Demos (~13 min)

Two participants demoed what they built between sessions:

**Samara Tager — Global Rollout Tracker**
Samara built a dashboard to manage the rollout of the Starter Dashboard across 17 markets. She connected it to Google Sheets, Slack, Amplitude, and JIRA — pulling in QA bugs, linked tickets, and data summaries automatically. Key learnings:
- She discovered Claude doesn't remember previous sessions — you need to re-provide context each time
- She had to explicitly tell Claude to make data connections live and persistent (check hourly, update automatically)
- Used Agentation for visual bug cleanup

**Rafa Socrates — Brand Guidelines Site**
Rafa built a single-page brand guidelines reference — a way for anyone in the company to access logos, colors, and design assets without needing Figma access. Key learnings:
- Used Visual Explainer for initial build
- Used Agentation for iterating on visual bugs
- Struggled with getting Figma variables/tokens imported perfectly — still a rough edge

### Part 2: Git & GitHub Core Concepts (~40 min)

Ryan walked through the four core concepts of Git:

#### 1. Commits
A commit is a snapshot of your work at a specific point in time. Think of it like a save point in a video game — you can always go back to it.

#### 2. Branches
A branch is a copy of the codebase that you can change without affecting the original. When you want to work on something, you create a branch, make your changes, and then bring those changes back when you're ready.

- **Main branch** = the central, "official" version of the code
- **Your branch** = your personal copy where you make changes
- You always branch off of main (unless an engineer tells you otherwise)

#### 3. Push & Pull
- **Push** = upload your local changes to GitHub (the cloud)
- **Pull** = download the latest changes from GitHub to your computer
- This is how you stay in sync when collaborating

**Key distinction:** There's what exists in the cloud (the remote repo on GitHub) and what exists locally on your computer. Push and pull keep these in sync.

#### 4. Pull Requests (PRs)
A pull request is NOT the same as a "pull." It's a formal request to merge your branch into the main codebase. It opens a conversation with engineering — they review your code, discuss changes, and ultimately approve and merge it.

**Important:** When you create a PR, ownership of the code transfers to the engineer. They handle the merge, QA, and release pipeline. You don't need to worry about merging.

**For prototypes:** The PR/merge process matters less. You're working in your own isolated environment — Claude Code handles branching for you. PRs become important when your work is heading to production.

### Part 3: Live Setup (~15 min)

Everyone installed Git and authenticated with GitHub:

1. **Install Xcode command line tools:** `xcode-select --install`
2. **Install GitHub CLI:** `brew install gh`
3. **Authenticate:** `gh auth login` → select GitHub.com → HTTPS → Login with browser
4. **Verify:** `gh api user` (shows your GitHub username)

---

## Key Concepts & Terms

| Term | What it means |
|------|--------------|
| **Git** | Version control system — tracks every change to your code |
| **GitHub** | Cloud platform where Git repos are stored and shared |
| **Repo (repository)** | A project folder tracked by Git |
| **Commit** | A saved snapshot of your code at a point in time |
| **Branch** | A parallel copy of the codebase for making changes |
| **Main** | The primary branch — the "official" version |
| **Push** | Upload your local changes to GitHub |
| **Pull** | Download latest changes from GitHub to your computer |
| **Pull Request (PR)** | A formal request to merge your branch into main — starts a conversation with engineering |
| **Remote / Origin** | GitHub (for now, these mean the same thing) |
| **Clone** | Download a repo from GitHub to your computer for the first time |
| **Merge** | Combining one branch's changes into another |

---

## Key Takeaways

1. **Git is how we collaborate on work.** It's the foundation for iterating on a product surface with other people.
2. **You can play freely.** Create a branch, experiment to your heart's content — the code only lives on your computer until you push it.
3. **Claude Code handles Git for you.** You can literally ask Claude "am I behind the remote branch?" or "create a new branch called my-feature" in natural language.
4. **PRs are conversations, not just code drops.** When you're ready to hand off work to engineering, the PR is where that conversation happens.
5. **For prototyping, Git is less critical.** But it becomes essential when your prototype is heading to production or when you're collaborating with others.

---

## What's Next

Session 3 will be hands-on: everyone pulls down a shared repo, creates branches, makes changes, and pushes them back. We'll also introduce **worktrees** — a way to run multiple agents on the same codebase in parallel universes.
