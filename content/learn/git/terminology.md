---
title: Terminology
pcx-content-type: tutorial
weight: 1
meta:
  title: Terminology
---

# Terminology

### Repository

A repository can be thought of as a directory that stores all versions of files, folders and content regarding a project.

### Clone/Cloning

When you clone a repository you are creating a copy of the repository on your computer.

### Origin (Remote)

An alias for the remote repository that is used to track changes - the repository you will typically clone from. It is the repository that is used to push and pull changes. It is a shared repository that all users can access and exchange their changes. Stored on a hosting service like github or gitlab.

### Main Branch

The default branch. After cloning a project from the remote server, the main branch will be the only branch found in your local repository.

### Branch

A branch is a version of the repository that diverges from the main branch or another. It represents an independent line of development or changes. Being able to merge these changes in the main branch or another.

### Merge

When we have two separate branches with different changes, we can merge them together to create a single branch. We merge one branch into the other - typically into the main branch.

### Push

When you have finished making changes to a branch in your local repository, nothing changes in the remote repository. To update the remote repository to include your changes, you must push those changes. This will update the branch of the same name as your local branch in the remote repository (by default, else updates a branch you specify).

### Pull

The inverse is the same - when changes are made to the remote repository, nothing will change on your local repository. To update your local repository with changes made to the remote repository, you must pull those changes.

### Checkout

When you have multiple branches in your local repository, you can checkout a branch to see the changes made to that branch. Basically, a way to switch between branches.

### Commit

When you commit something to your local repository, your changes will be stored in the current branch you are working on. Commits are like save points except each one of them are accessible to you, rather than the most recent one (traditional save point like MS Word or google docs). Although you can commit multiple times, the most recent one is the one that is accessible to you, unless you manually 'rollback'.

### Staging

The Staging Area is where you can store your changes before you commit them. It is a temporary area that is not accessible to you.
