---
title: Your First Repository
pcx-content-type: tutorial
weight: 2
meta:
  title: Your First Repository
---

# Your First Repository

## Setup From Scratch

### Initialize a Repository

To get started, you'll want to create an empty repository.

```sh
$ git init
```

This will initialize a repository in the file you are currently in. If you want to initialize a repository in a new directory, you can pass an additional argument.

```sh
$ git init /path/to/repository
```

If the /path/to/repository does not exist, it will be created.

### Add Files to Staging

First create some sort of markdown file and add some text to it.

```sh
$ echo "Hello World" > README.md
```

Then add all the files in the current directory to the staging branch (ie the files you want to commit).

```sh
$ git add .
```

If you only want certain files to be added to staging you can use the `git add` command with a file or directory name following `git add my/file`.

If there are certain files that you want `git add .` to ignore, then you can create a `.gitignore` file in the root of your repository. Any file or repository put in this file will be ignored by `git add .`.
For instance:

```
*.log
*.exe
testfiles
```

In the above example, `git add .` will ignore any file or directory that ends with `.log` or `.exe` or is named `testfiles`.

### Commit Changes

Now to commit the changes you've just added to the staging branch.

```sh
$ git commit -m "first commit"
```

`git commit` will commit the changes you've made to the staging branch. You can also add a message to the commit using `-m` - which is highly recommended. All messages should be descriptive, and should be short - less than 50 characters. They should also begin with a lowercase letter.

### Linking to Github

Now you need to setup a remote repository. Head over to [Github](https://github.com/) and create a repository. To do this, click on the `new` button in the top right corner of the right hand side bar.
![new repository button](../media/github-new-repo-button.png)

It will then ask for a name and an optional description. You will be given a choice between public and private. Public means anyone who comes across your github page can see your repository. Private means only you can see your repository. You can change this later.

Below that are some options to initialize the repository with. Leave the options unchecked, if set they can create conflicts between your local and remote repository.

![github repository options](../media/github-initialize-options.png)

### Link Remote and Push

You have now successfully created a repository on github. Now you need to link the remote repository to your local repository. You will see some commands in your newly created empty repository on github. Take a look at the ones regarding pushing an existing repository.

![github connect local to remote](../media/github-connect-remote.png)

Lets work through these commands.

```sh
$ git remote add origin git@github.com:helical-tutorials/my-first-repository.git
```

This will add a remote repository called `origin` to your local repository. This is the name of the remote repository. If you are to access any branch directly on the remote, you prefix the branch name like `origin/<branch>` or `origin <branch>`. So this command links your local repository to the remote repository.

```sh
$ git branch -M main
```

You can ignore this command if you've downloaded git recently. Github used to have the default branch called master. This will change the name of the default branch from master to main.

```sh
$ git push -u origin main
```

This command will push everything in your staging area of the current branch into the main branch of origin. The `-u` simply sets the upstream of the current branch to origin main. Which means in future, you can simply write `git push` and it will push everything to the main branch of origin.

And there it is. You've made a remote repository and linked it to your local repository. You can now push your changes to the remote repository. Try making a change to one of your files and then push your changes to the remote repository. Here are the commands you will need:

```sh
$ git add .
$ git commit -m "made some changes"
$ git push
```

## Cloning a Repository

For this, you are going to clone your recently created repository from github into a new local repository.

Firstly, you need to create a new directory to clone the repository into. Then head over to github and select the repository you want to clone.

Click on the green code button, then the ssh tab. Copy the link provided.

![github clone link](../media/github-clone-code.png)

Using this link, head back to your terminal and within the empty directory you created, run the following command:

```sh
$ git clone git@github.com:helical-tutorials/my-first-repository.git .
```

If you don't want to create a directory yourself, you can instead run:

```sh
$ git clone git@github.com:helical-tutorials/my-first-repository.git directoryName
```

This will create a directory that contains the repository within it.

Another option is to automatically create a directory with the same name as the github repository.

```sh
$ git clone git@github.com:helical-tutorials/my-first-repository.git
```

Great, you've successfully cloned your repository. You can now make changes to the files in the repository and push them to the remote repository.
