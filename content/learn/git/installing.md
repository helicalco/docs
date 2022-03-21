---
title: Installing
pcx-content-type: tutorial
weight: 1
meta:
  title: Installing Git
---

# Installing

## Why Version Control?

Git is a version control system that allow you to track changes in your files and directories. It makes it extremely easy to collaborate as it allows changes by multiple people to be merged into one. It works by having a centerally located place where all the changes are stored - github/gitlab. This is often called origin. Then users can clone the repository down to what is called a local version, and make changes to the files. When they are done they can push their changes to the origin.

## Setting up Git

First you want to [make a github account](https://github.com/signup). This will be the platform you'll use to store your origin files.

### Install/Config Git

Now you'll want to install git on your pc. You can do this by installing the [Git](https://git-scm.com/downloads) package.

For command line install (Linux/Mac):

```sh
$ sudo add-apt-repository ppa:git-core/ppa
$ sudo apt update
$ sudo apt install git
```

Once installed, you'll need to do a little bit of configurtion. Firstly, open your terminal and check that git is installed:

```sh
$ git --version
```

You should see something like this:

```sh
$ git version 2.35.1
```

This means that git has sucessfully installed. If this didn't work, take a look at this [webpage](https://github.com/git-guides/install-git).

Once installed, you can config git. First, set up git with your username and email address:

```sh
$ git config --global user.name "your_username"
$ git config --global user.email "your_email@example.com"
```

Then you need to setup sshkeys on the computers you'll be using. Github has dropped support on http authentication, so you'll need to use ssh. For more information about github's http deprecation have a look [here](https://magecomp.com/blog/generate-personal-access-token-github/).

##### Note on Windows Gitbash

On installing Git on windows, an application called gitbash will have installed. This will allow you to run any linux command line commands on windows.

## Setup SSH Keys

### What are SSH Keys?

SSH Keys are used with the SSH network protocol for safely encrypting and transferring data between computers. SSH is a protocol that allows computers to communicate securely without the need for a password. For more information on the SSH protocol, have a look at [this page](https://www.ssh.com/ssh/).

### Creating an SSH Key

You will need to create an SSH key on the computer you're using and copy this over to github. So when you try to connect, you'll will be authenticated using this key.

You may already have an ssh key. So first check these locations for a file call id_rsa.pub:

##### Windows

In windows this is found in Users/\<user\>/.ssh

##### Linux

In linux it's found at ~/.ssh
Change to ssh directory:

```sh
$ cd ~/.ssh
```

Then list contents of directory:

```sh
$ ls
```

You're looking for a file name 'id_rsa.pub'. If you don't see this, you'll need to create one.

If you have one then skip this step.

Create an ssh key by running this command:

```sh
$ ssh-keygen -C <youremail>
```

If it prompts for a place to save just push enter.
Do the same for password (just push enter).

### Link ssh key to github

Copy your ssh key - found in previously mentioned locations.

##### Linux

```sh
$ cat ~/.ssh/id_rsa.pub
```

Highlight and copy the text.

OR copy using the command

```sh
$ pbcopy < ~/.ssh/id_rsa.pub
```

##### Windows

On windows you can do the same command from gitbash or find id_rsa.pub in Users/<user>/.ssh and copy it.

### Add SSH Key to Github

1. Go into settings in github.
![github-settings](../media/github-settings.png)
2. Click on SSH and GPG keys on the left side bar.
![github-ssh-tab](../media/github-ssh-tab.png)
3. Select new SSH key (green bubble to right).
![github-new-ssh](../media/github-new-ssh.png)
4. Paste the SSH key with whatever title you want and hit Add SSH key.
![github-added-ssh](../media/github-added-ssh.png)

### Finishing Up

You're all set. Now you'll will be able to interact with github using git. Take a look at the [next tutorial](../git-workflow) to get started using git with github.
