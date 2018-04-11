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
<<<<<<< HEAD
Commit these changes to our BRANCHES

git checkout master
Switches us back to the master branch. The comment we made has disappeared in
hello_git.cpp. The file goodbye.cpp has disappeared.

git merge goodbye
=======
>>>>>>> goodbye
