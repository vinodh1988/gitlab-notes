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

5. #### Git pull

create a file third. txt in web ide with some content
and commit it with message third-text

locally

```
git pull
```


### Branching 

A Branch is a seperate line of code and files 
which is always created from an existing branch

to create a branch 

```
git branch <branchname>
ex: git branch feature1

git branch

git checkout feature1
```


create a file feature1.txt

add some content

```

git add .
git commit -m feature-commit

```


```
git push origin feature1
```

#### Merging Locally into main branch

Switch to main branch
and merge feature1 branch

```
git checkout main
git diff main feature1
git merge feature1
git push 
```

### Project Collaboration - Merge Request -Branch Security -Strategy

Two accounts

1. Original account - browser1 (We are going to use it as Admin)
2. Another account - browser2 (This one as Contributor/Developer)

In the original account
create a project named - TeamCollab

Under Manager > click Members

* Add a new member
* Add the email of your second account
* Set the role as Developer

Click Branches
Click Branch rules
Check current main branch rules , it is protected branch

### in the second developer account

open the project in the web ide

add the file x.txt

commit it into a branch called feature1

### In the Owner account

open the merge request

click merge button

Merge operation is complet

#### Release branching strategy
----------------------------------

Create a project in your first account
and invite the second user

1. In your original account
go to Branches
create a new branch named release
 visit the branch setting page again

 2. In the second account
 open your project and open WEB IDE

 and create a branch named feature1


 ### Excercise - Dealing the push conflicts, merge conflicts,branch differences, undo, etc

 New Project
---------------

Technique 1 (all other developers)
--------------
Create a project structure and code in the central repo
first

and in all the local machines clone the project


when you clone remote will be preconfigured and default branch would
be main

Technique2 (primary person who created the project)
---------------

Create a local project and structure in a folder

Create a local git repo
 
 How?
          git init
		  
 Git remote  add origin <remote project https url>
 
 Note: you should create a project in central repo with out any readme file
 
 The you add files
 commit and push it
 
 #### The reset command

 Create a a.txt

 ```
 git add .
 git commit -m file1
 ```
 
  Create a b.txt

 ```
 git add .
 git commit -m file2
 ```
 
 
  Create a c.txt

 ```
 git add .
 git commit -m file3
 ```
 
 
 check log

 ```
 git log --oneline
 ```

 reset to the commit of file1

 ```
 git reset <commit id of file1>
 ```

 to clear the untracked files

 first check what would be deleted

 ```
 git clean -n
 ```

 clean the tree with

 ```
 git clean -f
 ```

 #### The revert command

 

The changes in b file is done in two parts

line1
line2      (part1)  commit1

line3
			(part2)  commit3
			
			
the changes in c file is done in two parts

line1
line2      (part1)  commit2

line3     (part2)   commit4

After analysis

commit3 and commit 4 can be un done directly

commit 1 or commit 2 can be undone only after undoing their
respective followsup commit3 and commit4
 
 #### the stash command


 
 
 
 



