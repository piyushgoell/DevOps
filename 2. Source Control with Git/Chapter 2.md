# **Cloning Repository**
## Cloning Local Repositories.
Clones a local repository to a new repository on the local file system.

    git clone <local repo> <new repo>

## Cloning Remote Repository
Clones a remote git repository to the local file system.

    git clone <remote URL>

# **Forking**
There are two main reason for forking the project.

1.  To update another project. --> A developer forked the project. which is basically cloning the original project but housing the clone on a serer so that developer outside the original project can collaborate on fixing the bugs. Once the bug is fixed then they would request the maintainer of the original project to incorporate their work.
2.  To start a new project based on another project. --> If someone wanted to start their on project but they wanted to base it on the work that someone else had started.

# **Securing your GitHub Account**
Steps:
1. On your system open terminal and type
   
        ssh-keygen
        -> Generating public/private rsa key pair.
        -> ...
        cat .ssh/id_rsa.pub
        -> ssh-rsa ealogifaloigjeoljgawjawjlowlokwlkwglkggl

2. Now, copy ssh-rsa generated token and go to your github account and go to settings and "SSH and GPG keys" and click on "New SSH key" and save it

# **Push, Pull and Tracking Remote repository**

1. git remote
   
   shows the remote servers that are being tracked for the current repository, and their latest statistics.
        git remote
        --> origin
        
        git remote -v
        --> origin git@github.com:piyushgoell/Recipe-App.git (fetch)
        --> origin git@github.com:piyushgoell/Recipe-App.git (push)

        git remote show origin
        --> detailed message

2.  git fetch 

    fetches new commit information down from the remote server for the current repository, doesn't commit anything to local database.
    
        git fetch origin

3.  git push

    pushes local changes to the upstream git repository.

        git push -u <remote><local branch>
        git push -u origin <branch>

4.  git pull 
   
    done from github UI to incorporate the changes pushed in git push command.

# **GitLab**

   
    