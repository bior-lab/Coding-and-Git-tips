# Coding and Git tips

## Setting the repository on your own PC using Git

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

## Push your updates to GitHub

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

## Coding tips
- It is recommended to use **Visual Studio Code** as your main editor. It allows you to open an integrated terminal, preview Markdown files (README), and manage Git directly.

- For more information on **common Unix commands** (e.g., ```cd```, ```ls```, ```rm```), please check [here](https://web.stanford.edu/class/archive/cs/cs107/cs107.1212/resources/).

- For more information on **version control** with Git, please see the cheat sheet [here](https://git-scm.com/cheat-sheet).

- Try asking ChatGPT for help first. It can quickly guide you through common problems.
