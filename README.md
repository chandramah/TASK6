
# TASK 6: Host a Static Website with GitHub Pages

## Objective
Deploy a simple static HTML website using GitHub Pages for free hosting.

## Project Overview
This repository contains a basic static website with an `index.html` file, hosted on GitHub Pages. This allows free and easy deployment of static content without any server or backend.

---

## Live Website Link
[https://chandramah.github.io/TASK6/](https://chandramah.github.io/TASK6/)

---

## Git Commands Used

### Initial Setup and Push
```bash
cd "C:\Users\91957\TASK 6"
git init
git remote add origin https://github.com/chandramah/TASK6.git
git add .
git commit -m "Initial commit - Task 6 static website"
git branch -M main
git push -u origin main
````

### Fixing File Rename Issue (Windows case-insensitive system)

Git on Windows does not recognize filename case changes directly, so a two-step rename was done:

```bash
git mv INDEX.HTML temp.html
git commit -m "Rename INDEX.HTML to temp.html"
git mv temp.html index.html
git commit -m "Rename temp.html to index.html"
git push
```

### Handling Remote Conflicts (Pull before push)

```bash
git pull origin main --rebase
```

### Resolving Rebase Conflicts

* Added and removed conflicting files:

```bash
git add index.html
git rm INDEX.HTML
git rebase --continue
```

* If needed, force push after rebase:

```bash
git push origin main --force
```

### Checking Git Status and Committing Changes

```bash
git status
git add index.html
git commit -m "Rename INDEX.HTML to index.html for GitHub Pages"
git push
```

---

## Troubleshooting Faced

* **GitHub Pages 404 Error:**
  Caused by having `INDEX.HTML` instead of `index.html`.
  **Fix:** Rename file to lowercase `index.html` since GitHub Pages is case-sensitive.

* **Git Not Detecting Case Rename:**
  On Windows, Git sometimes ignores file case changes.
  **Fix:** Rename file to a temporary name first, commit, then rename to correct case and commit again.

* **Push Rejected Due to Remote Changes:**
  Remote had commits not present locally.
  **Fix:** Used `git pull origin main --rebase` to sync remote changes before pushing.

* **Rebase Conflict (Rename/Delete Conflict):**
  Git conflicted between renamed and deleted files.
  **Fix:** Resolved conflicts by adding/removing files manually and continued rebase.

* **Unstaged Changes Blocking Pull:**
  Tried pulling with unstaged changes present.
  **Fix:** Staged and committed changes first before pulling.

---

## How to Use This Repo

1. Clone or download the repository.
2. Modify `index.html` or add static assets (CSS, JS, images).
3. Stage, commit, and push changes to `main`.
4. GitHub Pages auto-updates the live site within minutes.

---

## Tools & Technologies Used

* GitHub Repository
* GitHub Pages (for free static website hosting)
* HTML

---

## Outcome

Learned how to deploy static web pages for free using GitHub Pages, and handled real-world Git troubleshooting on Windows.

