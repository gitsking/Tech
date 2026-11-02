XML
Markdown
reStructured text
AsciiDoc

# Command line (git gui) and GIThub

1. step1: create a repo
2. step 2: clone it into local
[Git documention repo link:] (https://docs.github.com/en)
> git tokens:  
> When git asks you for a username and password, use your GitHub username and use the personal access token code for your password. For example:

,,,
$ git clone https://github.com/USERNAME/REPO.git
Username: YOUR_USERNAME
Password: YOUR_PERSONAL_ACCESS_TOKEN
,,,

**Useful Unix commands**
1. With git, you'll be using Unix commands to move around 
your directory structure (folders and files)
2. **print working directory (pwd)** tells you what 
folder you are in
3. **list (ls)** tells you what files and folders 
are in your current folder
4. **change directory (cd)** moves you to a new folder 
(Example: $ cd PremKumarMogi/git-practice/sample)
Changes your current directory to a new directory
Special directory names:
. (one period): your current directory
.. (two periods): up one directory
~ (tilde): home directory
5. **make directory (mkdir)** creates a new folder

## Short Cuts

Tab helps to fill the data, takes last used word

up arrow used to copy the previously used commands

## Command structure

- General command structure
- command -o -- option argument (s)
- Options modify the command in some way
- One dash for one-letter options
- Two dashes for multiple-letter options
- Options before arguments
- Because elements are separated by spaces, sometimes
you need to put arguments in quotes

git

**Example git commands**
- Git commands start with git and then a command
- git config -- list
- git config -- global user.name "Peter Gruenbaum"

**Example one-letter option**
- commit -m "Marketing changes"

# Section 2: File Stages
- A file goes through 4 stages in documentation.
unstages > staged > committed > pushed

**Stages defined**
1. **Unstaged:** You've made a local change to the file. (Or added
or deleted a file.)
2. **Staged:** You've marked a local change as something you want
to commit to save in git
3. **Committed:** You have committed the file, saving this version
in git.
- Each commit has description to help you remember what this
version is about
4. **Pushed:** You've uploaded the file to the server so that others
can access it

## How to Move Files from One Stage to the Next
1. **Unstaged:** Just make changes on your computer
2. **Staged:** Use the git add command
3. **Committed:** Use the git commit command
- Add a description
- You don't need to tell it which files, because it commits the
staged ones
4. **Pushed:** Use the git push command
- You don't need to tell it which files because it pushes all the
committed files that haven't been pushed already

## Text and Binary Files
- Git works on both text and binary files
- **Text:** documents
- **Binary:** images, video, audio, etc.
- Both are treated the same
- The only difference: merging different versions
1. **Text:** software can reliably figure out how to merge
2. **Binary:** extremely difficult to figure out how to merge.

## Adding files to repository

- add a new file to a folder, this will be considered as unstaged file.


 > For this exercise, you will be creating a new text file, adding it into Git, 
 committing it, and then uploading it to GitHub.
1. First open your text editor (for example, Notepad++ for Windows, Atom for Mac, 
etc.). Create a new file and then write two paragraphs of documentation for a 
product that you make up. Separate the paragraphs with a blank line.

,,,
This documentation describes how to use the Pavel robotic toothbrush.
Note that this toothbrush is not safe to use for children, adults, or pets.
,,,

2. Save it in your exercise folder that you cloned the repository into. 
Give it the name docs.md.
3. Open your terminal app and cd to the exercise folder in your home directory. 
Do an ls (list) command and you should see docs.md listed. README.md is also 
listed because that was created when you cloned the repository.

,,,
cd ~/exercise
ls
,,,

4. Do a git status and it should list docs.md as “untracked”. This means it’s 
unstaged.
,,,
git status
,,,

5. Now stage all files in the current directory with the git add command. Only docs.md will be staged, because you haven’t made any changes to README.md.

,,,
git add .
Git and GitHub for Writers Exercise 4
,,,


6. Do a *git status* to verify that *docs.md* is staged.

7. If this is the first time you have used Git, before you do a commit, you need to give git some
information about yourself so that when it does a commit, it can include that information. Type
these two lines, replacing “Jane Doe” and jane@example.com with your own name and email.
(If you have already been using Git, you will not need to do that.)

,,,
git config --global user.name "Jane Doe"
git config --global user.email jane@example.com
,,,

**Note:** You may get a message suggesting that you type *git config --edit*. I do not recommend
doing that, since it tends to bring up an ancient, very confusing editor called Vim. If you do end up doing
that, type :x to exit, and do the git config lines above instead.

8. Now commit all of the staged files, which is just docs.md. Use the -m option to add a message.
The example below shows one possible message, but you can put whatever you like between
the quotation marks.

,,,
git commit -m "Added docs.md"
,,,

9. Again, do a *git status* to verify that everything is committed.

**Note:** Notice that you haven’t had to sign into your GitHub account in any way. The reason for this is
that you created a public repository, so anyone can read it. However, it’s not true that anyone can make
changes to it. You have to have access in order to do that. When you push your changes to GitHub, it will
require that you sign in if you haven’t already.

10. Type git push origin to upload your changes. Note that the first time you use Git, you will be
asked for your username and password. This happens differently on different operating systems.
On Windows, a dialog will pop up. On Mac OSX, you will be asked in the command line.

,,,
git push origin
,,,
11. Open up the browser with your GitHub account. Go to your exercise repository by clicking on
the exercise link. (Or if you are already there, refresh the page.) You should see the file has been
added, now you have two files: docs.md and README.md.

# Making Changes 

introduction
1. what happens when you make a change?
2. How to stage, commit, and push that change

## What happens when you make a change
1. File is automatically unstaged
2. Do a git add to stage it
3. You still have a chance to change it before committing
- If you do, you will need to do a git add again to stage it again
4. Do a git commit to commit it
5. Do a git push to upload it to GitHub

[Open exercise] (C:\Users\PremkumarMogi\git-practice\sample\Exercise+5+Changing)

# renaming and Deleting files
introduction
1. how to rename a file.
2. How to delete a file.

> What happens when you rename a file

- A renaming is considered a change, and the file is
automatically unstaged
- Do a git add to stage it
- Do a git commit to commit it
- Do a git push to upload it to GitHub
- An alternative is git mv
1. This combines renaming and git add .

make changes--> add changes --> commit changes --> push changes

## Delete a file

- A delete is considered as a change, and the file is
automatically unstaged
- Do a git add to stage it
- Do a git commit to commit it
- Do a git push to make the changes to GitHub

[Open exercise 2] (C:\Users\PremkumarMogi\git-practice\sample\Exercise+6+Renaming+and+Deleting)

# Why git designed this way?


1. When would you make changes but not stage them?

- You don't stage changes until they are at a point where you
expect to commit them
- You don't know yet that you are going to keep these
changes

** Example:**
- Your project manager wants you to totally reorganize to see if it
works
- You may decide to just delete all the changes and go back to the
old organization

2. When would you stage changes but not commit them?

- Staging gives you a final check to make sure it's what you want

**Example:**
-  You stage some changes
-  You read over them one last time
-  If they are fine, you commit them
-  If not, then you continue editing, unstaging the files

3. When would you commit changes but not push them? 

- Until they are pushed, they are private
- You might not be ready to share

**Example:**
- You finish a draft on one section and commit it
- You finish a draft on a second section and finish it
- You stage and commit the edits
- Now you are ready and you push both commits
- GitHub has both, and your collaborators can use the latest

# Working with previous commits

* Introduction

- The power of version control
- How to view previous commits in GitHub
- The HEAD commit
- How to work with previous commits in Git
- How Git works under the covers
- Best practices for commits

**1.HEAD**

- Git labels a special commit as HEAD (all capitals)
- It means that commit you are currently working on
- This is usually the most recent commit you've made
-- Technically, the most recent you've made on a branch
- However, you can move HEAD to a different commit if
that's something you want to work with

**2. GIT**

- git log shows you your history
- git log --online presents a compact version
-- set the commit that i am working on
- use git checkout to set the current version to an old commit
- use git checkout master (brings back to the version you went back from) to set the current version to the most recent (on the master branch)
-- more on the master branch later

>> ** Note:** Dont use checkout to make changes by moving back to previous version,
only use it when you need any data from previous version.

## Best practices for commit

- commmit often
- ideally each commit for changes contain just one change

-- for ex: added a section, removed a section, 

- clear, concise message for each commit
-- lets you find changes easily.

[sample excerise] (C:\Users\PremkumarMogi\git-practice\sample\Exercise+7+Going+Back+in+Time)

#Tags

**Covers**
1. What is a tag?
2. How to add a tag
3. How to see what tags exist
4. Checking out a tag
5. Pushing a tag

## Tags
- Sometimes you want to label a commit as special
-- This is called a tag
- For example: you could tag a commit that corresponds to the files that are 
part of a release
- A tag is just a label applied to a commit to make it easier to
find
- Tags have a name and a description
- Tags are applied locally. use git push to upload it to GIThub

## Git commands
- git tag -a adds a tag with name and description

,,,
-- git tag -a my_tag -m "This is my new tag"
,,,

- git tag lists all tags
- git checkout tags/<tagname> to checkout a tag
- git push origin <tagname> to push a tag

[Tag Exercise] (C:\Users\PremkumarMogi\git-practice\sample\Exercise+8+Tags)

#Pull

**Covers**
- Collaboration and version control
- What is a pull?
- Conflicts
- Binary files
- Fetch

## Collaboration

- The main advantages of version control:
-- Going back in time
-- Collaboration
- Version control lets multiple people work on a file at the
same time
-- But you each have your own copy
- You can control how that those separate changes are
incorporated

## pull

- git pull downloads all commits that have been pushed
to the repository
- You can only do a git pull if you have committed your
files
-- In other words, no merging unless you are at a good stopping
place

### Handling changes
- How does git pull handle changes? Three cases:
- Remote file hasn't changed since last pull you've done.
-- Leaves local file as is, whether you've changed it or not.
- Remote file has changed. Local file hasn't changed.
-- Replaces local file with remote file
- Both remote and local files have changed.
-- Remote file is merged into local file.

## Merging

- How does a merge happen?
- Git compares line-by-line, noticing which lines have changes
- If the line hasn't changed remotely or locally, then the line
stays the same
- If a line has changed, either remotely or locally, it uses the
changed line
- If the line has changed both remotely and locally, then this
is called a "conflict"

## Conflict

- If a line is changed both remotely and locally, then Git doesn't
have enough information to know which one is right.
- It will notify you of a conflict
- It puts both the old and new lines in the file, marking them with
<<<<<<< and >>>>>>> symbols, so you know where they are
- Edit the files, choosing how you want to merge and removing
the <<<<<<< and >>>>>>> symbols
- Tell Git that the conflict is resolved.


## Binary files
- Git can only merge text files
-- Remember, it goes line by line
- Binary files (images, audio files, video files, etc.) cannot be
merged
- You will need to choose a version
- If you need to merge, you will have to do it manually

## Fetch

- You may come across the git fetch command
- This will download the remote files, but not merge them
- You will need to do the git merge command to merge
- git pull does both automatically. git fetch and
git merge give you finer control.
- As a writer, you will probably only need to use git pull

**Exercise**

- Create a change on GitHub
- Pull the change and see it locally
- Create a change on both GitHub and locally
- Pull the change and merge
- Create a conflict
- Pull the change and resolve the conflict

[pull excersice] (C:\Users\PremkumarMogi\git-practice\sample\Exercise+9+Pull)

# Branches
- Create a new branch when you start making changes for that particular purpose
- Once you have everything in the branch the way you want it, merge it back into 
the branch it came from.

## The master branch

- When a repository is created it has one branch called
master

- The master branch is the root branch
- Unless you are on a very small project, you typically don't work directly on the
 master branch
- Instead, you create a branch, make commits, and then merge back into master

## Creating a branch
- git branch branch-name creates a branch named
branch-name
-- Branches off the current branch
-- But you stay on the current branch
- *git checkout -b branch-name* creates a branch and also moves you to that branch

## Branch names

- Branch names can use letters, numbers, dashes, periods, and forward slashes
- They are case sensitive Most common is to use lowercase with dashes between words
**Example: api-docs**
- Slashes are used to create groups of branches
- Example: v1.2/api-docs, v1.2/login-fix

## Moving to a branch
- git checkout branch-name moves to the branch named branch-name
- You can only move to another branch if all files are committed
-- In other words, you want to be at a good stopping place
-- If you aren't ready to commit, you can use git stash (more
later)
- *git branch* displays all brancehs and which one you are on.

## Deleting and pushing
- *git branch -d branch-name* deletes the branch named branch-name
-- Only do this once you have merged your changes or else you are
sure you don't want that branch
- *git push* uploads everything to the server, including new branches
-- Until you do this, all new branches are local only
- Once pushed, you can delete the branch on GitHub
-- You will see the changes when do a git pull.

**Exercise**

-Create a branch
- Listing branches
- Making changes and committing
- Switching branches
- Pushing the branch to GitHub

[deleting and oushing exercise] (C:\Users\PremkumarMogi\git-practice\sample\Exercise+10+Branches)

#stash
> Covers
- What if you aren't ready to commit?
- Stash command
- Listing stashes
- Popping a stash
- Naming stashes

## Stash

- If you are not ready to commit, then Git provides a way to "stash" your changes.
- You revert back to the last commit
- You can then switch to another branch.
- When you are ready, come back to your branch and "pop" your stash
- You will see the changes that you made when you stashed

## Stack

- Each time you create a stash, it puts it on the top of a list.
- When you "pop" a stash, it removes it from the list.
- Now the top of the list is the second most recent stash you created.
- It's like a stack of dishes

## Git commands

- git stash will create a new stash and revert to the most recent commit
- git stash list will list all the most resent stashes
- git stash pop will restore your changes to the most recent stash on the stack
-- Changes are unstaged
-- Removes stash from top of the list

**Exercise**
- create a named stash
- list your stashes
- moving to another branch and back
- pop your stash

[exercise] (C:\Users\PremkumarMogi\git-practice\sample\Exercise+11+Stash)

# Merging Branches

**Covers**
- What does it mean to merge a branch?
- Merging through command line vs. GitHub
- Pull requests
- Conflicts
- Squashing commits
- Merging with git command line

## merging

- Create a new branch in order to make changes for a particular purpose
-- Could be master, or could be another branch
- Once you have everything in the branch the way you want it, merge it back into 
the branch it came from
- now original branch has the changes that you made.

## 2 ways to merge

- You can merge locally using the Git command line
- You can merge remotely using GitHub
- GitHub is easier and provides really good visual tools to
lead you through the merge process
-- I recommend doing it this way if you can
-- Changes need to be pushed

## pull requests

- When you are ready to merge your branch, you create a
pull request on GitHub
- Often someone else will review your changes and then
approve the pull request
- If possible, GitHub will merge the changes automatically
- If there are conflicts, GitHub will display them and let the
approver resolve the conflicts before merging


## Merge vs. squash and merge

- When you merge, you can either:
-- Merge pull request
-- Squash and merge pull request
 **Merge pull request**
- Every commit that was in the new branch becomes a commit on the original branch

** Squash and merge pull request **
- All commits that were in the new branch are squashed down into one
commit on the original branch
- "squash and merge" simplifies the history

## git diff and merge

- The git diff command compares two branches
-- * git diff branch1 ... branch2 *

- The git merge command can merge the branch locally
-- Change to the branch to merge into
-- *git merge newBranch*

**Exercise**

- Create and accept a pull request with no conflict
- Create and accept a pull request with a conflict

[Exercise-12] (C:\Users\PremkumarMogi\git-practice\sample\Exercise+12+Merging+Branches)

# Cloning

** Covers **
1. What is cloning?
2. How to clone a project on GitHub
3. HTTPS vs SSH cloning
4. What is the origin in Git commands?

## Cloning

- Cloning is making a local copy of a remote repo.
- This creates copies of all the files and history locally.
- when cloned you will receive both visible and hidden files.

## HTTPS vs SSH

- You may have noticed a link that says "Use SSH"
- You can clone using either secure HTTP or secure shell (SSH)
- HTTPS is simplier
- SSH is more secure
- SSH requires generating a special SSH key and provide the passphrase.

> Refer on web reagrding SSH key and key generation.

## origin

- origin in Git is just shortcut for the URL where you cloned your repository 
from
- So if you cloned your repository from
https://github.com/pgruenbaum/exercise.git

-- then git push origin is the same as:
-- git push https://github.com/pgruenbaum/exercise.git

- In theory you can push your changes to other repos
-- This is very unusual

[Exercise 13] (C:\Users\PremkumarMogi\git-practice\sample\Exercise+13+Cloning)

# Rebasing

1. what is rebasing?
- Think of Git history like a timeline of commits.

- Suppose the main branch has moved ahead while you were working on your own branch.

- Without rebase:

main:    A --- B --- C
                  \
feature:           D --- E

- Then someone adds commit F to main:

main:    A --- B --- C --- F
                  \
feature:           D --- E

- A rebase takes your commits (D and E) and "replays" them on top of the 
latest main.

main:    A --- B --- C --- F
                            \
feature:                     D' --- E'

** In Simple Terms **

- Merge = Combine two branches by creating a new merge commit.

- Rebase = Move your branch to start from the latest version of another branch,
 making the history look cleaner.

2. When would you use it?
-

3. Git Command
- From your branch, use the git rebase command
followed by the name of the branch you are rebasing from.
- For example:
-- *git rebase master*
- Usually this is the branch that you branched from

# handling problems

1. How Git can create difficult situations
2. Overall strategy for handling problems
3. Reverting unstaged changes
4. Reverting unpushed commits
5. How to start over if you need to

## How Git creates difficult situations

- With all the branching and merging, sometimes you'll find yourself in a 
situation where Git won't let you do something you need to do
-- Won't let you commit, push, pull, etc.
- Try to figure out how to fix it
-- Git provides suggestions
-- Get help from internet and other people

## A strategy you can use
- Sometimes it's faster to not try to fix Git problems the
"correct" way. Instead:
1. Copy your changed files to a folder outside of the repo

2. Revert your changes back to a point where Git works again

3. Manually merge the changes back in.

## Reverting unstaged changes
- If you've made changes that you haven't committed yet that
you don't like use the git reset command
- I recommend just searching on something like "how do I
undo things in git" to see the exact syntax
- It's:
 *git reset -- hard* 
 
## Make your local version the same as remote
- If you feel like you've messed up your local version, but you know the remote 
(GitHub) version is good, you can make the local the same as remote
- I recommend just searching on something like "git make local branch same as
 remote" to see the exact syntax
- It's:
-- git fetch origin
-- git reset -- hard origin/branchName
--- where branchName is the name of the remote branch

## Start over

- If nothing works, here's a last resort:

1. Copy your changes to files outside the repository.

2. Delete the local repository

3. Clone the repository again into a new folder

4. Manually merge your changes back in

# Ignoring files


1. Why you would ignore files
2. The .gitignore file
3. Ignoring files
4. Ignoring folders

## Why you would ignore files
- Software typically consists of "source" files and "build" files
- Tools take source files and create build files, which are the final
product
- For documentation, source files might be Markdown and build
files would be HTML.
- You should only have source files in Git
- Build files take up too much space and are redundant with the
source files
- So build files should be ignored
- You might also have your own local files that you just want to
keep local


## .gitignore
- To ignore files:
1. Create a file called . gitignore in the top level directory of your local 
repository
2. List any files ignore (you can use "wildcard" characters)
3. List any folders to ignore
4. Add the file to the repository and commit

> **Note** that because it starts with a period, it will be considered a hidden file.

## The file structure

- Any line that starts with # is simply a comment, and doesn't
do anything
- List any file to be ignored using a path
- You can use * for a wildcard (meaning anything)
- List any folder by ending with a /

**Example**
# Ignore the file notes.txt in the tmp folder
temp1/notes.txt

# Ignore all .txt files
temp2/ *. txt

# Ignore everything in the tmp folder
temp3/

# Forking

1. what is forking?

- A fork is a copy of a repository. Forking a repository allows you to freely 
experiment with changes without affecting the original project.

- Forking is very similar to branching

-- Branching occurs in the same repo. Forking occurs across GitHub accounts

- Branching is part of Git. Forking is part of GitHub.

- you create a pull requests to merge changes back into the original Github project.

- forking can be called pull requst from one github account to another.


## When do you fork?

- Most common in open source projects
-- Anyone can make a copy of the repository and make improvements
-- They create pull requests to ask to incorporate their improvements
-- The project owner can decide whether they want those changes
- It's also used for non-public projects
-- Team members fork and create pull requests

## How do you fork?

1. goto the project you want to fork on github.

2. clcik the **Fork** button.

3. choose your account.

> create a pull request after making the neccessary changes.

4. click the **create pull request** button in github.

5. follow the instructions.

[**exercise**] (C:\Users\PremkumarMogi\git-practice\sample\Exercise+14+Forking)

# Documentation and next steps

**Covers**

- Documentation systems that you can use with Git, GitHub, GitBook, Jekyll, Sphinx, AsciiDoctor

- How to keep learning Git and GitHub.


## Documentation

- You may be wondering how to create documentation from the files you work 
with in Git

- This lesson talks about several different options

## GitBook

- Like GitHub, but designed for documentation
- Nice look-and-feel
- Can choose your own domain
- Free for 2 users, one public space, one private space

## Tools other than version control
- Host files in GitHub
- Webmaster uses local copy of repo for files
- Runs scripts to turn into HTML
- Markdown: Jekyll
- ReStructured Text: Sphinx
- AsciiDoc: AsciiDoctor
- Some tools, like ReadMe can automatically pull from GitHub and generate 
documentation.

*this is the end of training*