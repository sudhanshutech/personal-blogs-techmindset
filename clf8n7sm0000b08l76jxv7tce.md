---
title: "Git Commands- That You Don't Know"
seoTitle: "Git commands-That you don't know"
datePublished: Tue Mar 14 2023 19:25:05 GMT+0000 (Coordinated Universal Time)
cuid: clf8n7sm0000b08l76jxv7tce
slug: git-commands-that-you-dont-know
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/UT8LMo-wlyk/upload/382cc06db496bbcdded5cb6475853b27.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1678821704627/f290401c-a130-4031-8846-ad7786e90422.jpeg
tags: github, opensource, git, commands, layer5

---

As developers, we rely heavily on Git and GitHub to track changes to our code and collaborate with others. However, there are times when we may encounter issues or situations that require more specialized commands beyond the basic ones we are familiar with. In this article, we will explore some of the most popular but **unknown Git commands** that can help us solve problems more efficiently and effectively.

### Undo a Merge Commit in Git

The Git reset command helps you to undo merge commits.

For this, we must know the hash/id of the commit to go to the previous commit and to get the hash run `git log` or `git reflog`

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1678805981386/70761b46-f137-4539-a89a-2078bf27dea3.png align="left")

After getting the hash run `git reset --merge previous commit`

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1678806213938/500473bf-9935-439c-b9b0-46d2ab9da1fb.png align="left")

---

### Difference between the two files

The `git diff` the command is used to show the differences between two sets of code changes. This command is most commonly used to compare the changes made in your local codebase to the changes made in the remote repository on GitHub or another hosting service.

1. To compare the changes made in the working directory to the last commit, you can run:
    
    ```bash
    git diff
    ```
    
2. To compare the changes made in a specific file to the last commit, you can run:
    
    ```bash
    git diff <file>
    ```
    
3. To compare the changes made in the working directory to a specific branch, you can run:
    
    ```bash
    git diff <branch>
    ```
    

To compare the changes made in a specific file between two branches, you can run:

```bash
git diff <branch1> <branch2> <file>
```

---

### Forgot to stage a file

It often happens that we forgot to stage a file and we do the commit. So don't worry we have a solution for this as long as we have not pushed the commit.

```bash
git config --global alias.commend 'commit --amend --no-edit
```

After setting up this command do the process we do as usual to stage a file.

`git add <file name>` and then `git commend`  
This will open the default text editor to show the commit message of the most recent commit. If you're satisfied with the existing message, you can save and exit the editor to complete the amend.

---

### Git merc

The command `git config --global alias.merc 'merge --no-ff`the command creates a Git alias called `merc` that allows you to merge branches with the `--no-ff` option. The `--no-ff` the option tells Git to create a merge commit even if it's a "fast-forward" merge, where Git can automatically apply the changes in one branch to the other without creating a new commit.

1. First, make sure you're on the branch that you want to merge changes into. You can use the `git branch` command to see the current branch and the available branches:
    
    ```bash
    git branch
    ```
    

Use the `git merge` command with the `--no-ff` option and the branch name you want to merge from. For example, if you want to merge changes from a branch called `feature-branch` into the current branch, you can run:

```bash
git merc feature-branch
```

This will create a merge commit with the changes from the `feature-branch` branch, even if it's a fast-forward merge.

Alternatively, you can use the `git merge` command directly with the `--no-ff` option:

```bash
git merge --no-ff feature-branch
```

This will also create a merge commit with the changes from the `feature-branch` branch, even if it's a fast-forward merge.

---

### Git cherry-pick

`git cherry-pick` is a way to pick a commit from one branch and put it into another.  
For example, if accidentally you commit to the wrong branch so don't worry you can undo your changes just by switching to the actual branch and cherry-pick the commit to where it should belong.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1678819701507/62beece0-4ee3-4c1e-bcc4-de70553c11eb.png align="left")

Before running this command first get the id of commit and the switch to the actual branch and do `git cherry-pick <commit-ref>`