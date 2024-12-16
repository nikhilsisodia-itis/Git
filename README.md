# GitHub Docs:

## Git Setup:
 Download git from:
> [Git.com](https://git-scm.com/downloads)

Follow the on-screen Git install process.

## Create GitHub Account:
>Go to [GitHub.com](https://github.com/) and sign up for an account.

## Git Configuration:
Configuration let Git know who you are. 
<br>
It also helps to specify changes made by you in a Project(s).

    git config --global user.name "GitHub_UserName"
    git config --global user.email "GitHub_Email"

(Replace GitHub_UserName and GitHub_Email with your GitHub Username and Email.)

'global' flag is used to set the username and e-mail for every repository of your Computer.
<br>
Remove global if you want to set the username and e-mail for your current repository.

## Initialize a repo in your local project: 
    git init

The 'git init' command is used to initialize a new Git repository.
<br>
The command creates a new GitHub repo in the current directory on your local machine.

## Connect your local repo with the remote repo:
    git remote add origin <your_github_repo_url>

'remote' is a subcommand used to manage a remote repository connections.
<br>
'add' is a subcommand to add a new remote repository.
<br>
'origin' is the name you are giving to the remote repository. 
<br>
Origin is a common convention for the main remote repository.

## Verify the new remote URL:
    git remote -v

Output: 
<br>
origin <span style='color: royalblue;'> link to your remote repo </span> (fetch)
<br>
origin <span style='color: royalblue;'>link to your remote repo </span> (push)

## Check the status:
    git status

The 'git status' command displays the state of the working directory and the staging area.

## Add changes to the staging environment:
    git add <file_name>

OR

    git add .

The 'git add' commands is used to add changes to the staging environment. 
<br>
Staging environment is a place that tells the user about changes made and to review them before commiting them. 

The 'git add <file_name>' command is used to add a specific file to the staging area.
<br>
The 'git add .' command is used to add all the changes to the staging environment.

## Commit Changes:
    git commit -m '<commit_message>'

Git Committing is the technique of saving changes from the staging ares to the repo. 
<br>
This command creates a SnapShot of user's project current state.
<br>
Includes only those directories & files that are been staged.

## Set the upstream branch:
    git push -u origin <branch>

The 'git push -u' command is used to push changes to the remote repository.
<br>
The '-u' flag is used to set the upstream branch.
<br>
*Note:* You need to set the upstream only once per branch, this publishes the branch on the remote repo.

## Push changes to the remote repository:
    git push <remote> <branch>

This command is used to upload your local repository content to a remote repository.
<br>
It transfers commits from your local branch to a remote branch.

## Pull changes from a remote repository:
    git pull <remote> <branch> 

This command is used to fetch and integrate changes from a remote repository into your current branch. 
<br>
It is a combination of git fetch and git merge.

## Check the logs:
    git log

The 'git log' command is used to display the commit history of the current branch.

## Create a new branch:
    git branch <branch_name>

Branches allows you to keep different versions OR features of your project. 
<br>
Branches can be used to develop features, fix bugs, etc.
<br>
The 'git branch' command is used to create a new branch in the repository.

## List all branches:
    git branch

The 'git branch' command is used to list all the branches in the repository.

## Delete a branch:
    git branch -d <branch_name>

The 'git branch -d' command is used to delete a branch in the repository.

## Set or change the branch name:
    git branch -M <branch_name>

The 'git branch -M' command is used to rename the current branch.
<br>
<branch_name> can be any name you want to set as the branch name.
<br>
*Note:* 'main' is the default branch name that is mostly used over the Internet.

## Switch to a specific branch OR commit:
    git checkout <branch_name> OR <commit_id>

The 'git checkout' command is used to switch between branches or commits in a repository.
<br>
It is used to update the working directory to a specific commit.
<br>
*Note*: You can get the commit_id from the 'git log' command.

## Forcefully switch to a specific branch OR commit:
    git checkout -f <branch_name> OR <commit_id>

The 'git checkout -f' command is used to forcefully switch between branches or commits in a repository.

## Merge a branch:
    git merge <branch_name>

The 'git merge' command is used to merge changes from one branch to another.
<br>
It is used to integrate changes from another branch into your current branch.

## Reset changes:
### 1. Soft reset:
Undo changes in your repository without losing the changes in your working directory. 
<br>
It moves the HEAD pointer to a specified commit, but it does not modify the working directory or the staging area.

        git reset --soft <commit_id>
### 2. Mixed reset:
Undo changes in your repository and the changes in your staging area.
<br>
It moves the HEAD pointer to a specified commit and modifies the staging area, but it does not modify the working directory.

        git reset <commit_id>

### 3. Hard reset:
Undo changes in your repository, changes in your staging area, and  changes in your working directory.
<br>
It moves the HEAD pointer to a specified commit, modifies the staging area, and modifies the working directory.

        git reset --hard <commit_id>

## Revert changes:
Git revert is a command used to create a new commit that update the project to the specified commit.
<br>
It is used to undo changes in the repository.
<br>
Revert maintains the history of the project by adding a new commit that reverses the changes.

        git revert <commit_id>



## GitHub SSH Set-up:
Step 1: Generate a new SSH key (if you don't have one):
        
    ssh-keygen -t ed25519 -C "your_email@example.com"

Step 2: Add your SSH key to the SSH agent:
        
    eval "$(ssh-agent -s)"
    ssh-add ~/.ssh/id_ed25519

Step 3: Copy the SSH key to your clipboard:

    clip < ~/.ssh/id_ed25519.pub

Step 4: Add the SSH key to your GitHub account:

Open your GitHub account.
<br>
Go to settings.
<br>
Go to GitHub SSH and GPG keys settings. 
<br>
Click "New SSH key". 
<br>
Paste the key from your clipboard into the "Key" field and give it a title.

Step 5: Test your SSH connection:

    ssh -T git@github.com

Output: Hi <your_username_will_be_displayed>! You've successfully authenticated, but GitHub does not provide shell access.

Now, you can clone and use any repo using the SSH link.
<br>
*Note:* You need to use bash terminal for the above commands, for the SSH set up.