# Git Useful Commands
Git useful commands which I have ever used. Please add, update or delete what ever you want, and help to improve it.

## Table of content
* [Init](#Init)

* [Config](#Config)

* [Branch](#Branch)

* [Checkout](#Checkout)

* [Add and Remove](#Add-and-Remove)

* [Commit](#Commit)

* [Reset](#Reset)

* [Diff](#Diff)

* [Tag](#Tag)

* [Push and Pull](#Push-and-Pull)

## Init
* Init git in specified folder

   `git init `

* Get a project from a url

  `git clone url`

* Connect local project to a remote url

  `git remote add origin ulr`

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

* See remote url and branches of project.

    `git remote show origin`

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
* Add current directory changes, untracked files and etc to local

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



  

