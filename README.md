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
   
