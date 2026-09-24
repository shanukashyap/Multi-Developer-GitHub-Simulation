# Multi-Developer GitHub Simulation

A Python project created to demonstrate a real-world **Git and GitHub collaboration workflow** involving multiple developers.

In this project, two developers are simulated using separate branches and a separate clone of the GitHub repository.

The project demonstrates how developers can work independently on features, push their changes to GitHub, create a Pull Request, review the code, and merge the feature into the `main` branch.

---

## Project Overview

This project is a simple Python calculator application.

The initial project was created by **Developer A**.

**Developer B** then:

1. Cloned the repository.
2. Connected to the remote GitHub repository.
3. Fetched remote information.
4. Pulled the latest changes.
5. Created a feature branch.
6. Implemented a subtraction feature.
7. Committed the changes.
8. Pushed the feature branch to GitHub.
9. Created a Pull Request.
10. Submitted the changes for code review.
11. The Pull Request was reviewed and merged into `main`.

Since this project was completed individually, two branches and separate local copies were used to simulate two developers.

---

# Technologies Used

* Python 3
* Git
* GitHub
* Visual Studio Code

---

# Project Structure

```text
Multi-Developer-GitHub-Simulation/
│
├── main.py
├── calculator.py
├── README.md
└── .gitignore
```

---

# File Description

## `main.py`

This is the main Python application.

It imports calculator functions and demonstrates the calculator operations.

Example:

```python
from calculator import add, subtract


def main():
    addition_result = add(10, 20)
    subtraction_result = subtract(20, 5)

    print("Addition Result:", addition_result)
    print("Subtraction Result:", subtraction_result)


if __name__ == "__main__":
    main()
```

---

## `calculator.py`

This file contains the calculator functions.

### Addition

```python
def add(a, b):
    return a + b
```

### Subtraction

```python
def subtract(a, b):
    return a - b
```

The `subtract()` function was the feature implemented by Developer B.

---

## `.gitignore`

The `.gitignore` file prevents unnecessary files from being tracked by Git.

```gitignore
__pycache__/
*.pyc
.venv/
venv/
.env
```

### Why `.gitignore` is used

It prevents files such as:

* Python cache files
* Virtual environment files
* Environment variables
* Compiled Python files

from being accidentally committed to the repository.

---

# Application Output

When the application is executed:

```bash
python main.py
```

The output is:

```text
Addition Result: 30
Subtraction Result: 15
```

---

# Git and GitHub Collaboration Workflow

The main purpose of this project is to demonstrate a collaborative Git workflow.

The workflow is:

```text
Developer A
     |
     | Create Project
     v
   Git Init
     |
     | Commit
     v
   Main Branch
     |
     | Push
     v
   GitHub Remote Repository
     |
     v
Developer B
     |
     | Clone
     v
Local Repository
     |
     | Fetch
     | Pull
     v
Create Feature Branch
     |
     | Implement Feature
     v
Commit Changes
     |
     | Push
     v
GitHub Feature Branch
     |
     v
Pull Request
     |
     v
Code Review
     |
     v
Approve
     |
     v
Merge
     |
     v
Main Branch
```

---

# Developer A Workflow

Developer A is responsible for creating the initial project.

## Step 1: Create the project

Developer A creates:

```text
main.py
calculator.py
README.md
.gitignore
```

---

## Step 2: Initialize Git

```bash
git init
```

`git init` creates a new Git repository in the project folder.

---

## Step 3: Check repository status

```bash
git status
```

This shows which files are untracked or modified.

---

## Step 4: Add files

```bash
git add .
```

This stages the project files for committing.

---

## Step 5: Create the first commit

```bash
git commit -m "Initial calculator project"
```

This saves the initial version of the project in Git history.

---

## Step 6: Create the main branch

```bash
git branch -M main
```

This renames the current branch to `main`.

---

## Step 7: Connect to GitHub

```bash
git remote add origin https://github.com/YOUR_USERNAME/Multi-Developer-GitHub-Simulation.git
```

The `origin` remote represents the GitHub repository.

---

## Step 8: Push the project

```bash
git push -u origin main
```

This uploads the local `main` branch to GitHub.

---

# Remote Repository

A remote repository is a repository hosted on a platform such as GitHub.

In this project:

```text
Local Repository
       |
       | push
       v
GitHub Remote Repository
```

The remote can be checked using:

```bash
git remote -v
```

Example:

```text
origin  https://github.com/YOUR_USERNAME/Multi-Developer-GitHub-Simulation.git (fetch)
origin  https://github.com/YOUR_USERNAME/Multi-Developer-GitHub-Simulation.git (push)
```

---

# Developer B Workflow

Developer B simulates another developer joining the project.

## Step 1: Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/Multi-Developer-GitHub-Simulation.git
```

`git clone` downloads the GitHub repository to the local computer.

It creates:

* Local project files
* Git history
* Remote connection

---

# Clone vs Download

`git clone` is different from simply downloading ZIP files.

When using:

```bash
git clone
```

Git also downloads the repository's version history and configures the remote repository.

---

# Step 2: Check the remote repository

```bash
git remote -v
```

This confirms that the cloned project is connected to GitHub.

---

# Step 3: Fetch remote changes

```bash
git fetch origin
```

`git fetch` downloads information about changes from the remote repository.

It does not automatically merge those changes into the current working branch.

---

# Step 4: Pull the latest changes

```bash
git pull origin main
```

`git pull` retrieves changes from the remote repository and integrates them into the current branch.

---

# Fetch vs Pull

## `git fetch`

```bash
git fetch origin
```

Downloads remote information without automatically changing the working files.

## `git pull`

```bash
git pull origin main
```

Downloads and integrates changes into the current branch.

In simple terms:

```text
fetch = "Check and download remote information"

pull = "Download and integrate remote changes"
```

---

# Step 5: Create a Feature Branch

Developer B creates a separate branch:

```bash
git checkout -b feature-subtract
```

Alternatively:

```bash
git switch -c feature-subtract
```

The branch is named:

```text
feature-subtract
```

The purpose of a feature branch is to allow Developer B to work on the new feature without directly changing `main`.

---

# Branch Workflow

The branch structure becomes:

```text
main
 |
 +---- feature-subtract
```

Developer B works on:

```text
feature-subtract
```

instead of directly working on:

```text
main
```

---

# Step 6: Implement the Feature

Developer B adds a subtraction function to `calculator.py`.

```python
def subtract(a, b):
    return a - b
```

The main application is also updated to use the new function.

```python
from calculator import add, subtract


def main():
    addition_result = add(10, 20)
    subtraction_result = subtract(20, 5)

    print("Addition Result:", addition_result)
    print("Subtraction Result:", subtraction_result)


if __name__ == "__main__":
    main()
```

---

# Step 7: Test the Feature

Run:

```bash
python main.py
```

Expected output:

```text
Addition Result: 30
Subtraction Result: 15
```

This confirms that the new feature works.

---

# Step 8: Check Changes

Developer B checks the repository:

```bash
git status
```

Then views the code differences:

```bash
git diff
```

`git diff` shows the changes made to the project before committing them.

---

# Step 9: Commit the Feature

Stage the files:

```bash
git add calculator.py main.py
```

Create a commit:

```bash
git commit -m "Add subtraction feature"
```

The commit records Developer B's feature in Git history.

---

# Step 10: Push the Feature Branch

Developer B pushes the feature branch to GitHub:

```bash
git push -u origin feature-subtract
```

This creates the remote branch:

```text
feature-subtract
```

on GitHub.

---

# Pull Request

After pushing the feature branch, Developer B creates a Pull Request on GitHub.

The Pull Request compares:

```text
feature-subtract
        ↓
       main
```

Example Pull Request title:

```text
Add subtraction feature
```

---

# Pull Request Purpose

A Pull Request allows another developer or maintainer to:

* Review the code
* Discuss changes
* Check the implementation
* Identify potential problems
* Approve the changes
* Merge the feature into `main`

The Pull Request acts as a controlled process for integrating new code.

---

# Code Review

The Pull Request changes are reviewed on GitHub.

The reviewer checks:

* Whether the subtraction function works
* Whether the code is readable
* Whether the existing addition feature still works
* Whether the new code follows the project structure
* Whether the feature is ready to merge

After reviewing the changes, the Pull Request can be approved.

---

# Merge Process

After the Pull Request is approved, it can be merged into `main`.

The GitHub process is:

```text
Pull Request
     |
     v
Code Review
     |
     v
Approval
     |
     v
Merge Pull Request
     |
     v
main
```

After merging, the subtraction feature becomes part of the main project.

---

# Updating Local Main Branch

After the Pull Request is merged, the local repository can be updated.

Switch to `main`:

```bash
git checkout main
```

Pull the latest changes:

```bash
git pull origin main
```

Now the local `main` branch contains the merged subtraction feature.

---

# Important Git Commands Demonstrated

This project demonstrates the following commands.

## `git init`

Creates a new Git repository.

```bash
git init
```

## `git status`

Shows the current state of the repository.

```bash
git status
```

## `git add`

Stages files for commit.

```bash
git add .
```

## `git commit`

Creates a snapshot of changes.

```bash
git commit -m "Add subtraction feature"
```

## `git log`

Shows commit history.

```bash
git log --oneline
```

## `git clone`

Copies a remote Git repository to a local computer.

```bash
git clone <repository-url>
```

## `git remote`

Displays remote repository information.

```bash
git remote -v
```

## `git fetch`

Downloads information from a remote repository w
