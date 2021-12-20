# Basics Of Git

## File System
When we initialize a Git repository, a hidden directory is created within our working directory named **.git** that contains the configuration info about our repository.

- COMIT_EDITMSG : It contains the messages for each commit to the repository. Each line in the file is in order of commit.
- HEAD : It contains the reference to the current branch that we are working on.
- config : It contains the configuration information about our repository, such developer's username and email address.
- description : It contains the name of the repository. It is typically used by git web.
- hooks : It contains automated script that can run during some particular phases of the Git process.
- index : It keeps track of the iteams in our staging area and ready to be commited.
- info : It contains iteams such as an exclude file.
- logs : It contains log files for the activities that goes within the git repository, such as commits and changes to the project.
- objects : It is actually a database consisting of compressed files that are hashed version of contents of files that have been commited.
- refs : It contains reference files in folders for the branches and tags of your repository.

## Creating a Local Repository

Initializes a git repository, either by creating a new directlry or adding the git repository files to an existing directory. 
Command : git init /path/to/directory  
Initializes a bare git repository, for larger projects, contians no working area.
Command : got init --bare /path/to/new/directory 

## Basic Configuration of Git

**git config** is used to configure various elements of git environment.  
  To set the global variable:-  
  - git config --global user.name "Piyush Goel"  
  - git config --global user.email "piyushgoel.in@gmail.com"
  
  To set the variable for a specific project:-  
  - git config user.name "Piyush Goel"
  - git config user.email "piyushgoel.in@gmail.com"  

  To check the specific variable property:-  
  - git config user.name 
  - git config user.email

  To specify the default text editor to be used while working with text based file:-    
  - git config --global core.editor "/user/bin/vim" 

  To check all variable property:-   
  - git config --list

  To check global configuration information:-   
  - cat ~/.gitconfig (git store all global configuration in .gitconfig file)

## Adding files to project.

- **git add** : It is used to add files to a git project, adds them to the index files so that they can be tracked in the staging area.  
    Syntax : git add README.md

- **git status** : It is used to see  what files are in the staging area (not commited yet).  
  Git will not bother about empty directory. It will not list.  
    Syntax : git status
    But, if we want to list those as well. we can create .keep files.
    Commands :   
    touch src/.keep  
    git add src/.keep  
    Syntax : git status -s (view the output in shortend format)
    Syntax : git status -v (get more verbose output, including what was changed in a file)

- **git rm** : It removes file from stagging as well as from file system of a project.
  Syntax : git rm -f src/.keep

## Commiting to git
- **git commit** : Opens text editor to prepare for a commit of files in the staging area.
- **git commit -m "CommitMessage"** : Bypasses the editor and performs a commit with the specified message.
- **git rm --cahched filename** : To remove the committed file
- **git commit -a -m "commit message"** :  To commit a modified file directly.
- **cat .git/COMMIT_EDITING** : To view the commit message:  
- **git log** : To view git commit in database:  

## Ignoring Certain FileTypes
 touch .gitignore  
 git add .gitignore  
 git status  
 echo "build/*" >> .gitignore  
 git commit -a -m "Updated gitignore file"

## Tag, Branching, Merging & Reverting.

**Tag** : To mark a specific commit in your project. To put a sticky note on a particular point of your project history.

To set a tag  
    
    git tag -a <tagname> -m <message>
    git tag -a v0.1 -m "First tag for the project"

To view a tag

    git tag

To remove a tag

    git tag -d <version>
    git tag -d v0.1

**Branch** : 

To create a new branch of the project

    git branch <branch name>
    git branch development

To switch to another branch

    git checkout <branch name>
    git checkout development
    git checkout -b development [create and switch branch]

Let's assume we have introduced some changes on branch development

    git commit -m "new feature added"
    git checkout master
    git status

the changes made on development branch is not visible on master.

## Merging Branches

**HEAD**: It knows where our last commit was, lets look at HEAD file

    cat .git/HEAD
    -> ref : refs/heads/master
    cat .git/refs/heads/master
    -> awfwf7wf7aw9faw9fwa9faw9fwff9w9faf
    git log --oneline
    -> awfwf update something
    -> wdwfw added something

We want to merge our development work into master branch, so we have to be on master branch to merge development branch into master.

To merge the two branches
    
    git merge <branch name>
    git merge development
    -> **Fast-forward**

Now, to complicate things lets create two branches

    git branch trail1
    git branch trail2

    git checkout trail1
    echo "stuff" >> info.txt
    git add info.txt
    git commit -m "new info file added"

    git checkout trail2
    echo "things" >> info.txt
    git add info.txt
    git commit -m "new info file added"

    git checkout trail1

    git merge trail2
    -> Merge conflict in info.txt

    git status
    -> shows details of conflict
    
    vim info.txt [make changes to persist both changes]
    ---------------------
    <<<<<<<< HEAD
    stuff
    ========
    things
    >>>>>>>> trial2
    ----------------------
    # Changed to below
    ------------------
    stuff things
    -------------------

    git add info.txt
    git commit -m "Added trail2's work, resolved merge conflict"
    cat info.txt
    -> stuff things

To delete a branch

    git branch -d <branch name>
    git branch -d trail2

## Rebasing
    
    git rebase <branch name>

## Reverting a commit

    git revert <commit> [press enter and put comment]
    git revert HEAD [revert the last commit]
    git revert HEAD-2 [revert to last 2nd commit]

## diff command

view the differences between two commits, files, blobs, are between working tree and the staging area.
    
    git diff
    git diff changeset
    git diff --summary changeset

## Garbage Collection
The git grabage collection command, cleans out old objects that can not be referenced by the database anymore, and compresses contents within the .git directory to save disk space.

    git gc

By default, cleans out objects that are older than two weeks.

    git gc --prune
    git gc --auto [check if repository needs cleaning]
    git config gc.pruneexpire "30 days"


    git log
    git log --graph
    git log --since="4 days ago"
    git log -S build
    git log --stat
    git log --shortstat
    git log --pretty=format:"%h - %an - %ar - %s"