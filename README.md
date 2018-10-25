# GitHub Tutorial

_by Bairu Li_

---
## Git vs. GitHub

_What is Git and Github?_  
**Git:**
* Git is a _version-control_ system that runs on the command line  

  (so you need to know basic command line codes as well. I recommend going to [codeacademy](https://www.codecademy.com/) 
  to learn about basic command line before learning git and github.)
  
* Version-control means you can keep track of your code or just about any file. 

  The basic workflow of git is creating a file inside a directory and initialize it using `git init`. 
  This turns that _directory_ into a **_repository_**, or repo for short. Then you can add files from your working directory to the 
  _staging area_ using `git add`. The _staging area_ is the step before a commit and it allows you to edit however you want.  
  
**Github:**
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

### Creating SSH key  
_SSH vs. HTTPS_  
* They both are the _url_ to your **remote** repo or also known as github. 
* However for HTTPS you have to enter your github username and password everytime you do a _push_. 
* On the other hand SSH is a one time password for one repo. So you don't have to type in you information every single time. 
  * SSH is the most convient for us (students of HSTAT) because we will only be using cloud9 on our computers. So we will be the only one that
  will use this IDE so your directories will be safe. 

If you are working on the same computer with a group, then the HTTPS would be
more helpful because other people might mess with your directories if you use SSH. 

![image](/github-tutorial/Capture2.PNG)

**Steps on creating SSH key:**

1. Go to [github](https://www.github.com) and click on your **profile icon** on the **top right** and click on **settings**
2. On the left side bar, click on **SSH and GPG keys**
3. Click on the green **New SSH key button**
4. Title your SSH key, if you are using cloud9 then type in cloud9

The following steps are exclusive to cloud9. 

5. Go to [cloud9](https://www.c9.io) account and click on the gear icon on the **top right**

![image](/github-tutorial/Capture4.PNG)

6. Click on the **SSH keys** on the left bar
7. Copy and paste the **_second_** key into **github** and **Add SSH key**

![image](/github-tutorial/Capture5.PNG)

8. Finally open up your workspace and type in the following to your command line:
`ssh -T git@github.com`


---
## Repository Setup

When you are first on your IDE or on your workspace

1. The first thing you can do is to **create a directory** using `mkdir` followed by your file name. 
2. After creating, you must **navigate** into the directory using `cd` followed by your file name. 
3. Once you cd into it, you can do `git init`.  
 _This will get all the tools ready for you to use git. If you don't do `git init` then you
 can't use any of the cool git commands. You should see (master) pop up._

4.  Then you can **edit** your file by opening it either manuelly on the left side in your workspace where all your directories are, or use `c9` followed the file name to open its working directory. There you can edit however you want.

5. When you are happy with your edits or you've been editing for a while, you can **add** that file  into the _staging area_ using `git add` followed by the file name.  
_Other options you can do that will save you time is to do either `git add .` or `git add --all`. `git add .` will add all files to the stage **except for deleted files**. Whereas `git add --all` will add all files including deleted files. This way you don't have to type out the file name every time_

6. Next, you can **commit** your changes to **save** them so you don't lose them when you exit out. You can do this by using `git commit -m "a message"`.  
_For the "a message" part, type in a relevant message that explains what that commit is. For example, I am writing a paragraph but didn't get to finish. If I want to save my changes so that I can come back to it later, I can write my message as "need to finish analysis". Why do we write these messages? This will tell your future self what that commit is so that you don't forget if you decide to come back to that file later._

Now that we've finished our local stuff, it is time to create a remote. Think of this as if you are trying to cross a river. There are two locations, where you are at now (your local; c9; IDE) and the other side (remote; github; cloud). You can't cross to the other side,...if the other side is never there to begin with. 

1. First create a _repo_ in github. This will set up the destination. Go to your [github](www.github.com) account and click on "New repository" on the top right:  

![image](/github-tutorial/Capture.PNG)

2. Enter the name of your repository. This should be the same name as the one in your _local_.

Now that you have a destination, you have to be able to get to it somehow. Going back to the river scenerio, you can't go to the other side if there is no bridge. So to create this bridge that will connect the two, you do the following:

3. **Make sure you click on the SSH**

![image](/github-tutorial/Capture3.PNG)

4. Copy and paste these two commands into your IDE one at a time respectively.

![image](/github-tutorial/Capture6.PNG)

And that is it, you've linked up your IDE to github.

---
## Workflow & Commands

* Use `git status` to make sure you've done what you did. This helps you keep track of what you are doing. 
  * If it shows red then your file have not been added to the stage and it will also suggest what you can do.
  * if it shows green, then that file is on the stage and it is ready for commit.

* Use `git add` to add your files to the stage. I have explained this before, refer back to repository setup.

* Use `git commit -m` to save your changes that you've made after editing that file. 
  * You have to put a message in quotations "" to have the right syntax. I have also explained this before.

* Use `git push -u origin master` to push your commits up to github
  * what do all this mean?
    * **git** = a git command, duh
    * **push** = sending (pushing) your commit from your local repo to the remote (github) repo
    * **-u** = upstream. This is telling git to remember where to push to (which repo and which _branch_.
    *  **origin** = telling which remote repo to push to. This is the nickname of the repo
  * Because you typed in **-u** you don't have to type in this long command every single time. The **-u** remembers where to push to. **So you can just type in** `git push` **the next time you want to push, which is a lot shorter.**
* Use `clear` to _clean_ your IDE, this makes it look nicer. This will make more room for you to code.  
  

---
## Rolling Back Changes

Rolling back changes means if you can undo what you've done. If you unintentionally _added_ a file, there is a way to undo that. There is a way to _undo_ any add, commit, and push that you've made.

* Use `git checkout` followed by file name to **undo changes** you've made when editing a file in the working directory. 
  * Using this will undo **all** the changes you've made to the file since the **last add**. 
  * If you did a `git add` before you realized you don't like the edits, you can't use this command to undo those edits.

* Use `git reset HEAD` followed by file name to **unstage** the file. 
  * If you accidentally staged a file, you can unstage it using this command
  * Lets go back to `git checkout`. This command will not undo edits after you did a `git add`. However if you unstaged (un-add) it using `git reset HEAD`, then `git checkout` will in fact work again and it can undo your edits. 

* Use `git reset --soft HEAD~1` to **undo a commit**. 
  * If you committed accidentally or feel that you want to make just a small change, then you can use this command to undo that commit. This will leave everything untouched. It would only remove the commit.
* Use `git reset HEAD~1` to **undo a commit _and unstage_ the file**.
  * There is no `--soft` in this command, so it won't just leave everything as it is. `--soft` is the lightest touch of undoing a commit. 
  * Your previous edits will still be there
* Use `git reset --hard HEAD~1` to **undo a commit, unstage the file, _and undo all the changes you've made_**.
  * This is the hardest commit reset you can do, hence the name `--hard`
  * Not only this will undo your commit and unstage the file, it will also undo all the changes you made just like `git checkout`.

Some visuals:

![image](/github-tutorial/Capture7.PNG)

* Use `git revert SHA` to undo push.
  * This is very risky because it might cause some conflicts when you are collaborating with someone else.
  * To get the `SHA`, you can do `git log`. `git log` will show you all the commits that you've made and _their number_. This number is beside the commit. Remember to always press 'Q' to quit log.
  * Example: `git revert a867b4afb5eee4cac766c053`

  


<!--Great Job :) You were very thorough and direct with your explainations which is good for better understanding. Make sure to explain more of why with the how and the what.-->

