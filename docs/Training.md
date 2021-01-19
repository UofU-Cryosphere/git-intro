---
title: "U of U Cryosphere Lab: An Introduction to Using Git and GitHub"
author: Durban G. Keeler
date: 27 September 2019
---

# An Introduction to Using Git and GitHub

This serves as an introductory guide to help interested lab members learn how to use `Git` and GitHub.
These are the most used variant of version control and therefore represent valuable skills for anyone interested in code use and code development (especially of an open source nature).
Git is far too powerful of a tool to learn in a single training, but this should help you at least get started with the tool and familiarize yourself with it sufficiently to seek out answers to future questions.
[Stack Overflow](https://stackoverflow.com/) is a great resource for finding all sorts of answers regarding `Git`, as is the tutorial website for GitHub, [GitHub Guides](https://guides.github.com/).

In this introduction, you will learn a little background behind Git and GitHub, how to create a new repository on GitHub, how to clone an existing repository on GitHub to your local machine, and how to perform some basic tasks using Git and GitHub.

## What is version control?

Version control allows you to keep a record of all the changes you have made to files throughout the whole time you are working on them.
Even when you are not collaborating with anyone else, this can be extremely useful.
For instance, is this experience familiar?
[](Figures/phd101212s.png)
Version control allows you to avoid this tangled mess of document naming with a continuously-updated version of your code that still allows you to return to previous states.
This makes for excellent backups of your code, so if you make an edit that unintentionally breaks important things, you can simply roll back your changes to a previous state.
Version control also greatly facilitates code collaboration between different individuals.

The basic idea behind Git and version control generally is to save a base version of a file and then save only the changes made to it at each step along the way.
You can combine the base file with a list of changes (or several lists of changes) to get back a snapshot of the file at any point in time.
A version control system is a tool that keeps track of these changes for us and helps us version and combine (or *merge*) our files.
It allows you to decide which changes make up the next version, called a *commit*, and keeps useful metadata about them.
The complete history of commits for a particular project and their metadata make up a *repository*.
Repositories can be kept in sync across different computers facilitating collaboration among different people.





the idea of local and remote repositories (the Git name for code projects).
An individual is able to keep a copy of the code locally on their computer (the *local* repository).
From there, they can make edits and changes to the code without it affecting other people's local repository or the central code (the *remote* repository).
Once an individual is satisfied with the changes, they can *push* those changes to the *remote* repository, where those changes are available for other users to access.
All the snapshots of changes made to the repository throughout time (a *commit* in Git-speak) are saved in the repository history, and you are able to review/revert back to the exact version of your code as it existed for any commit in your code history.
Later in the training, we will also discuss several other topics like *branches* (which allow you edit your code without fear of ruining what already works) and *tags* (where you can save a specific version of your code for future reference).

# Git Training

This is intended as a instructions and tutorials page for learning how to use Git and GitHub.
Prior to the in-lab training on Git/GitHub, please complete the prerequisite steps so that we can get right into using Git during the training.

## Prerequisites

Prior to the lab training meeting, you will need to sign up for a [GitHub account](https://github.com/).
Simply follow the GitHub link and create an account (or scroll to the top of the page and click *Sign Up*).
We will also do a lot of this intro using the Git command line.
Even though there are many IDEs that offer git integration directly, it's important to understand the basics of `Git` so you can troubleshoot later when necessary or if you need more advanced control of your repositories.
You will therefore need to install Git to your personal machine.
There are various ways to do this, but [this website](https://www.atlassian.com/git/tutorials/install-git) has a nice walk-through for each system.
Complete steps 1-4 for your respective computer OS.
In Step 4 (the configuration step), you will want to use the email address associated with your GitHub account, as this will make some later parts of the training more straightforward.

For macOS, unless you are familiar with the other methods, I would recommend sticking with the *Git for Mac Installer* method.
For Windows users, I would recommend using the *Git for Windows stand-alone installer* option.
Make sure the option to install *Git Bash* is also selected (although I believe the default is to install *Git Bash* along with Git Command and Git GUI).
You can use any of the three you wish, but in the training we assume the use of *Git Bash*.
Also for Windows, after installing Git and Git Bash, you can verify it succeeded by opening a Bash (or Command Prompt) terminal and running:
```
$ git --version
```
For both Windows and MacOS, don't worry about using the Git Credentials Helper the Atlassian link talks about in Step 5.
It does add some convenience, but is not necessary for the training, and you can always do it later if you wish.

If everything went smoothly, you should now have an active GitHub account, and Git installed and minimally configured on your machine. Yay! Make sure to bring your personal computer to the lab training if at all possible, as this will make it much easier for you to follow along and try out the different exercises.

If you have any questions or issues with setting up Git and GitHub prior to the lab training, don't hestitate to ask for help. I (Durban), Matt Olsen, or any of the other grad students/post docs familiar with Git would be happy to help you out!

### Optional additions

The following are some additional steps you may want to take, but are not absolutely necessary to be ready for the training.
The default editor in Git is called Vim.
If you know you want to use something different (I for instance, prefer to use Nano), you can also set that option in the command line (the Bash terminal) with the following command:
```
$ git config --global core.editor <name of editor to use>
```
Note that on Windows, you will have to specify the full path to the editor executable file ([this website](https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup) offers a bit more guidance on this).
If you want to switch to the Nano editor, most modern macOS machines come with it pre-installed, while Windows machines will need to download and install it (that can be done following the directions on [this website](http://www.oznetnerd.com/git-nano-windows/)).

If the instructions about using a different editor don't make much sense, don't worry about it.
The default Vim editor will also work just fine.
If you are unfamiliar with Vim and want some background prior to the training, you can check out [this website](https://scotch.io/tutorials/getting-started-with-vim-an-interactive-guide) or many similar ones from a Google search.

Finally, if you are interested in having text color highlighting with git, you can set that option with the Bash command:
```
$ git config --global color.ui "auto"
```

## Tour of GitHub

## Creating a new repository on GitHub

1. Log in to your GitHub account
2. On the left-hand side, select "New" to create a new repository
3. Name it whatever you want (e.g. "git-practice") and add a description if you want of what the repo is for
4. Choose "Public" or "Private" for the repo (for these exercises it doesn't actually matter)
5. Check the box to initialize the repo with a README doc
6. Click "Create repository"

Congratulations, you just made a repository on GitHub!
The main point of GitHub, however, is to house your code in a manner that is easy to manage and accessible by others to promote code sharing and collaboration.
Most of the actual development of code will take place on your (and your collaborators') local computers.
To manage your projects locally and to keep them in sync with GitHub and each other, we use *Git*.
We will now introduce you to this application, show you some of the most commonly used commands, and allow you to practice them with your newly-created GitHub repository.

## Git command line

All git commands start with the keyword `git` followed by various other commands and options.
These are accessed using the command line terminal (or *Git Bash* terminal in Windows).
After launching a terminal window, you can get a list of all the possible git commands by typing `git` at the command line prompt:
```
$ git
usage: git [--version] [--help] [-C <path>] [-c name=value]
           [--exec-path[=<path>]] [--html-path] [--man-path] [--info-path]
           [-p | --paginate | --no-pager] [--no-replace-objects] [--bare]
           [--git-dir=<path>] [--work-tree=<path>] [--namespace=<name>]
           <command> [<args>]

These are common Git commands used in various situations:

start a working area (see also: git help tutorial)
   clone      Clone a repository into a new directory
   init       Create an empty Git repository or reinitialize an existing one

work on the current change (see also: git help everyday)
   add        Add file contents to the index
   mv         Move or rename a file, a directory, or a symlink
   reset      Reset current HEAD to the specified state
   rm         Remove files from the working tree and from the index

examine the history and state (see also: git help revisions)
   bisect     Use binary search to find the commit that introduced a bug
   grep       Print lines matching a pattern
   log        Show commit logs
   show       Show various types of objects
   status     Show the working tree status

grow, mark and tweak your common history
   branch     List, create, or delete branches
   checkout   Switch branches or restore working tree files
   commit     Record changes to the repository
   diff       Show changes between commits, commit and working tree, etc
   merge      Join two or more development histories together
   rebase     Forward-port local commits to the updated upstream head
   tag        Create, list, delete or verify a tag object signed with GPG

collaborate (see also: git help workflows)
   fetch      Download objects and refs from another repository
   pull       Fetch from and integrate with another repository or a local branch
   push       Update remote refs along with associated objects

'git help -a' and 'git help -g' list available subcommands and some
concept guides. See 'git help <command>' or 'git help <concept>'
to read about a specific subcommand or concept.
```

## Cloning

Git is able to a ton of really useful things, but we will focus on a few of the basic commands that are most commonly used.
The first one we will discuss is `git clone`, which allows us to take an existing repository from GitHub and copy it to our local machine.
On your local machine, navigate to the location you would like to place your repository (using `cd <path to location to save repo>` in the terminal), and enter the following into the command line terminal:
```
$ git clone <web address of copied GitHub repo>
```
After performing this step, you should have an exact duplicate of your GitHub repository on your local machine (which currently only consists of a README file and a few git-specific files).
You can confirm this by using the `status` command:
```
$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
nothing to commit, working directory clean
```
This informs you which *branch* of your repo you are on (we'll talk about branching later), whether your local copy is in sync with your remote copy on GitHub ("origin/master"), and whether any recent changes have not yet been added to the repository tracking (a *commit* in git-speak).
`git status` is likely the single most used command for git, as it provides a quick summary of where you are currently at and what should happen next.

## Staging edits

The next step will be to make some changes to the repository, and see how we can track those changes.
First, open the README.md file so we can make some changes.
You can use any editor you want for this (Notepad++, Nano, Vim, Rstudio, etc.); Git is entirely editor agnostic.
For this example, I am using Nano.
```
$ nano README.md
```
This opens the file, which for me currently reads:
```

# git-practice
For practicing with git
```
I will now make some changes to the file.
```

# git-practice
For practicing with git

Here are some changes to the file.
Wow that was super fun.
```
Now save the changes and then go back to the terminal to see how that affected the git repository.

If we run `git status` again, we get the following:
```
$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

      modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
```
This now says (in addition to what branch we are on and that the local branch is up-to-date) that we have some changes that have yet been *staged*.
You stage a change in preparation to officially add that change into your local repository's history, a process known as a *commit*.
As the `git status` output states, we use `git add <filename>` to stage the changes in any file we wish to include in the next commit.
Alternatively, we can throw away our changes and revert back to the latest version of a file in the local history using `git checkout -- <filename>`.

**Bonus note**: *If you have several files you wish to add/remove from the staging area, you can use a '.' to select them all at once. For example,* `git add .` *will add all changed files to the staging area.*

Let's add our change to the staging area (git also supports tab completion of file names)
```
$ git add README.md
```
and check the status again
```
$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	   modified:   README.md
```

## Committing

When we *commit* a change, we add those changes into the recorded history of the git repo.
At this time, it will be assigned a unique identifier so that we can review our code at that specific state at anytime we wish.
To commit our currently-staged changes, enter `git commit` into the terminal.
This should open an editor window with the following message:
```

# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.
# On branch master
# Your branch is ahead of 'origin/master' by 1 commit.
#   (use "git push" to publish your local commits)
#
# Changes to be committed:
#       modified:   README.md
#
```
It's considered good practice to always include a message along with the commit, briefly explaining what changes are included in the commit.
That's what this editor window is intended for.
In fact, Git will actually abort the commit if you refuse to provide a commit message.
Go ahead and add a message for this commit:
```
Adds additional detail to the README doc.
# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.
# On branch master
# Your branch is ahead of 'origin/master' by 1 commit.
#   (use "git push" to publish your local commits)
#
# Changes to be committed:
#       modified:   README.md
#
```
and save the edits.

BOOM!
You just made a commit.
Git then outputs the commit's unique identifier, your commit message, and some summary details about the changes made.

## Pushing/pulling

After performing a local commit, if we check the status again:
```
$ git status
On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)
nothing to commit, working directory clean
```
we see a couple of things.
At the end, we see that there are now no changes to commit.
We also see that our local branch is now out of sync with the remote branch by 1 commit.
*Pushing* is the process of merging recent commits on your local computer to your remote repository copy on GitHub, while *pulling* takes new commits on GitHub and adds them to your local history.
This is accomplished by the straightforward command
`''
$ git push origin master
```
Here the `origin` refers to your remote repository on GitHub, while `master` is the name of the *branch* we are pushing to (more on branches later).
The terminal will then prompt you to authenticate with your GitHub username and password.
If that is successful (i.e. you have access to the repository you are attempting to push to), the terminal will output some info about the process and finally state that the push was successful with `master -> master`.
Checking the status shows
```
$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
nothing to commit, working directory clean
```
that we are back in sync with our remote repo.
If we go to the repository on GitHub, we can see the changes made, as well as the different commits that now reside in the history.
You have now successfully pushed a commit to a remote repository.
Later on in the tutorial we will walk through pulling commits to your local machine, but it's the same process just in reverse.

## Branching

## Collaboration

### Add a collaborator

- Add neighbor as collaborator in GitHub
- Create new branch

### Merge conflicts



## Workflow suggestions



### Issues

### Pull Requests

### Versions/tags
