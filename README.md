# Coding and Git tips

## 1. General coding tips
- It is recommended to use **Visual Studio Code** as your main editor. It allows you to open an integrated terminal, preview Markdown files (README), and manage Git directly.

- For more information on **common Unix commands** (e.g., ```cd```, ```ls```, ```rm```), please check [here](https://web.stanford.edu/class/archive/cs/cs107/cs107.1212/resources/).

- For more information on **version control** with Git, please see the cheat sheet [here](https://git-scm.com/cheat-sheet).

- Try asking ChatGPT for help first. It can quickly guide you through common problems.

## 2. Git setup

### 2.1 Setting the repository on your own PC using Git

1. Download and install Git from https://git-scm.com/downloads
2. Verify installation. Open your terminal and check that Git is installed correctly:
```
git version
```
3. Navigate to your working directory. Open the terminal and move to the folder where you plan to store and edit the repository:
```
cd /path/to/your_folder
```
4. Initialize Git (optional if cloning directly)
```
git init
```
5. Clone the repository. Download the specific repository from GitHub:
```
git clone https://github.com/bior-lab/YOUR-REPO-NAME.git
```
6. Enter the repository folder
```
cd YOUR-REPO-NAME
```

### 2.2 Push your changes to main

After you finish editing or adding files, follow these steps to upload your work:

1. Check which files have been changed
```
git status
```
2. Stage the files you want to upload (. means add all changes)
```
git add .
```
3. Commit your changes with a short message
```
git commit -m "Your msg here to indicate the major changes"
```
4. Push your work to GitHub
```
git push origin main
```
5. Verify your upload

Go to your GitHub repository page. Check that your new files and commit message appear in the repo.

Note: Run ```git pull``` before each new task to push to make sure you’re working on the latest version of the repository. Before pushing new changes made by you, you need to incorporate the previous changes made by other repository contributors.



## 3. Push your changes to your own branch via a PR (if a review is needed)

The basic idea: we co-develop an app together, and every improvement you make needs to be reviewed by the product manager before it goes into the official version.

The `main` branch is protected, so you **cannot push to `main` directly**. Instead, you make your changes on your own **branch** and then ask for them to be merged into `main` through a **Pull Request (PR)**. A reviewer will check your changes before they are merged.

Think of it this way:
- `main` = the official version that everyone uses
- your branch = your personal working copy
- Pull Request = "Please review my changes and add them to the official version"

### 3.1 Get the latest version

Before starting any new task, make sure you are on `main` and up to date:

```
git checkout main
git pull
```

### 3.2 Create your own branch

Create a new branch and switch to it. Use your name and a short description, e.g. `maomao-version`:

```
git checkout -b yourname-short-description
```

You only need to do this once per task. To check which branch you are on, run `git branch` (the current branch is marked with `*`).

### 3.3 Edit, stage, and commit

Make your changes, then:

```
git status
git add .
git commit -m "Your msg here to indicate the major changes"
```

### 3.4 Push your branch to GitHub

Push your **branch** (not `main`):

```
git push origin yourname-short-description
```

### 3.5 Open a Pull Request

1. Go to the repository page on GitHub. You will see a yellow banner saying your branch had recent pushes. Click **Compare & pull request**.
2. Make sure it says `base: main` ← `compare: yourname-short-description`.
3. Write a short title and description of what you changed and why.
4. Click **Create pull request**.

### 3.6 Wait for review

The reviewer (e.g., Haoxuan) will check your PR. They may:
- **Approve and merge** it. Done!
- **Leave comments** asking for changes. Make the changes on the same branch, then `git add`, `git commit`, and `git push origin yourname-short-description` again. The PR updates automatically.

### 3.7 After your PR is merged

Switch back to `main` and pull the latest version before your next task:

```
git checkout main
git pull
```

For a new task, go back to Section 3.2 and create a new branch.

### 3.8 Common problems

| Problem | Solution |
|---|---|
| `git push origin main` is rejected | `main` is protected. Push your own branch instead (Section 3.4). |
| I made changes on `main` by mistake | Run `git checkout -b yourname-short-description` to move your uncommitted changes to a new branch, then continue from Section 3.3. |
| I'm not sure which branch I'm on | Run `git branch`. |
| My PR has conflicts | Ask the reviewer for help. |

