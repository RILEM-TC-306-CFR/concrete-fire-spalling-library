# Contributing to the Concrete Fire Spalling Database

Thank you for your interest in contributing! This guide is designed for people new to GitHub. We'll walk you through every step.

## Table of Contents

1. [Getting Started](#getting-started)
2. [Making Changes](#making-changes)
3. [Creating a Branch](#creating-a-branch)
4. [Submitting a Pull Request](#submitting-a-pull-request)
5. [Common Tasks](#common-tasks)
6. [Need Help?](#need-help)

---

## Getting Started

### Prerequisites

You'll need:
- A **GitHub account** (free) – [Sign up here](https://github.com/signup)
- **Git installed** on your computer – [Download here](https://git-scm.com/download/win)
- **VS Code** (optional but recommended) – [Download here](https://code.visualstudio.com/)

### Clone the Repository

This means downloading the project to your computer.

**Using Command Line:**
```bash
git clone https://github.com/RILEM-TC-306-CFR/concrete-fire-spalling-library.git
cd concrete-fire-spalling-library
```

**Using VS Code:**
1. Open VS Code
2. Press `Ctrl+Shift+P` (Command Palette)
3. Type: `Git: Clone`
4. Paste: `https://github.com/RILEM-TC-306-CFR/concrete-fire-spalling-library.git`
5. Choose a folder to save it

---

## Making Changes

### Step 1: Update Your Local Repository

Before making changes, always pull the latest version:

```bash
git pull origin main
```

This downloads any recent changes from GitHub so you start with the current version.

### Step 2: Edit Files

Make your changes directly to files:
- Edit the **CSV database** with new experimental data
- Update **README.md** with documentation
- Modify any other files as needed

You can edit files in:
- **VS Code** (recommended) – syntax highlighting, easy navigation
- **Notepad** or any text editor
- **Excel** (for CSV files – but save as CSV, not .xlsx)

### Step 3: Check What Changed

**Using VS Code:**
1. Press `Ctrl+Shift+G` to open Source Control
2. You'll see all modified files listed

**Using Command Line:**
```bash
git diff
```

This shows exactly what changed (lines added/removed).

---

## Creating a Branch

A **branch** is a separate copy of the project where you can make changes without affecting the main version. This is important for keeping things organized.

### Why Use Branches?

- Multiple people can work simultaneously
- Changes are isolated and safe
- Easy to compare different versions
- Can be reviewed before merging into main

### Create a Branch

Choose a descriptive name for your branch (e.g., `add-new-spalling-data`, `fix-readme-typo`, `update-contributor-info`).

**Using VS Code:**
1. Press `Ctrl+Shift+G` (Source Control)
2. Click the **three dots (...)** menu
3. Select **Branch → Create Branch...**
4. Enter your branch name
5. Press Enter

**Using Command Line:**
```bash
git checkout -b your-branch-name
```

Example:
```bash
git checkout -b add-new-experimental-data
```

### Switch Between Branches

**Using VS Code:**
- Look at the bottom-left corner – it shows your current branch
- Click it to see a list of branches
- Click a branch name to switch to it

**Using Command Line:**
```bash
git checkout branch-name
```

---

## Making & Saving Your Changes

### Step 1: Save Your Files

Make sure all your changes are saved:
- **VS Code**: Press `Ctrl+S` (or `Ctrl+Shift+S` to save all)
- **Other editors**: Use File → Save

### Step 2: Stage Your Changes

Staging means marking files as "ready to commit".

**Using VS Code:**
1. Open Source Control (`Ctrl+Shift+G`)
2. Click the **+** icon next to each file you changed

**Using Command Line:**
```bash
git add filename.csv
git add README.md
```

Or to add all changed files:
```bash
git add .
```

### Step 3: Commit Your Changes

A **commit** is a snapshot of your changes with a description.

**Using VS Code:**
1. Type a message in the textbox (e.g., "Add 5 new fire test specimens")
2. Click the **Commit button** (✓ checkmark)

**Using Command Line:**
```bash
git commit -m "Add 5 new fire test specimens from 2026 study"
```

**Good commit messages:**
- ✅ "Add concrete material composition data"
- ✅ "Fix typo in Species column header"
- ✅ "Update References section"
- ❌ "changes"
- ❌ "update"

### Step 4: Push to GitHub

Push means uploading your changes to GitHub.

**Using VS Code:**
1. Click the **three dots (...)** menu in Source Control
2. Select **Push** (or **Publish** if new branch)

**Using Command Line:**
```bash
git push origin your-branch-name
```

Example:
```bash
git push origin add-new-experimental-data
```

---

## Submitting a Pull Request

A **Pull Request (PR)** asks the project maintainers to review your changes and merge them into the main database.

### Step 1: Push Your Branch

Make sure your branch is pushed to GitHub (see "Push to GitHub" above).

### Step 2: Go to GitHub

1. Go to: https://github.com/RILEM-TC-306-CFR/concrete-fire-spalling-library
2. You should see a notification with your branch name and a **"Compare & pull request"** button
3. Click it

**If you don't see it:**
1. Click the **Branch** dropdown (currently shows "main")
2. Select your branch name
3. Click **Contribute** (green button)
4. Click **Open pull request**

### Step 3: Fill in the Pull Request Details

**Title:** A clear, short description
- Example: "Add 5 new fire spalling specimens from Mróz et al. 2026"

**Description:** Explain what you changed and why
```
## Changes Made
- Added 5 new test specimens (rows 1001-1005)
- Updated specimen geometry parameters
- Added new instrumentation data

## Data Source
Mróz, K., et al. (2026). Fire resistance of concrete with recycled aggregate.

## Related Issues
Closes #42
```

### Step 4: Review

- The project maintainers will review your changes
- They may ask questions or request modifications
- Make changes on your branch if needed (they'll appear automatically in the PR)

### Step 5: Merge

Once approved, a maintainer will click **"Merge pull request"** to add your changes to the main database. Congratulations! 🎉

---

## Common Tasks

### I Made a Mistake. How Do I Undo Changes?

**Before committing:**
```bash
git restore filename.csv
```

**After committing (but not pushed):**
```bash
git revert HEAD
```

### How Do I Update My Branch With Latest Changes From Main?

```bash
git fetch origin
git rebase origin/main
```

### I Accidentally Committed to 'main'. How Do I Fix It?

Contact the maintainers. They can help revert or move commits to a branch.

---

## Complete Workflow Example

Here's a step-by-step example of adding new data:

```bash
# 1. Clone repository
git clone https://github.com/RILEM-TC-306-CFR/concrete-fire-spalling-library.git
cd concrete-fire-spalling-library

# 2. Update to latest
git pull origin main

# 3. Create new branch
git checkout -b add-fire-test-data-2026

# 4. Edit your files (use editor of choice)
# Add data to CSV, update README, etc.

# 5. Check what changed
git diff

# 6. Stage changes
git add "RILEM TC CFR Task C - Spalling Database_v0-0-0 (01.04.2026).csv"
git add README.md

# 7. Commit
git commit -m "Add 10 new fire resistance test specimens from 2026 study"

# 8. Push to GitHub
git push origin add-fire-test-data-2026

# 9. Go to GitHub website and create Pull Request
```

---

## Writing Good Data Entries

When adding new experimental data, please ensure:

1. **Data completeness** – Fill in as many parameters as possible
2. **Source citation** – Include DOI, reference, or publication details
3. **Data accuracy** – Double-check numbers and units
4. **Unit consistency** – Follow the database column headers
5. **Description** – Add notes in the "Additional Notes" column if anything is unusual

---

## Need Help?

### Getting Help

- **GitHub Help**: https://docs.github.com/
- **Simple Git Commands**: https://git-scm.com/docs
- **General Questions**: Open an [Issue](https://github.com/RILEM-TC-306-CFR/concrete-fire-spalling-library/issues) on GitHub

### Common Issues & Solutions

**"Permission denied (publickey)"**
- You need to set up SSH keys. Follow this guide: https://docs.github.com/en/authentication/connecting-to-github-with-ssh

**"Your branch is behind origin/main"**
- Pull the latest changes: `git pull origin main`

**"Merge conflict"**
- Don't worry – contact the maintainers, they'll help resolve it

---

## Guidelines

- Be respectful and constructive
- Test your changes before submitting
- Write clear commit messages
- Reference related issues when relevant
- Follow the existing data format

---

## Thank You! 

Your contributions help advance fire safety research. We appreciate your help!

For questions about this guide, please reach out to the project maintainers or open an issue on GitHub.

---

**Last updated**: April 1, 2026
