---
title: Essential Commands
pcx-content-type: tutorial
weight: 4
meta:
  title: Essential Commands
---

# Essential Commands

## Using Branches

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

Deletes `new-branch`.
