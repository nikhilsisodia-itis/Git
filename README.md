# GitHub Docs:

## Git Setup:
Download git from:
[GitHub](https://git-scm.com/downloads)

Follow the on-screen Git install process.

## GitHub Account:
Click here [GitHub](https://github.com/) and sign up for an account.

## Git Configuration:
Configuration let Git know who you are. It also helps to specify changes made by you in a Project(s).

    git config --global user.name "GitHub_UserName"
    git config --global user.email "GitHub_Email"

(Replace GitHub_UserName and GitHub_Email with your GitHub Username and Email.)

'global' flag is used to set the username and e-mail for every repository of your Computer.
Remove global if you want to set the username and e-mail for your current repository.

## Initialize a repo in your local project: 
    git init

## Connect your local repo with the remote repo:
    git remote add origin <your_github_repo_url>

'remote' is a subcommand used to manage a remote repository connections.
'add' is a subcommand to add a new remote repository.
'origin' is the name you are giving to the remote repository. Origin is a common convention for the main remote repository.

## Verify the new remote URL:
    git remote -v

## Add changes to the staging environment:
    git add <file_name>

OR

    git add .

The 'git add' commands is used to add changes to the staging environment. 
Staging environment is a place that tells the user about changes made and to review them before commiting them. 

The 'git add <file_name>' command is used to add a specific file to the staging area.
The 'git add .' command is used to add all the changes to the staging environment.

## Commit Changes:
    git commit -m '<commit_message>'

Git Committing is the technique of saving changes from the staging ares to the repo. 
This command creates a SnapShot of user's project current state.
Includes only those directories & files that are been staged. 

## Pull changes from a remote repository:
    git pull <remote> <branch> 

This command is used to fetch and integrate changes from a remote repository into your current branch. 
It is a combination of git fetch and git merge.

## Push changes to the remote repository:
    git push <remote> <branch>

This command is used to upload your local repository content to a remote repository.
It transfers commits from your local branch to a remote branch.

## Check the logs:
    git log

The 'git log' command is used to display the commit history of the current branch.


## Check the status:
    git status

The 'git status' command displays the state of the working directory and the staging area.

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
Go to settings.
Go to GitHub SSH and GPG keys settings. 
Click "New SSH key". 
Paste the key from your clipboard into the "Key" field and give it a title.

Step 5: Test your SSH connection:

        ssh -T git@github.com

Output: Hi <your_username_will_be_displayed>! You've successfully authenticated, but GitHub does not provide shell access.

Now, you can clone and use any repo using the SSH link.
*Note:* You need to use bash terminal for the above commands, for the SSH set up.