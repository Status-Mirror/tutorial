This is a README saying exactly what I've done to make this a GIT repository.

##################################################
#THE FIRST STEP, COMMIT FILES TO A GIT REPOSITORY#
##################################################

git init
This makes a hidden .git file, which can be seen with "ls -a".

git config --global user.name 'Stuart Morris'
Tags my name to git (possibly for the entire laptop).

git config --global user.email 'sjm630@york.ac.uk'
Tags my email address to git.

git add hello_git.cpp
Adds the file hello_git.cpp to the git repository.

git status
Tells us what's currently in the git repository (and how to remove it), and what
isn't (and how to add it)

git add *.cpp
Adds all files ending in .cpp.

git add .
Adds everything in the current working directory (including things inside
folders)

git commit
This opens a VIM text editor. You must hit i to enter insert mode and start
writing. You exit insert mode by hitting Esc. Then finally, you enter the
command :wq to exit Vim. Now the snapshot of whatever was in the staging area
when you did "git status" has been saved, and the stage is empty once more. The
purpose of this text editor is to add a comment about what you have changed.

git commit -m 'Initial commit'
Achieves the same as above, and commits with the comment "Initial commit" -
usurping VIM.

touch .gitignore
Uses touch (creates a file) to create a hidden file called gitignore. Any
filename which appears in .gitignore will not be included in a "git add ."
command. To ignore a directory, enter /Bad_Folder into .gitignore, to ignore
every file in that directory.

##########
#BRANCHES#
##########

Note that until now, when we have done "git status", it has told us we were in
the master branch.

git branch goodbye
Creates a branch so that we can make our code say hello and goodbye. The branch
will be called goodbye

git checkout goodbye
Moves us to the "goodbye branch". Can be confirmed with a git status.

touch goodbye.cpp
Make a new file while in this branch, also add a comment to hello_git.cpp to
demonstrate a change to a file

git add .
Add everything to the stage

git commit -m 'Hello and Goodbye'
Commit these changes to our BRANCHES

git checkout master
Switches us back to the master branch. The comment we made has disappeared in
hello_git.cpp. The file goodbye.cpp has disappeared.

git merge goodbye
As long as you haven't been making changes in the master branch before you do
the git merge command (like updating a README...), then this command will update
the master branch to use the files from the goodbye branch (e.g. the comment in
hello_git.cpp now appears in

####################################
#USING GITHUB (STARTING REPOSITORY)#
####################################

Log into github.com. At York, your username is sjm630@york.ac.uk, and your
password is 1=X1 (in the usual password notation you use). In the top right hand
corner there is a +. Select this and choose "New repository". Fill in the
document and create your repository. On the next page, there will be a url. For
me: https://github.com/Status-Mirror/tutorial.git

git remote
This command lists the remote repositories we have access to. Currently, we have
none.

git remote add origin https://github.com/Status-Mirror/tutorial.git
This will add this url as a remote location, which it will call "origin" (so
"git remote" will now list origin).

git push -u origin master
Pushes the "master" branch to the remote location "origin"

##################################
#USING GITHUB (UPLOADING CHANGES)#
##################################

touch README.md
GitHub likes its README files to written as .md files. The syntax can be looked
up. For a basic one, let the first line be our header "#MY STUFF", and the next
line can be just plain text "This is my stuff". This is the file we'll add.
