# Development Git Tutorial: A Comprehensive Guide
![gitImage](https://d1m75rqqgidzqn.cloudfront.net/wp-data/2020/08/11133333/image-25.png)


## So, what is Git?
1. ** Snapshots **

Git is a DVCS that stores data in a file system made up of snapshots. 

2. ** Local Operations **

Git mostly relies on local operations because most necessary information can be found in local resources. 

3. ** Tracking Changes **

Every single change applied to any file or directory is tracked by Git. And, as the gatekeeper, Git will always detect file corruption or loss of information in transit.

4. ** Loss of Data **

Git is set up to greatly minimize the possibility of irreversible damage to files, such as accidentally lost data. Git makes it extremely difficult for a snapshot of your file that is committed to be lost.

5. ** States **

Files in Git can reside in three main states: committed, modified and staged.

 >_ Committed _ 

Data is securely stored in a local database

> _ Modified _

File has been changed but not committed to the database

>_ Staged _

Flagged a file’s changed version to be committed in the next snapshot

![gitImage](https://blog.udemy.com/wp-content/uploads/2015/08/image066.png)


## History of Git
* git tarce root connect to the open sorurce software project linux kernel
* 2002 they strated they used DVCS called bitkeeper
* 2005 the developers stopped using this DVCS due to tension between the Linux kernel community and the company behind BitKeeper’s 
* The chief architect of the Linux kernel Linus Torvalds, began creating Git. With the intention of creating a DVCS with a workflow design similar to that of BitKeeper, which was also fast, Git allowed for non-linear development via multiple branches, could support large projects, possessed strong mechanisms preventing corruption.

## Getting Started
### Download Git
**  Git can be installed in three ways:**
1. Install as a package
2. Install via another installer
3. Download and compile the source code.
 
  ** Mac OS X **

* Terminal

The simplest method for installing Git on a Mac (for Mavericks 10.9 and above) is running Git from the Terminal. If Git is not installed, you will see a prompt for installation.

* Git Website

You can also download Git by visiting this [link](http://git-scm.com/download/mac)

* GitHub

A third option is to install Git as part of the GitHub for Mac install. GitHub is repository hosting service, which we will discuss in a future section.

Download GitHub for Mac via this [link](http://mac.github.com)


### Windows
** _ Git Website_**

You can download Git by visiting this [link](http://git-scm.com/download/win)

** _ GitHub _**

Install Git as part of the GitHub for Windows [install](http://windows.github.com)

### Linux

** _ Package Manager _**

You can try installing Git via your distribution’s inherent package management tool.

For Fedora:
```
$ sudo yum install git
 ```

For Ubuntu:
 ```
$ sudo apt-get install git
 ```
 
### Git Website

To download Git for Linux, visit this [link](http://git-scm.com/download/linux)

** Graphical Clients **

Git includes inherent Graphical User Interface (GUI) tools. However, users can also utilize third-party tools created for particular platforms.

** GUI Clients **

You can access a variety of GUI clients for Mac, Windows, and Linux via this [link](https://git-scm.com/downloads/guis)

### Initial Customization
_ To change settings, you can repeat these steps._

* Configuration of Variables

An inherent Git tool called git config allows the setting of configuration variables that control aspects of Git’s operation and look.

* Identity Setting

After installing Git, users should immediately set the user name and email address, which will be used for every Git commit.

> Type the following into Terminal or Command Line:
```
git config --global user.name "Jane Smith"

git config --global user.email "example@email.com"
```

To confirm that you have the correct settings:
```git config --global user.name (should return Jane Smith)
git config --global user.email (should return example@email.com)
```
# Workflow

Local Repository Structure
The local Git repository has three components:

1. Working Directory: The actual files reside here.
2. Index: The area used for staging
3. Head: Points to the most recent commit
![Head](https://blog.udemy.com/wp-content/uploads/2015/08/image036.png)
## Saving Changes
* Tracked
* Untracked


## The Life Cycle of File Status
1. After you edit a file, Git flags it as modified because of changes made after the previous commit.
2. You stage the modified file.
3. Then, you commit staged changes.
![cycle](https://blog.udemy.com/wp-content/uploads/2015/08/image006.png)

## Tracking and Staging a New File
_ Single File _

Track one file only by using the following format:
```
git add filename
```

All Files

Track all files in a repository by using the following command:
```
$ git add *
```
After adding a new file called EXAMPLE, you would see information regarding changes to be committed when using the git status command:
```
$ git status
```

> Committing a File
```
$ git commit -m “made change x,y,z”
```
>Committing All Changes
```
$ git commit -a
*This command commits a snapshot of all modifications to tracked files in the working directory.
```

>Pushing Changes
```
$ git push origin master 
```

## Stashing Changes
* When you are not ready to commit changes but do not want to lose them either
```
 git stash 
 ``` 
 * When you are ready to continue working on the changes, simply use the  
 ``` 
 git stash apply 
 ``` 
## Remote Repositories
In order to collaborate on Git projects, you must interact with remote repositories, versions of a project residing online or on a network. 

** _ Cloned Repositories _**

 Git will automatically give the name “origin” to the server from which you cloned and the name “master” to your local branch.

** _ Seeing Your Remotes  _**
By running the git remote command, you can view the short names, such as “origin,” of all specified remote handles.
```
$ cd example

$ git remote -v

remote1 https://github.com/remote1/example (fetch)

remote1 https://github.com/remote1/example (push)

remote2 https://github.com/remote2/example (fetch)

remote2 https://github.com/remote2/example (push)

remote3 https://github.com/remote3/example (fetch)

remote3 https://github.com/remote3/example (push)
```
** _  Adding Remotes  _**
To create a new remote Git repository with a short name, use the following format:

git remote add shortname url
Example:
```
$ git remote
origin

$ git remote add js https://github.com/janesmith/project1

$ git remote -v

origin https://github.com/johndoe/project1 (fetch)

origin https://github.com/johndoe/project1 (push)

js     https://github.com/janesmith/project1 (fetch)

js     https://github.com/janesmith/project1 (push)
```

** _ Fetching _**

Used this command format:
```
git fetch [remote-name]
```
** _ Pushing _**

```
git push [remote-name][branch-name]
```
### Renaming/Removing Remotes
** _ Rename _**
> Example:

```
$ git remote rename js jane

$ git remote

origin
```


** _ Remove _**

Example:
```
$ git remote rm jane

$ git remote

origin
```

#### Undoing Actions
Git has mechanisms for undoing certain actions.

** _  Commit Mistakes _**

Example:
```
$ git commit --amend
```
Also you can use this command to easily change your commit message, if no changes were made since the newest commit.
Example:
```
$ git commit -m “my first commit”

$ git add example_file

$ git commit --amend
```

** _ Unstaging a File _**
Example:
```
$ git reset HEAD index.html 

Unstaged changes after reset:

M index.html
```