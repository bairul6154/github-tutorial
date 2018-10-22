# GitHub Tutorial

_by Bairu Li_

---
## Git vs. GitHub

_What is Git and Github?_  
##### Git:
* Git is a _version-control_ system that runs on the command line  

  (so you need to know basic command line codes as well). I recommend going to [codeacademy](https://www.codecademy.com/) 
  to learn about basic command line before learning git and github.
  
* Version-control means you can keep track of your code or just about any file. 

  The basic workflow of git is creating a file inside a directory and initialize it using `git init`. 
  This turns that _directory_ into a **_repository_**, or repo for short. Then you can add files from your working directory to the 
  _staging area_ using `git add`. The _staging area_ is the step before a commit and it allows you to edit however you want.  

##### Github:
* Github is the "cloud" or online in a website

  It can _store_ all your files and can let other people to see it or maybe even _collaborate_ on it
  
* In github, you can also see all the changes (commits) you've made to a repository. 

  The basic workflow of github is either starting from someone
  else's repository or your own repository. 
  
* It is called github for a reason, so it does require git.  

If you don't understand some of these, don't worry you will after reading through this tutorial.

---
## Initial Setup
If you haven't already, you need to create a github account before you do anything. (If you are a HSTAT student then you can HSTAT email as you username)  
**Creating SSH key**  
SSH vs. HTTPS  
They both are the url of the remote repo (github). However HTTPS you have to enter your github username and password everytime you do 
a push. On the other hand SSH is a one time password for one repo. SSH is the most convient for us (students opf HSTAT)









---
## Repository Setup

When you are first in bash, you should see this:
[image][bash]  
The first thing you can do is to create a directory if you haven't. After creating, you must navigate (cd) into the directory before you do
anything. Once you cd into it, you can do `git init`, which will get all the tools ready for you to use git. If you don't do `git init` you
can't use any of the git commands. You should see (master) pop up.

The next step is to create that repo in github. Go to your github account and click on this:  
[image][addrepo]


[addrepo]: image
[bash]:image

---
## Workflow & Commands



---
## Rolling Back Changes