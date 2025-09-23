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

#### Checking the logs

to check all the commits made

```
git log --oneline

```

#### To check details of a commit

copy the commit id from the log

run



```
git show <commitid>
```

press q to come out

#### To check what brach you are currently in

Run

```
git branch
```

the branch with * is the current

#### To check what is the remote origin

To know to which central repo you are connected

```
git remote get-url origin
```

### To push the code

run
```
git push origin main
```

### Case Study - Comparing, Pulling , Fetching and Handling Conflicts
1. 
In the local repository
create a file index. html
add any random content
stage it and commit it

```
git add .
git commit -m first-commit
git push
```
2. 
open Web iDE 
create a file named second.txt add some content
graphically
commit it with a message second-commit

3. In the Local repository, add a new file index.css
add some content and

```
git add .
git commit -m css-commit
git push
```

Note: you will get an error, because in central repo you have
and additional commi which you do not have locally
 4. 
#### Git Fetch

Instead of pullin, which actually adds the files directly into
the repos

we can first bring in the changes with actually
commiting the changes locally

this can be done using

```
git fetch 
```
it will fetch changes but will not merge the changes locally

you can compare local repo with remote repo using git diff command

```
git diff main origin/main
```

if there is no conflicts, you can merge the fetched code

```
git  merge
```