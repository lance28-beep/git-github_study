# Git and GitHub

Source Study:
[FreeCodeCamp](https://youtu.be/RGOj5yH7evk)/

## Anu nga ba ang Git?

- most commonly used version control system
- <b>Version control</b> also known as source control is the practice of tracking and mananging changes to software code.
- Git tracks the changes you make to files, so you have a record of what has been done.
  -Free and open source version control system
- most widely used version control system in development.
- most programmers interact with git on a daily basis.

## What is Version Control

the management of changes to documents, computer programs,large websites, and other collections of information.

## Terms

- <em>Directory</em> - Folder
- <em>Terminal or Command Line</em> - Interface for Text Commands
- <em>C-L-I</em> - Command Line Interface
- <em>CD</em> - Change Directory
- <em>Code Editor</em> - Word Processor for Writing Code
- <em>Repository</em> - Project, or the folder/place where your project is kept
- <em>Git</em> - the tool that tracks the changes in your code over time
- <em>Github</em> - A website to host your repositories online

## Git Commands

- <em> clone </em> - Bring a repository that is hosted somewhere like Github into a folder on your local machine.
- <em> add </em> - track your files and changes in Git
- <em> commit </em> - Save your files in Git
- <em> push </em> - Upload Git commits to a remote repo, like Github
- <em> pull </em> - Download changes from remote repo to your local machine, the opposite of push

## other terms
- <em>Unstaged changes</em> are changes that are not tracked by the Git. For example, if you copy a file or modify the file. Git maintains a staging area(also known as index) to track changes that go in your next commit. ... The next git commit will transfer all items from staging into your repository.

# Create Account

[github.com](https://github.com/)

> create <em>New repository</em><br>
> input <em>Repository name</em><br> > <em>Create repository</em>

...or create a new repository on the command line

```
echo "# bfhdfhdf" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/lance28-beep/bfhdfhdf.git
git push -u origin main
```

...or push an existing repository from the command line

```
git remote add origin https://github.com/lance28-beep/bfhdfhdf.git
git branch -M main
git push -u origin main
```

## Notes

<hr>
<em>ls -la</em> -means ( list everything in the directory,including hidden files and folders )
<hr>

```
git status
```

shows me all the of the files that were updated or created or deleted,but haven't been saved in a commit yet.

<hr>

```
git add .
```

track your files and changes in Git. <br>
. (dot) - all files

<hr>

```
git commit -m "added index.html"
```

(-m) dash m is for message <br>
you need to have a message in order to commit your files. <br>
this will only save the code locally or commit isn't live on Github yet.

<hr>

```
git push
```

we want to push our code live to a remote repository where our project is hosted

<hr>

## SSH Keys

in order to push them to Github under your account,you're going to have to prove to github that you are the owner or your account.<br>
so you have to connect your local machine to your github account somehow.
<br>
The way this is done is by using SSH keys.

```
ssh-keygen -t rsa -b 4096 -C "email.example.com"
```

```
PS C:\Users\user\Desktop\Git and Github\git-github_study> ssh-keygen -t rsa -b 4096  -C "myEmail@gmail.com"
Generating public/private rsa key pair.
Enter file in which to save the key (/c/Users/user/.ssh/id_rsa): testkey
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in testkey
Your public key has been saved in testkey.pub
The key fingerprint is:
SHA256:tG1HLoTHufmvbZOP7qSfTjBX3kd30+2mf5K1Csw7HIU myEmail@gmail.com@gmail.com
The key's randomart image is:
+---[RSA 4096]----+
|                 |
|         o .    o|
|        o = o  .B|
|       . = E . ==|
|        S * * . *|
|         .o= + oo|
|          .+o ++.|
|           oo**=.|
|           .+O@++|
+----[SHA256]-----+
PS C:\Users\user\Desktop\Git and Github\git-github_study>
```

search for the key that was generated

```
PS C:\Users\user\Desktop\Git and Github\git-github_study> ls | grep testkey
-a----         7/19/2021   6:47 PM           3389 testkey
-a----         7/19/2021   6:47 PM            747 testkey.pub
PS C:\Users\user\Desktop\Git and Github\git-github_study>
```

There are two test key that was generated<br>

- testkey - private key,and it is the one that you have to keep secure on your local machine
- testkey.pub - the key that you're going to upload to your github interface.<br>
- pub people to see this key.

How it works is that the public key you put on Github,and everytime you want to connect to GitHub or push your code on GitHub or use your account via you local machine, you use your private key to show Github,that you are the one that generated this public key.Its a mathematical proof that only this private key could have generated this public key.

### print out public key

```
cat testkey.pub
```

<hr>

```
git push origin master
```

<em>origin</em> - is an option set for here.

- basically a word that stands for the location of our Git repository <br>

<em>master</em> - is the branch that we want to push to.

<hr>

## Starting Repo locally

- create a folder locally
  > git init
- - initialize Git repository
- - (git process e.i git add ./git commit/git status)
- to push(create a new Git repository)
- - Repository name
- - description
- - create repository
- copy ssh from newly created repository <br>

sample:

> git remote add origin git@github.com:lance28-beep/git-github_study.git

- <em>remote<em> means somewhere else,but not on this computer
- we are going to use this to add a reference to the remote repository on Github
  > git remote -v
- it shows any remote repositories that we connected to this repo.
- now that this are set up.we can now use git push origin.

## GitHub Workflow

<hr>

- Write code
- Commit Changes

> notice that there wasn't an step here <br>(no git add to stage changes) - because gitHub handles that for us<br>
> by committing in github, we are adding and commiting at the same time.

- make a pull request

## Local Git WorkFlow <hr>

- write code
- stage changes <code>git add</code>
- commit changes <code>git commit</code>
- push changes <code>git push</code>

  > this will update github source code or the code in the github repository with the changes that we made locally.

  <hr>

  ## Local Changes

> git status <br>

displays the state of the working directory and the staging area. It lets you see which changes have been staged, which haven't, and which files aren't being tracked by Git. Status output does not show you any information regarding the committed project history.

> git diff

git diff is a multi-use Git command that when executed runs a diff function on Git data sources.
<br>changes to tracked files

> git add .

Add all current changes to the next commit

> git add -p \<file>

Add some changes in file to the next commit

> git commit -a

Commit all local changes in tracked files

> git commit

Commit previously stagged changes

> git commit --amend

change the last commit
(note-dont amend published commits)

# Git Branching

<strong>Git branches</strong> - are effectively a pointer to a snapshot of your changes. ... The implementation behind Git branches is much more lightweight than other version control system models. Instead of copying files from directory to directory, Git stores a branch as a reference to a commit. <br>
<img src="https://wac-cdn.atlassian.com/dam/jcr:389059a7-214c-46a3-bc52-7781b4730301/hero.svg?cdnVersion=1718" alt="Italian Trulli" width='500'>

<hr>
Git Branching <br>
<strong>Master Branch</strong>
-naming convention for the main or the default branch in a repository
<br>its called branching becuasse it starts to look more like a tree when you have mulitple branches.

- Commit # 1
- Commit # 2
- Commit # 3

<strong>Feature branch</strong>
A feature branch is a copy of the main codebase where an individual or team of software developers can work on a new feature until it is complete. With many engineers working in the same code-base, it's important to have a strategy for how individuals work together.

<img src='https://image.slidesharecdn.com/gitbranchmanagement-140301040840-phpapp02/95/git-branch-management-6-638.jpg?cb=1393647122' withd='500'>

<strong>Hotfix Branches</strong>
Maintenance or “hotfix” branches are used to quickly patch production releases. Hotfix branches are a lot like release branches and feature branches except they're based on main instead of develop . This is the only branch that should fork directly off of main

> git branch - list all existing branches <br>
> git checkout \<branch\> <br>
> git checkout -b feature-readme-instructions
> git switch -b feature-readme-instructions

```
user@Lance MINGW64 ~/Desktop/Git and Github/git-github_study (master)
$ git switch feature-readme-instructions
Switched to branch 'feature-readme-instructions'
M       README.md

user@Lance MINGW64 ~/Desktop/Git and Github/git-github_study (feature-readme-instructions)
$ git add .

user@Lance MINGW64 ~/Desktop/Git and Github/git-github_study (feature-readme-instructions)
$ git status
On branch feature-readme-instructions
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   README.md


user@Lance MINGW64 ~/Desktop/Git and Github/git-github_study (feature-readme-instructions)
$
```

## Branches & Tags

> git branch -av <br>

List all existing branches

> git checkout \<name_of_branch>

Switch Head branch

> git branch \<new_branch> or git checkout -b \<new_branch>

Create a new branch based on your current Head

> git checkout --track <remote/branch>

Create a new tracking branch based on a remote branch

> git branch -d \<name_of_branch>

Delete a local branch

> git tag \<tag-name>

Mark the current commit with a tag

## What is a <strong>pull request</strong> or PR <hr>

basically a request to have your code pulled into another branch.
A pull request is a method of submitting contributions to an open development project. ... A pull request occurs when a developer asks for changes committed to an external repository to be considered for inclusion in a project's main repository.

<hr>

### notes

generally the workflow has been <code>git add</code> and then file name or period dot everything in this directory.this time,there's a shortcut,<underline>because we've just modified one file.and the file has already been committed to git in the past,which is why it says modified and not created.

> git commit -am <br>

<code>-am</code> - dash a stands for add and m at the same time for message

> git merge master

remember how i sadi before that merging locally wasnt the regular pattern.while it isn't for merging branches into master.but master gets updated as you go along as you're working on your project,because maybe other people are merging into master and you don't have those changes in your branch.But you dont want to get too far behind the master as you're working because then its going to be really difficult to merge later.so as changes are made to master in the GitHub repo,you're going to want to pull those down to your local master branch.

<hr>

## Undoing in Git

Undo Commit (After git commit, Before git push)
If you have committed changes to a file (i.e. you have run both git add and git commit ), and want to undo those changes, then you can use <strong>git reset HEAD~</strong> to undo your commit.

<i>So what if we make a mistake?what if we accidentally add something or commit something to git,and we didn't mean to do it,we can actully undo our stages or our commits</i>

>git reset

we can either do git reset with no arguments,or I can say git reset and just the name of the file that we want to onstage.

```
$ git reset
Unstaged changes after reset:
M       README.md
M       index.html
```

>git reset HEAD~1

what head means to GIT is a pointer to the last commit.<br>
so I'm telling it to do something with the last commit<br>
<code>~1</code> which is telling git instead of pointing to this last commit that I just made,right here,I want you to go back one commit further,and head will now point back one commit further meaning it will completely undo the commit that we just made
-unstaged and uncommitted those last changes

<hr>

## Forking in git
A fork is a copy of a repository. Forking a repository allows you to freely experiment with changes without affecting the original project.

<img src="https://upload.wikimedia.org/wikipedia/commons/3/38/GitHub_Fork_Button.png" width="500">

its going to make a complete copy of the repository.<br>
<strong>Why would you want to Fork?</strong>
we probably don't want to fork our own repo because we already have full access to all of the code.<br>
but for other people's repos.