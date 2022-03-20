---
title: Git Workflow
pcx-content-type: tutorial
weight: 2
meta:
  title: Git Workflow
---

# Git Workflow
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


Then you want to type
git add .
This adds all the files to the staging branch (ie the files you want to commit)

Then type
git commit -m "first commit"
This commits all files in the staging branch (basically saying commit all my changes to memory)
-m means to add a message
Write whatever you want as the message (under 50 characters if you can)

One thing to do is to make sure your master branch is actually changed to main (this is to stop clashes with the recent change github has made). You
only ever need to do this once.
git branch -M main
Now you need some way to link this repository and the empty one on github together. Go into github and in the repository at the top you will see Set up in Deskop or HTTPS | SSH. Click on SSH and copy the link. Should look similar to this git@github.com:BlaviButcher/something.git
In your terminal type:
git remote add origin <that copied link>
Once that is complete you can push all your repository to the mothership
git push -u origin main
What to do on each change
From here on out. Any time you make a change to something you can commit it

git add .
git commit -m "Made another change"
And when you are ready for those changes to go to the mothership use
git push -u origin main
Now for the second computer
Once everything has been pushed from the first computer. Refresh your github. Make sure you're in the repository. The page should look different. Up the top right there should be a green button that says code. Click on it and select the ssh tag. Copy the text in here (should be the same as the link you used for remote).

Then create a folder and cd into it and type:

git clone git@github.com:BlaviButcher/firstPhaserGame.git

If you don't want to create a folder and cd you can just write:
git clone git@github.com:BlaviButcher/firstPhaserGame.git folderName

And it will create a folder for you in the current directory.

That should be sorted.

Keep changes in sync
Now lets say you make changes on computer 2 and push them to the mothership. Computer 1 is now behind. So when you jump on computer 1 next time you need to type:
git pull

This will pull all the data from the mothership and once again everyone will be the same.

There will be times where you let it get out of sync. Google will be your friend in these times. The best way to avoid it is to be proactive. Always make sure you have commited and pushed from one computer before working on the other computer. And don't make any changes one one computer without first pulling from the mothership.

Future
Given that I was trying to keep this simple there will be some things that I haven't explainedin detail (branching, staging, production etc) or having explained things in a way that isn't quite correct, but makes things easier to understand. If anyone wants to go into more depth or has any correction we would all be very grateful. And yes I'm aware that the mothership analogy doesn't take into account that the mothership is technically cloned too! smile

If anyone has any issues please feel free to contact me on discord: BlaviButcher#3698
