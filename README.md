# Custom zsh functions

helper zsh functions written by yours truly to make my (and maybe your) coding life just a little easier. Maybe learn something in the process.

### Scaffold-practice

This one is a quick way to setup the file system in a specified inside the script directory for praticing problems on [HackerRank.com](https://www.hackerrank.com/)
_It took me forever to actually write it with almost all bells and whistles of an actual shell script. always wanted to learn how to create scripts that handle flags as well as arguments. Well, vio la!_

**If you are using zsh or other shells that `source` / `.` the custom scrits, make sure to mention that in your research of the builtin commands you'd like to use!!!**
`read` builtin, for instanse, requires a coprocess if `source`d or a completely different syntax for displaying a prompt to the user in the terminal and saving to a variable.

### git-lc

Runs `git add . -v` and 'git commit -m ${message}`. It now has the `-h` flag to show usage and tests for existance of the message.

Usage: git-lc [-flags] "commit message"
git-lc - add all files and commit locally with a meassage
"commit message" - required, the message assigned to the commit
[-flags]:
-h prints out this message

### git-up

In addition to the commands enclosed in **git-lc** also has the ability to push changes on the current local branch to a remote named 'origin' (just the name I always use 99% of the time) either to the identically named remote branch (with a -s flag) or to a new branch.

By default, it takes 2 arguments `[remote-branch-name] "commit message"` adds all files, creates a new commit with the specified message, if there are new changes on the current local branch, and pushes them to the provided branch. If the specified branch doesn't exist on the remote - the script creates one.

Usage: `$ git-up [-flags] <remote-branch-name> "commit message"` \n
git-up - add all files, commit with a meassage and push the current branch to a <remote-branch-name>
"commit message" - message assigned to the commit
[-flags]:
-h prints out this message
-p Previous. Uses the last commit; "commit message" argument is skipped
-s Same (branches). Pushes changes to the branch with the same name as the current one. <remote-branch-name> ignored
