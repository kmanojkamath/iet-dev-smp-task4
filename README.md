# Repository Analysis Notes

## Student Details

**Name:** K Manoj Kamath
**Roll Number:** 251CS130

---

# Basic Git Commands

Git is a distributed version control system used to track changes in source code and collaborate with other developers.

## Repository Setup

### Clone a Repository

```bash
git clone <repository-url>
```

Creates a local copy of a remote repository.

### Initialize a Repository

```bash
git init
```

Creates a new Git repository in the current directory.

---

## Checking Repository Status

### Check Status

```bash
git status
```

Displays modified files, staged files, and branch information.

### View Commit History

```bash
git log
```

Shows the commit history of the repository.

### Compact Commit History

```bash
git log --oneline
```

Displays a shortened version of the commit history.

---

## Working with Changes

### Add a Specific File

```bash
git add <file-name>
```

Stages a file for the next commit.

### Add All Changes

```bash
git add .
```

Stages all modified and new files.

### Commit Changes

```bash
git commit -m "Commit message"
```

Saves the staged changes in the local repository.

---

## Working with Branches

### View Branches

```bash
git branch
```

Lists all local branches.

### Create a Branch

```bash
git branch branch-name
```

Creates a new branch.

### Switch to a Branch

```bash
git checkout branch-name
```

Moves to the specified branch.

### Create and Switch in One Command

```bash
git checkout -b branch-name
```

Creates a new branch and switches to it immediately.

---

## Working with Remote Repositories

### View Remote Repositories

```bash
git remote -v
```

Shows configured remote repositories.

### Push Changes

```bash
git push origin branch-name
```

Uploads local commits to the remote repository.

### Pull Latest Changes

```bash
git pull origin main
```

Downloads and merges changes from the remote repository.

### Fetch Changes

```bash
git fetch
```

Downloads updates from the remote repository without merging them.

---

## Merging Changes

### Merge a Branch

```bash
git merge branch-name
```

Combines changes from another branch into the current branch.

### View Differences

```bash
git diff
```

Shows differences between files and commits.

---

# Difference Between Fork and Clone

## Fork

A fork creates a copy of another user's repository under your own GitHub account.

Example:

```text
Original Repository
        │
        ▼
     Your Fork
```

Characteristics:

* Exists on GitHub.
* Used when contributing to someone else's project.
* You have full control over your fork.
* Changes made in your fork do not affect the original repository.

---

## Clone

A clone creates a local copy of a repository on your computer.

Example:

```text
GitHub Repository
        │
        ▼
    Local Clone
```

Characteristics:

* Exists on your local machine.
* Used for development and editing code.
* Can be created from either the original repository or a fork.

---

## Fork vs Clone

| Feature                 | Fork                        | Clone                       |
| ----------------------- | --------------------------- | --------------------------- |
| Location                | GitHub                      | Local Computer              |
| Purpose                 | Create your own remote copy | Download repository locally |
| Ownership               | Your GitHub account         | Your local machine          |
| Used for Contributions  | Yes                         | Yes                         |
| Requires GitHub Account | Yes                         | No                          |

---

# Repository Workflow Analysis

The repository contains a GitHub Actions workflow named:

**My Simple CI-CD Pipeline**

Location:

```text
.github/workflows/
```

## Workflow Triggers

The workflow runs when:

1. Code is pushed to the `main` branch.
2. A Pull Request targeting the `main` branch is created or updated.

```yaml
on:
  push:
    branches: [main]

  pull_request:
    branches: [main]
```

---

## Workflow Steps

### Step 1 – Grab Code From Repo

```yaml
uses: actions/checkout@v4
```

Downloads the repository contents to the GitHub Actions runner.

---

### Step 2 – Run Linter Station

```yaml
echo "Checking code formatting style... All clean!"
```

Simulates checking code style and formatting.

---

### Step 3 – Run Testing Station

```yaml
echo "Running automated tests... 100% passed!"
```

Simulates running automated tests.

---

### Step 4 – Run Build Tool Station

```yaml
echo "Compiling and packaging code into production files..."
```

Simulates building the application.

---

### Step 5 – Run Deployment Station

```yaml
echo "Deploying files to the cloud. App is now live! 🚀"
```

Simulates deployment of the application.

---

# What the Workflow Is Doing

The workflow demonstrates the basic stages of a CI/CD pipeline:

1. Checkout source code.
2. Lint the code.
3. Test the code.
4. Build the application.
5. Deploy the application.

However, in this repository all stages after checkout only execute `echo` commands. They do not perform real linting, testing, building, or deployment tasks. The workflow serves as a template or demonstration of how a CI/CD pipeline can be structured in GitHub Actions.
