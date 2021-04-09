---
layout: post
categories: [Git Github Notes]
title: "Basic Git Notes."
---


Configuring username and email in git    

        git config --global user.name "varadan"
        git config --global user.email "varadan_pornhub@nic.in"

To list all the git settings    

        git config --list

To get a specific setting.  

        git config user.name #for viewing user_name
        git config user.email
        

To get help.     

        git help #git will list all the options adjoining 
                 #help and also lists most common commands
                 #for which help can be used with.
        
        #for example
        
        git help commit

Some system commands that will help in navigating the file system    

        cd ~ #changes the directory to the system home directory
        cd .. #changes the directory one step backwards the node
        pwd #lists the current working directory
        ls #lists all the files and directories in the cwd.
        
        clear #this clears the console
        

To intialise a git repository.     

        pwd #displays the current working directory of git
        
        cd <path_to_the_directory_git_should_work_in>
        
        git init #intializes a git repository in the current working directory

To commit a change to the git repository      

        git add .
        git commit -m "a commit message" #commit is like save the state of the 
                                         #repository at this point in time.
                                         

How to view the commit history.     

        git log
        git log --author="a author of this repository"
        

To view the current state of the repository.    

        git status #displays any changes that needs to added to the repository or not.
        

To View the modifications   

        git diff #differences in the working copy and the repository copy.
        

What is a working copy?  
The files we make constant edits before commiting to git is called working copy. 

What is a repository copy?  
When we commit a file to git, git makes a copy of that file and keeps that copy with it this is called repository copy.    

If a file let's say random.txt is changed and added to the staging area,      

        git diff #shows no differences as this file now is in the staging area
                 #diff only shows differences in the working copy and the repository
                 #copy


        git diff --staged #this command will show differences in the files 
                          #repository and the staging area
                          

To remove a file from working area.     

        git rm <name_of_the_file>
        
        git commit -m "a message"

        

To rename a file.    

Method 1

Add a new file then delete the old file == renaming the old file

        git add <a_new_file_name>
        git rm <a_old_file_name>
        
        git commit -m "a commit message"
        

Method 2

Renaming a file.  
In Git renaming a file == moving a file to a new file in the same location    

        git mv <name_of_the_old_file> <name_of_the_new_file>
        git commit -m "commit message"

Moving a file in Git            

        git mv <name_of_the_old_file> <file_destination\name_of_the_new_File>
        git commit -m "commit message"
       

To add and commit in one go

        git commit -am "a commit message"
        

Git checkout

        git checkout -- <name of the file> #checkout is a way to tell
                                           #git to take the <name of the file> file
                                           #from the repository
                                           #and put that in the working area.
                                           #What does -- mean?
                                           #it tells git that the name given to checkout 
                                           #is not a branch
                                           #note:- a space is present after --.
        git commit -m "message"
                                          
            
        

Unstaging a file.   

What is unstaging?  
it is to tell to git to remove a file from the staging area.

        git reset HEAD <name of the file to remove from staging area>
        
        

To get old version of the project.   

        git checkout <first few charachters of commit number> -- <name of the file>
        git commit -m "a commit message"
