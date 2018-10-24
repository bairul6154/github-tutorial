# GitHub Tutorial

_by Bairu Li_

---
## Git vs. GitHub

_What is Git and Github?_  
##### Git:
* Git is a _version-control_ system that runs on the command line  

  (so you need to know basic command line codes as well. I recommend going to [codeacademy](https://www.codecademy.com/) 
  to learn about basic command line before learning git and github.)
  
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
* They both are the _url_ to your **remote** repo or also known as github. 
* However for HTTPS you have to enter your github username and password everytime you do a _push_. 
* On the other hand SSH is a one time password for one repo. So you don't have to type in you information every single time. SSH is the most convient for us (students of HSTAT) because we will only be using cloud9 on our computers. So we will be the only one that
will use this IDE so your directories will be safe. 

So if you are working on the same computer with a group, then the HTTPS would be
more helpful because other people might mess with your directories. <!--I don't think it matters when different people work on the computer. Try asking Mr. Mueller about this.-->

[image][SSHandHTTPS]

[SSHandHTTPS]:/github-tutorial/Capture.PNG

---
## Repository Setup

When you are first on the command line or bash

1. The first thing you can do is to **create a directory** using `mkdir` followed by your file name. 
2. After creating, you must **navigate** into the directory using `cd` followed by your file name. 
3. Once you cd into it, you can do `git init`.  
 _This will get all the tools ready for you to use git. If you don't do `git init` then you
 can't use any of the cool git commands. You should see (master) pop up._

4. Then you can **add** whatever file you've just made into the _staging area_ using `git add` followed by your file name.  
_Other options you can do that will save you time is to do either `git add .` or `git add --all`. `git add .` will add all files to the stage **except for deleted files**. Whereas `git add --all` will add all files including deleted files. This way you don't have to type out the file name every time_


5. Next you can **edit** your file by opening it either manuelly on the left side in your workspace where all your directories are, or use `c9` followed the file name to open its working directory. There you can edit however you want.

6. When you are happy with your edits or you've been editing for a while, you can **commit** your changes to **save** them so you don't lose them when you exit out. You can do this by using `git commit -m "a message"`.  
_For the "a message" part, type in a relevant message that explains what that commit is. For example, I am writing a paragraph but didn't get to finish. If I want to save my changes so that I can come back to it later, I can write my message as "need to finish analysis". Why do we write these messages? This will tell your future self what that commit is so that you don't forget if you decide to come back to that file later._

Now that we've finished our local stuff, it is time to create a remote. Think of this as if you are trying to cross a river. There are two locations, where you are at now (your local; c9; IDE) and the other side (remote; github; cloud). You can't cross to the other side,...if the other side is never there to begin with. 

7. First create a repo in github. This will set up the destination. Go to your [github](www.github.com) account and click on this on the top right:  
[image][addrepo]

[addrepo]: image
[bash]:image

---
## Workflow & Commands

Use `git status` to make sure you've done what you did. This helps you keep track of what you are
doing. If it shows red then your file have not been added to the stage and it will also suggest what 
you can do.

[image][status]

Use `git add` to add your files to the stage

[image][add]

use `git commit -m` to save your changes that you've made after editing that file. You have to put a message in 
quotations "" to have the right syntax. This message is important because it will tell your future
self what that commit is. It will make your commit more clear if you write it in present tense.

use `git push` or `git push -u origin master` to push your commits up to the cloud or github. But 
you have to do the -u origin master first. The -u means upstream. this means it will remember where you've push
to. In this case it will remember that you've pushed to the master branch in github. So next time
when you want to do git push, you don't have to type out the name of the branch that you want to push if you are constantly
pushing to the same branch. You can just do `git push`.

[add]:image
[status]:image

---
## Rolling Back Changes

use `git checkout` to undo changes you've made when editing a file.

use `git reset HEAD` to unstage the file.

use `git reset --soft HEAD~1` to undo a commit.

use `git revert SHA` to undo push.

<!--Great Job :) You were very thorough and direct with your explainations which is good for better understanding. Make sure to explain more of why with the how and the what.-->

