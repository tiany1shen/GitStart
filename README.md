# GitStart

My first GitHub repository for learning Git and GitHub.

## Git 

Git is a free and open source distributed version control system.

### Install Git for Windows

Download Git for Windows at [git-scm.com](https://git-scm.com/download/win) or use a [mirror](https://registry.npmmirror.com/binary.html?path=git-for-windows/). 

### First-Time Git Setup

Set your identity once you have installed Git use
``` 
git config --global user.name "YourUserName"
git config --global user.email "YourUserEmail"
```
Every Git commit uses this information. You can used the username and useremail related to your GitHub account to setup the Git identity.

### Create a Git repository

Change a directory into a Git repository by the following commands:
```
cd Your/Project/Directory 
git init
```
A `.git` directory will be added into the project, which shows that this project is now controlled by Git. Use 
```
ls -ah
```
to check it exists. 

### Tracking files

Now the repository is still empty, you should track some files and do an initial commit use `git add` and `git commit` commands. First create and edit a file in the project directory.
```
type nul>README.md
# do some edition

git add README.md
git commit -m "docs: initial commit"
```

At this point, you have a Git reposity with a tracked file and an initial commit. You can use the following command to check those tracked files.
```
git ls-files
```