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

See [the Pro Git book Sec. 2](https://git-scm.com/book/en/v2/Git-Basics-Getting-a-Git-Repository) for more Git basics including:

- getting a repository
- recording changes
- viewing commit history
- undoing things
- working with remotes
- tagging
- Git aliases

#### Frequently used commands

```
git init        # initialize a local repository
git clone       # clone a remote repository

git add         # add file into Staging Area
git commit      # commit Staging Area to Repository

git status      # show the working tree status
git log         # show history of current branch
git reset       # reset current HEAD

git remote -v   # show all remote repository
git fetch       # download all remote changes
git pull        # git fetch + git merge
git push        # upload local branch to remote
```

### Git Branching

Git supports efficient branching operations. Here we create a new branch named `branching`, in which we edit content of this section. Meanwhile, we add some content into the previous section in the `main` branch. 

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

Now we have two different branch of this project: in `main` branch, this `README.md` file have a *Frequently used commands* section; while in `branching` branch, this file have new content about Git Branching. One can use `git merge` command to merge the `branching` branch into the `main` branch:
```
git checkout main
git merge branching
```
Since we change different part of the `README.md` file, there is no merge conflict. Git will automatically create a merge commit. Now that your work is merged in, you can delete the `branching` branch by
```
git branch -d branching
``` 

## GitHub

GitHub is the single largest host for Git repository. You can host your project source code on GitHub remotely. 

### Upload Local Repository to GitHub

Once you have create a new repository on GitHub, you can relate it to your local Git repository. See [the Pro Git book sec. 6.1](https://git-scm.com/book/en/v2/GitHub-Account-Setup-and-Configuration) for details of SSH access. 

#### Clone remote repository

Use `git clone` command to download remote repository to local directory, and the downloaded local repository is automatically related to the remote one.
```
git clone git@github.com:UserName/RepoName.git
git remote
```

#### Relate a local Git repository to remote one

Use `git remote add` command to relate local repository to remote one
```
git remote add origin git@github.com:UserName/RepoName.git
git remote
```

#### Synchronize local and remote files

Use `git pull` command to synchronize remote updates to local and `git push` command vise versa.
```
git pull origin main
git push origin main
```

### Delete remote files

You can delete a remote file while maintaining the local copy by
```
git pull origin main
git rm -r --cached Dirname
git commit -m "delete Dir"
git push origin main
```
