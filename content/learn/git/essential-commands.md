---
title: Essential Commands
pcx-content-type: tutorial
weight: 4
meta:
  title: Essential Commands
---

# Essential Commands

## Branch

A branch is a version of the repository that diverges from the main branch or another. It represents an independent line of development or changes. It allows you to make changes to your repository without breaking the already working code.
![Branching](../media/branching.png)

```sh
$ git branch
```

Lists all branches in your repository.

```sh
$ git branch new-branch
```

Creates a new branch call `new-branch`.

```sh
$ git branch -d new-branch
```

Deletes `new-branch`. It won't delete if there are unmerged changes. `-D` deletes the branch even if there are unmerged changes.

## Checkout

Checkout is a way to switch between branches, often referred as 'checking out'.

```sh
$ git checkout <branch>
```

This will change the current branch to the specified branch.

Rather than using `git branch` to create a new branch you can use checkout.

```sh
$ git checkout -b <branch>
```

This will create a new branch based on the current branch and checkout to the new one.

## Merge

Merging allows you to merge one branch into another. For instance, imagine you have a main branch, and you would like to implement a feature on it. You can create a new branch, implement and test the feature, and then merge it into the main branch.

Before merging you want to make sure you are on the branch that you would like to merge into. You can use `git branch` to list all branches and look for a green highlighted and/or a asterisk next to a branch name. Another option is to use `git status` to see which branch you are on. At the top it will say `On branch <branch>`.

### Fast-Forward Merging

This is the most simple of all the merges. It can be done when no branch has diverged from each other. If you have a main branch and create a feature branch from main. You do some work to the feature branch, but main remains untouched. Then you want to merge feature into main, this would be a fast-forward merge. Main is simply being fast-forwarded up to the point where feature branch is.

```sh
$ git merge <branch>
```

An example of an entire process from branch to merge:

```sh
# Start a feature
$ git checkout -b feature main
# Make some changes to the feature
$ git add <file>
$ git commit -m "changes made"
# Merge in the new-feature branch
$ git checkout main
$ git merge feature
# Delete as no longer needed
$ git branch -d feature
```

The merge will not be documented in the logs as there was no merge commit. To generate a merge commit when fast-forwarding use:

```sh
$ git merge --no-ff <branch>
```

### 3-way merge

If main were to have changes made to it while the feature branch also had changes, the merge would need to be a 3-way merge as there is no linear way for main to be fast-forwarded to the point where the feature branch is. A 3-way merge uses a dedicated commit to combine the two histories of the branches together. The merge command called is identical:

```sh
# Start a feature
$ git checkout -b feature main
# Make some changes to the feature
$ git add <file>
$ git commit -m "changes made"
# Merge in the new-feature branch
$ git checkout main
# Changes made in main
$ git add <file>
$ git merge feature
# Delete as no longer needed
$ git branch -d feature
```

The difference is that the merge commit is created.

### Merge Conflicts

When merging two branches, if the same file is edited on both branches, Git won't know which version to use. This is called a merge conflict. Git will stop a merge if a conflict occurs. To see what files have a conflict use:

```sh
$ git status
```

Git will automatically edit the affected files by adding symbols to easily distinguish the two versions.

```sh
here is some content not affected by the conflict
<<<<<< main
this is conflicted text from main
=======
this is conflicted text from feature branch
>>>>>> feature branch;
```

The branch before `=======` is the receiving branch and after is merging branch.

Once you have fixed up the conflicts by editing the files, you can use `git add` to add the corrected files. Then use `git commit` to create a merge commit.

## Pull
```sh
$ git pull <remote> <branch>
```

Will pull all changes from the remote branch into the current branch. If the local branch is tracking a remote branch, you can instead use `git pull` to pull the changes from the remote branch into the local branch.

## Push
```sh
$ git push <remote> <branch>
```

Will push all committed changes to the remote branch. You can also add the `-u` flag, which will set the local branches upstream to the remote branch mentioned. This allows you to use `git pull` and `git push` without mentioning branch names in the future.

## git init
```sh
$ git init
```

Creates a new repository in the current directory.

## git add
```sh
$ git add <file>
```

Adds file or files to the staging branch.

## git commit
```sh
$ git commit -m "commit message"
```
Commits file/files in the staging branch to the repository.

## git clone
```sh
$ git clone <url>
```
Clones a repository from a remote.

## git log
```sh
$ git log <branch>
```
Lists all commits in the branch.

## git status
```sh
$ git status
```
Shows the current branch you are on and additional information relative to the branch.

## git remove
```sh
$ git rm <file>
```
Removes file from the staging branch and stops tracking it.
