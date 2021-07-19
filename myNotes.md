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

- <em> Clone </em> - Bring a repository that is hosted somewhere like Github into a folder on your local machine.
- <em> add </em> - track your files and changes in Git
- <em> commit </em> - Save your files in Git
- <em> push </em> - Upload Git commits to a remote repo, like Github
- <em> pull </em> - Download changes from remote repo to your local machine, the opposite of push

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
- -pub stands for public,its called your public key,which means that it's okay for other people to see this key.

How it works is that the public key you put on Github,and everytime you want to connect to GitHub or push your code on GitHub or use your account via you local machine, you use your private key to show Github,that you are the one that generated this public key.Its a mathematical proof that only this private key could have generated this public key.

### print out public key
```
cat testkey.pub
```
git