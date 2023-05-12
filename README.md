# GitStart

My first GitHub repository for learning Git and GitHub.

## Git 

Git is a free and open source distributed version control system.

### Git Installation and Setup

#### Download and install Git for Windows

Download Git for Windows at [git-scm.com](https://git-scm.com/download/win) or use a [mirror](https://registry.npmmirror.com/binary.html?path=git-for-windows/). 

#### First-time Git setup

Set your identity once you have installed Git use
``` 
git config --global user.name "YourUserName"
git config --global user.email "YourUserEmail"
```
Every Git commit uses this information. You can used the username and useremail related to your GitHub account to setup the Git identity.

### Local Git Options

#### Create a Git repository

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

#### Tracking files

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

#### Other Git basics

See [the Pro Git book Sec. 2](https://git-scm.com/book/en/v2) for more Git basics including:

- getting a repository
- recording changes
- viewing commit history
- undoing things
- working with remotes
- tagging
- Git aliases

### Git Branching

Git supports efficient branching operations. Here we create a new branch named `branching`, in which we edit content of this section. Meanwhile, we add some content into the previous section in the `master` branch. 

#### Create a new branch 

You can run `git branch` to create a new branch and run `git checkout` to switch between branches.
```
git branch branching
git checkout branching
```
Or you can run `git branch` with the `-b` argument to do so at the same time.
```
git branch -b branching
```

#### Merge branch

Now we have two different branch of this project: in `master` branch, this `README.md` file have a *Frequently used commands* section; while in `branching` branch, this file have new content about Git Branching. One can use `git merge` command to merge the `branching` branch into the `master` branch:
```
git checkout master
git merge branching
```
Since we change different part of the `README.md` file, there is no merge conflict. Git will automatically create a merge commit. Now that your work is merged in, you can delete the `branching` branch by
```
git branch -d branching
``` 