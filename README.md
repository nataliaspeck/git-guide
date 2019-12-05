# git-guide

# init

You can initialize a local repository following those steps:
(Take look in your SSH keys to don't have permission problems)

1 - **By line command**

Init the local repository in your machine

    mdkir repository_name
    cd repository_name
    git init
    
    
Create a new repository [here](https://github.com/new) in Github and integrate it in your local repository
		

    git remote add origin git@github.com:nataliaspeck/repository_name.git
    git push origin master

(*origin* is the default name for remote repositories, you can change it)

Important: while doing it by line command, it's recommend that when you create the Github repository you shall not mark the options of initializing because they can cause problems of different content between the local ant the remote repository

2 - **By an existing Github repository**

In your local machine 

    git clone git@github.com:nataliaspeck/repository_name.git
   
## files lifecycle

![enter image description here](https://camo.githubusercontent.com/3a084791b3c5ae27a23ceeb5592d3bf80877cba2/687474703a2f2f6769742d73636d2e636f6d2f666967757265732f3138333333666967303230312d746e2e706e67)

You can write `git status` in your workspace terminal to look your files status. 

When you add files in your local repository, they are initally **untracked** by Git.  In other words, Git dont't recognize this files. 

To change a file status from **modified** to **stage** you can `git add filename` or `git add .` for all your files. 

After a commit, the files are now **unmodified**. When you modify them, they are **modified**.

To commit your changes, you can `git commit -m "Add a commit message here"` and then you can `git push origin(remote name) master(remote branch name)` to send your changes to the repository.

## logs

To see the history of commits in some branch, you can `git log`. It shows the hash of the commits, the Authors, the Dates and the descriptions.

To see the changes of some special commit, you can `git show HASH_OF_COMMIT`

To see a list of commits by author, you can `git log --author='NAME'`

To see a 'graph' of the connections between commits, you can `git log --graph`

Other util commands:
`git shortlog` or `git shortlog -sn` to see short and direct informations about the commits.
`git log --decorate` to see extra informations about the commits, like branchs and etc.   

## diff

To see the diff between your changes and the current state of the Git repo, you can `git diff`.

To see only the name of the changed files, you can `git diff --only-name`

## undo things

To undo all the changes you do (and not commit yet), you can `git checkout .` and to undo the changes in a special file, you can user `git checkout FILENAME`.

To unstaged changes, you can `git reset`, following the same logic of all ( . ) and file (filename) for the extra params.

To reset things you already commited, there are three main options:

`git reset --soft COMMIT_HASH`: this command return the changes commited to a staged status.

`git reset --mixed COMMIT_HASH`: this command return the changes commited to a modified status.

`git reset --hard COMMIT_HASH`: this command clear all the changes of a commit. 

Important: supposing you want to reset the last commit, you need to put the penultimate commit hash in the reset command.

## remote

To add a remote repo in your Git, you can use `git remote add REMOTE_NAME`

To list your configured remote repos, you can `git remote`

## branch

To create a new branch, we use `git checkout -b BRANCH_NAME`

To list all the branchs, we use `git branch`

To delete a branch, we use `git branch -D BRANCH_NAME`

To change the working branch, we use `git checkout BRANCH_NAME`

Rebasing and merging are both designed to integrate changes from one branch into another branch but in different ways.

 - **Merge** `git merge BRANCH_NAME`
merge mantains the chronological history of commits, and add a new commit, called merge commit

 - **Rebase** `git rebase BRANCH_NAME`
rebase add the commits in the finish of the branch,  the order is not keep

## .gitignore

The `.gitignore`  file tells git which files (or patterns) it should ignore. You can view an simple example in this repo.

## stash

The `git stash` command takes your uncommitted changes (both staged and unstaged), saves them away for later use, and then reverts them from your working copy.

At this point you're free to make changes, create new commits, switch branches, and perform any other Git operations; then come back and re-apply your stash when you're ready.

You can use `git stash list` to list all your saved stashes. Git keeps the order like an array of stashes (stash{0}, stash{1}...)

We use `git stash pop` to apply a stash and delete it from the list. In other hand, we use `git stash apply` to apply a stash but keeping it in the list for previous use.

To clear your stash, use `git stash clear`.

## tags

You can work with tags to divide your updates as releases versions. With `git tag` you can list all configured tags.

To create a tag we use `git tag -a 1.0 -m "Release One"` and then `git push origin master --tags` to send the tag to the remote repo. 

If you want to delete a tag, we can use `git tag -d 1.0` and then `git push origin :1.0` to exclude the remote tag.
