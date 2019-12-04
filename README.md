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
   
## Files lifecycle

 ![enter image description here](https://camo.githubusercontent.com/3a084791b3c5ae27a23ceeb5592d3bf80877cba2/687474703a2f2f6769742d73636d2e636f6d2f666967757265732f3138333333666967303230312d746e2e706e67)

You can write `git status` in your workspace terminal to look your files status. 

When you add files in your local repository, they are initally **untracked** by Git.  In other words, Git dont't recognize this files. 

To change a file status from **modified** to **stage** you can `git add filename` or `git add .` for all your files. 

After a commit, the files are now **unmodified**. When you modify them, they are **modified**.

To commit your changes, you can `git commit -m "Add a commit message here"` and then you can `git push origin(remote name) master(remote branch name)` to send your changes to the repository.
