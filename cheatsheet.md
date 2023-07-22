# Git Cheatsheet

## Main commands

- `git clone git@github.com:USER-NAME/REPOSITORY-NAME.git`: Clone a repository over SSH. Replace USER-NAME and REPOSITORY-NAME with the actual username and repository name.
- `git remote -v`: Show the URLs that Git has stored for the shortname to be used when reading and writing to that remote, providing an overview of the tracked remote repositories.
- `git status`: Show the status of changes as untracked, modified, or staged.
- `git add FILENAME` or `git add .`: Track new files and stage changes to already tracked files. `FILENAME` is for specific files and `.` is for all changes.
- `git commit`: Commits changes to the local repository. Because you've run `git config --global core.editor "code --wait"`, your commit message will open in VSCode. Write your message, save, and close the tab to proceed.
- `git log`: Show the commit history, displaying author, timestamp, and comments for each commit.
- `git push origin BRANCHNAME`: Upload your committed changes to the specified branch on the remote repository. Replace `BRANCHNAME` with the branch you want to push to. If you don't specify a branch, Git will push to the current branch.
- `git pull origin BRANCHNAME`: Update your local branch with the latest changes from the specified remote branch. If you don't specify a branch, Git will pull from the current branch.
- `git checkout -b BRANCHNAME`: Create a new branch and switch to it. Replace `BRANCHNAME` with the name you want for your branch.
- `git branch`: List all local branches.
- `git diff`: Show the file differences not yet staged.
- `git diff --staged`: Show file differences between staging and the last file version.
- `git rm FILENAME`: Remove a file from your working directory and stage the deletion.

Remember: you can always type `git help `<command>`` to get more information about a specific command.


## The three states

- *Modified* means that you have changed the file but have not committed it to your database yet.
- *Staged* means that you have marked a modified file in its current version to go into your next commit snapshot.
- *Committed* means that the data is safely stored in your local database.

## Working tree, staging area, and Git directory

![areas](https://git-scm.com/book/en/v2/images/areas.png)

The working tree is a single checkout of one version of the project. These files are pulled out of the compressed database in the Git directory and placed on disk for you to use or modify.

The staging area is a file, generally contained in your Git directory, that stores information about what will go into your next commit. Its technical name in Git parlance is the “index”, but the phrase “staging area” works just as well.

The Git directory is where Git stores the metadata and object database for your project. This is the most important part of Git, and it is what is copied when you clone a repository from another computer.

The basic Git workflow goes something like this:

1. You modify files in your working tree.
2. You selectively stage just those changes you want to be part of your next commit, which adds only those changes to the staging area.
3. You do a commit, which takes the files as they are in the staging area and stores that snapshot permanently to your Git directory.

If a particular version of a file is in the Git directory, it’s considered committed. If it has been modified and was added to the staging area, it is staged. And if it was changed since it was checked out but has not been staged, it is modified. In [Git Basics](https://git-scm.com/book/en/v2/ch00/ch02-git-basics-chapter), you’ll learn more about these states and how you can either take advantage of them or skip the staged part entirely.