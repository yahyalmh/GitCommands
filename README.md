# Git Useful Commands
Git useful commands which I have ever used. Please add, update or delete what ever you want, and help to improve it :punch:.

## Table of content
* [Init](#Init)

* [Config](#Config)

* [Branch](#Branch)

* [Checkout](#Checkout)

* [Add and Remove](#Add-and-Remove)

* [Commit](#Commit)

* [Stash](#Stash)

* [Reset](#Reset)

* [Diff](#Diff)

* [Tag](#Tag)

* [Push and Pull](#Push-and-Pull)

* [SSH Key](#SSH-Key)

## Init
* Init git in specified folder

   `git init `

* Get a project from a url

  `git clone <url>`

* Connect local project to a remote url

  `git remote add origin <ulr>`

* Get all commits log

  `git log` 
  
## Config
 
 All below commands affect globally on all projects, If you want use them for current project do not use `--global` switch
 * Showing system, global, and (if inside a repository) local configs

    `git config --list`

* Change your user name globally
    
    `git config --global user.name <username>`

* Disable SSL certificate checking

    `git config --global http.sslVerify false `

* Get remote url
    
    `git config --get remote.origin.url `
    
 ## Branch
* Show branches (current branch marked with *)

    `git branch `

* Create new branch

    `git branch <branch_name> `

* Delete a branch locally

    `git branch -d <branch_name> `

* Delete a remote branch

    `git push origin --delete <branch_name> `

* List all remote branch
    
    `git branch -a`

* List all branch and their commits(use origin/develop to check remote branch)

    `git show-branch`

* List all changes in a commit

    `git show [below_switches] <commit_id>`

    - The `--no-commit-id` suppresses the commit ID output

    - The `--pretty` argument specifies an empty format string to avoid the cruft at the beginning.

    - The `--name-only` argument shows only the file names that were affected (Thanks Hank). Use --name-status instead, if you want to see what happened to each file (Deleted, Modified, Added)

    - The `-r` argument is to recurse into sub-trees

* See remote url and branches of project

    `git remote show origin`

* Move existing, uncommitted work to a new branch (git version > 2.23)

    `git --version`
    
    `git switch -c <new-branch>`

## Checkout
* Fetch the remote branches

   `git fetch origin`
   
* Reset a file to the latest committed file version
    
    `git checkout -- <file_name> `

* Checkout to an existing branch

    `git checkout <branch_name>`

* Create and checkout to a new branch

    `git checkout -b <branch_name>`
       
## Add and Remove
* Add current directory changes, untraced files and etc to local

    `git add . ` 

* Add two files
    
    `git add file1 file2`

* Remove a file
    
    `git rm file`
    
## Commit
* commit whatever you added
 
    `git commit -m "message"`

* Commit two file simultaneously

    ` git commit -m "message" file1 file2 `
    
* Update latest commit messages. It lets you combine staged changes with the previous commit instead of creating an entirely new commit. 
    
    `git commit --amend -m "new message"`

## Stash
Often, when you’ve been working on part of your project, things are in a messy state and you want to switch branches for a bit to work on something else. The problem is, you don’t want to do a commit of half-done work just so you can get back to this point later. The answer to this issue is the git stash command.

* To push a new stash onto your stack
    
    `git stash` or `git stash push`

* To see list of you stashes

    `git stash list`

* To apply the last stash

    `git stash apply`

* To apply a stash with it's id(You can see stash ids by list them, it is like stash@{1})

    `git stash apply <stash_id>`

## Reset
* Clean file or directory from add

    `git reset HEAD -- <directory_nName> or <file_name>`

* Reset staged file, but changes will remain. just unstaged.
    
    `git reset <file_name> `

* Reset local to a specific commit by id, change will be remain.
    
    ` git reset --soft commit_id`

* Remove last commit but changes remain, if you want remove changes use `--hard` switch.

    `git reset HEAD^ `
    
## Diff
* See latest changes was created, `HEAD` is a pointer to the most recent commit.

    `git diff HEAD `

* Show changes you have just staged

    `git diff --staged `

*  Show all file in a commit

    `git diff-tree -no--committed-id --name-only -r commit-id`
   
## Tag
* List all tags

    `git tag`

* Create a tag with annotation(tag name) and message

    `git tag -a v1.0.0 -m "Release version 1.0.0"`

* Push all local tags to remote
    
    ` git push --tags`
    
* Push a specific tag

    `git push origin tag <tag_annotation>`

* Delete remote tag if you have permission(make sure tag annotation and branch name are different, otherwise cause to delete branch too)

    ` git push --delete origin <tag_annotation> `

* Delete a local tag

    `git tag --delete <tag_annotation>`
    
## Push and Pull
* push from local branch to remote one

    `git push origin(remote branch name) develop(local branch name)`

* Pull request

    `git pull origin <current_branch_name> `

* Merge a branch with current branch
    
    `git merge <branch_name>`

## SSH Key
To generate and use SSH keys to work with git, clone, pull, push,...
1. Generating a SSH key pair

    Run the following command and enter file in which to save the key, give absolute path like `/home/user/.ssh/git_key` or accept default, and it will save the key in `/home/user/.ssh` dir. You can see the generated key by `ls ~/.ssh`.

    `ssh-keygen`
2. If you don't want to type your password each time you use the key, you'll need to add it to the ssh-agent.
    1. To start the agent, run the following:

        `eval 'ssh-agent'`
    2. Enter ssh-add followed by the path to the private key file:

        `ssh-add ~/.ssh/<private_key_file>`
3. Add generated public key, the file with `.pub` extension to your GitHub or GitLab account, and then you can run any command without entering your credential each time. Your validation will be done by SSH key automatically. Notice you can use generated private key on another machine or add another one on that machine.




  

