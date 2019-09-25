---
author: Durban G. Keeler
date: 27 September 2019
---

# U of U Cryosphere Lab: An Introduction to Using Git and GitHub

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

