Reference: A Quick Guide to Organizing Computational Biology Projects http://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1000424

The website for today's lesson can be found here: http://chendaniely.github.io/2015-11-23-harvard/.

You can read up on the software carpentry Git lesson here: http://swcarpentry.github.io/git-novice/

Link to the etherpad: http://pad.software-carpentry.org/2015-11-23-harvard
I will save this after the workshop into the course website so it's backed up in multiple places.

We will learn not to do this anymore: https://xkcd.com/1597/

Please write good commit messages: https://xkcd.com/1296/

Git will help you version control so you you really do end up with 1 final doc: http://www.phdcomics.com/comics/archive.php?comicid=1531

Interactive tutorial on git and branching: http://pcottle.github.io/learnGitBranching/

Some links about the git flow model of collaboration.
Don't feel the need to follow this model right away.
It took me a good year or so with git to start to understand what the model is trying to accomplish.
As you get more confortable with Git, it'll be easier to pick up a new topic within Git.

http://nvie.com/posts/a-successful-git-branching-model/

https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow

The stream seemed to work!

Git collboration: https://www.livecoding.tv/video/2015-11-23-harvard-git/
Git branching: https://www.livecoding.tv/video/2015-11-23-harvard-git-branches/

# Instructions for the exercies

## Collboration and Forking Exercise
```
Pair up, into person A and person B
Part I
1. person-A fork person-B's repository
2. person-A clone the forked repository to your local computer
3. person-A make a change to the repository
4. person-A push the change to your github account
5. person-A create a pull request to person-B
5.1. collaborate
6. person-B accept the change    

Part II
1. person-B make a new change after your pull request
2. person-A add person-B's repository as a new remote (upstream)
    `git remote add upstream GIT_URL`
3. person-A get the new changes from person-B
4. person-A update your github fork so it is the same as Person-B    

part III
1. switch roles.
```

## Branching Exercise
```
Pair up, into person A and person B
Part I
1. person-A make a change to the repository (use a branch)
        this repo will be the cloned branch you used earlier in part II
        from person-B
        git checkout -b BRANCH_NAME
        make some changes and commits
2. person-A push the change to your github account
        git push origin (master) *this is what you did before
        git push origin BRANCH_NAME *this is what you will do now
3. person-A create a pull request to person-B
4.1. collaborate
5. person-B accept the change
        This change will take the branch from person A
        and merge it into person B's master branch

Part II
1. person-B make a new change after your pull request
        Either do it on a new branch
2. person-B send yourself a pull request and have person a collaborate, and merge
3. person-A get the new changes from person-B
        (git pull upstream)
4. person-A update your github fork so it is the same as
Person-B 
```

# Etherpad Contents

Reference:
A Quick Guide to Organizing Computational Biology Projects
http://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1000424

http://software-carpentry.org/
go to lessons: http://software-carpentry.org/lessons.html
go to the git site: http://swcarpentry.github.io/git-novice/
Git configurations: http://swcarpentry.github.io/git-novice/02-setup.html

learn git branching: http://pcottle.github.io/learnGitBranching/

git flow workflow:
    https://www.atlassian.com/git/tutorials/comparing-workflows/feature-branch-workflow

http://nvie.com/posts/a-successful-git-branching-model/x`

git setup:
```bash
$ git config --global user.name "Vlad Dracula"
$ git config --global user.email "vlad@tran.sylvan.ia"
$ git config --global color.ui "auto"
$ git config --global core.editor "nano -w"
```

```git init```
this will turn the current folder into a git repository, everything from here on will be tracked
git status 

```ls -a``` will let you see hidden folders - e.g. the `.git` folder

`git status` allows us to see what's being tracked and anything that has changed

example:
`git add README.md`      
This adds the file to the staging area. This only needs to be done once. You can also use: git add . 

`git config --list`        This lets you see what commands you have run

`.gitignore`
Git will not track what's specified in here

`git log` will let you see the log of all the work you had done in reverse chronological order
`git log --oneline` to see with less whitespace
exiting using "Q" if running the log opens a new file

`git diff` to see the differences between two files
use this if you're not sure why a file is being shown as 'modified'
`git diff HEAD~1` this lets us check what the file looked like two commits behind us
`git diff --stage` for one commit behind when you staged files

Use `touch` to create a file

Track a deleted file by adding the file after git status just like any other action with a file. You can "undelete" using `checkout`

`checkout`
`git checkout` is  used to take your "head" and point it somewhere else, like to your old commits 
You can do this using either `~` or the hash from the log

Panic button
`git reset --hard`

Moving a git tracked folder (entire repo) to another folder is fine. Git only tracks what's happening within the repo

GitHub in the cloud (BitBucket is an alternative)
Unlimited free public repos with GitHub
can distribute "raw" by just right clicking raw button and sharing that link

Remote origin 
"origin" --> where
"master" --> what
`push` to the cloud
`pull` to bring it back to your local repo

Adding a remote repo:
`git remote add origin [webaddress.git]`
insert your repo address (https) in the brackets
Use git remote -v to check whether or not you have connected to your remote repo on GitHub 
git push origin master 
this is used to push your local repo to your remote; you may initially be prompted to enter your username and password

Unstaging a file
`git reset`

`git pull origin master`
"pulling" the changes that exist in the remote repo to your local machine
Fast forward message == extending our local master branch one commit

Fixing conflicts within a file 
done manually -- you clean this up in your text editor
Then you need to push back to the remote

Live Coding Stream:
https://www.livecoding.tv/chendaniely/

Cloning  - one time download from GitHub to local computer
downloading and initiating repo into your local machine

Fork - one time download from GitHub to GitHub
Click the "fork" button to make a copy of the repo you want to contribute to *in your account*
You can then edit this version of the code and eventually submit a pull request to the original repo owner

Pull Request - please accept my changes from my fork back into your repo
*Always add a clear message to the person who's repo you forked. 

3 Part Exercise for Collaborating with Others:

## Branching

Branching- a way to give a series of commits and easy to remember name
e.g. simulation with two different parameters; you could create a branch for each version of the simulation

log and show everthing:
    git log --oneline --graph --decorate --all
    * hit q to exit the log

Creating a new branch
`git checkout -b something_else`
replace "something_else" with the name of your new branch
`git branch -a`
lists all the branches
`git checkout branch_name`
used to move between branches. Replace branch_name with the name of your branch or master.
* using git branch will let you create a branch but will not move you to that branch

Can use cat to see the changes in the repo

To merge branches you must be on the branch you  want to merge into
e.g. to merge branches into  master, you much checkout master before you merge

`git branch -d `
deletes the branch -- lowercase is safer as you'll be prompted to make sure you're ready to delete. Don't use uppercase.

`git push origin --delete [branch_name]`
will delete the remote branch

`git rebase`
e.g. git rebase master
re-writting history - rewind and move forward to the head of master then replay commits

