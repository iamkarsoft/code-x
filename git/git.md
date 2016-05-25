This is an article documenting my journey using Git. Git is a version control system used for software development or programming in general, although it may be used for other stuff like storing files on a remote server and even hosting a website with github pages. Everything you see here is codes that i have used and how i understand them, you may have a different way and some of my codes may be wrong.

1- Setting my git identity

This is to let github know who is using it by setting your name and email address.

This is done after you’ve created an account on github.com, and probably created a repository and you are actually going to push your local project to the remote server. In other fot github to upload the project to your account, it will require you to enter your username and password credentials. You can set them in your terminal using the following code.

```
$ git config --global user.name “ Kofi Amoussou”
```
after letting github know your name, now you set your email address

```
$ git config --global user.email “ karsoft92@gmail.com”
```
2- Setting my editor

Text editors!! there are dozen of them in the wild. I personally use 4 text editors which are sublime text, brackets, atom and notepad ++, i do interchange for some reasons but the editor i often use is Atom. You can set your default text editor in git

```
$ git config --global core.editor “ Atom ”
```
3- Initializing your project

As i said git is used to document the progress of your projects , meaning you save and upload the progress of your code along with your source code on a remote server. Git does that by placing a special folder in your local repository, before it does that you will have to initialize that repository to allow git track the folder. You can initialize and track a folder by running the following code, you must be in the folder you want to track , for example if i want to track the Koofi folder , i will have to switch to the kofi folder located in my xampp folder which where my local server resides

```
$ cd c:/xampp/htdocs/koofi
```

after that i will run the code to initialize the folder

```
$ git init
```
4- Checking file status

Now that you have initialize your project, git will have access to your folder but it won’t start tracking files you haven’t given it permission to track. To check the files git is tracking, you run the command

```
$ git status
```
5- Tracking Files

To track files and folders in your local repositories.

```
$ git add index.html
```
The previous code adds the file index.html to be tracked.

6- Opening a file

You can open file through the terminal, so atom is my defaut editor hence.

```
$ atom index.html
```
7- Seeing Difference or changes made

to see the difference you made in your projects

```
$ git diff
```
or


```
$ git diff --staged
```

8- Viewing the history of your project

If you want to view the history of your projects, basically the history of your commits from the first commit to the last one

```
$ git log
```

9- Adding a remote file
Lets say you want to add a repository you found on github to your local machine

```
$ git remote add origin remote-url
```
then you will need to fetch its content

```
$ git fetch 
```
and finally if you want to push your changes to the repository

```
$ git push origin master
```

10- Branches

Branches are like versions just like a tree has a branches but all of it form a tree. You can create a branch when you want to work your project without touching the current source. So a branch imports your code to another environment where you continue to work and when you are satisfied , you can then merge your branch with the main project environment which is known as the master

creating a branch in the terminal

```
$ git branch branchname
```

after which you will have to switch to its environment by typing in the command line

```
$ git checkout branchname
```

or you could just try the second option that creates the branch and switches to it’s environment automatically

```
$ git branch -b branchname
```
To merge a branch with master, first checkout and go back to your master branch

```
$ git checkout master
```
then you can merge your other branchname into the master branch to update the master branch

```
$ git merge branchname
```

if you are done merging into the master branch, you can now dispose of the other branch if you want to

```
$ git branch -d branchname
```

sometimes deleting your branch may cause you some problems and will require you to force git to delete the branch. you just do that by simply changing -d with -D hence.

```
$ git branch -D branchname
```
maybe you want to see all the branches you’ve created

```
$ git branch
```
This will give you a list of all your branches and there will be the one with (*) meaning you are currently in that branch.


11- Pushing your branch
If you want to push your branch to the remote repository, you just use the following command

```
$ git push origin branchname

```

12 - correcting permission 

Step 1: From your project repository, bring in the changes and test.

```
git fetch origin
git checkout -b correct_permissions origin/correct_permissions
git merge master
```

Step 2: Merge the changes and update on GitHub.

```
git checkout master
git merge --no-ff correct_permissions
git push origin master
```
