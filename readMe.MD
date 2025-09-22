## Git lab notes


### Central repository
------------------

      It is a single point of truth
	  for the entire project this is
	  one copy of the source code
	  that is shared by all developers
	  all environments
	  
	  but different version code can be maintained
	  in the same respository using a technique 
	  called branching
	  
	  
### Local Repository
----------------
       When a developer wants to work with 
	   project 
	   
	   he/she would
	   clone the project locally and start
	   working
	   
	   the local version of the
	   repository is called local repository
	   
Developer Activities
	 -----------------------
	 
	 When a developer edits/creates a files
	 it is basically untracked in the local repository
	 
	 first it has to tracked
	 
	
### Exercise 1 - Pushing the code

create a file index.html

add the following code into it

```
<html>
    <body>
        <h1>Hello!</h1>
    </body>
</html>
```
	 
Check the status of the repository

```
git status
```
	 
To track the file you need to stage it

Staging: making the file/files ready to be commited, yet
tracked by the local repository

to stage, run the following command

```
git add index.html
```

if you give , git add .  all the untracked files will be added
	 
#### Commiting the file

commiting means adding the file to local repository

to commit

```

git commit -m " your message "

```
	   