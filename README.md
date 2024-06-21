# gitcmd
This repository contains usage of important git commands used during development.

# git init : Initialized empty Git repository 

# git config --local user.name "IramAbid" : Sets the user name only for the current repository. 

# git config --local user.email "irama4633@gmail.com" : Sets the user email only for the current repository. 

# git config --global user.name "IramAbid" : Sets the user name for all repositories for the current user. 

# git config --system user.name "IramAbid" : Sets the user name for all users on the system (requires admin/root privileges)

# git help --all or -a: Print all the available commands on the standard output.

# git help --all --no-external-commands: exclude the listing of external "git-*" commands found in the $PATH

# git help --all --no-verbose: When used with --all, print description for all recognized commands. This is the default.

# git help --all -no-aliaises: When used with --all, exclude the listing of configured aliases.

# git help -c or --config: List all available configuration variables. This is a short summary of the list in git-config

# git help -g or --guides: Print a list of the Git concept guides on the standard output.

# git help --user-interfaces: Print a list of the repository, command and file interfaces documentation on the standard output.

# git clone "https://github.com/IramAbid/gitcmd.git" : Clone a repository into a new directory  (possible flags --local --shared)

# git add <file>: Add file contents to the index. 

[--verbose | -v] 
[--dry-run | -n] Don’t actually add the file(s), just show if they exist and/or will be ignored
[--force | -f] Allow adding otherwise ignored files.
[--edit | -e] Open the diff vs. the index in an editor and let the user edit it. After the editor was closed, adjust the hunk headers and apply the patch to the index.

# git status -Show the working tree status

-s
--short
Give the output in the short-format.

-b
--branch
Show the branch and tracking info even in short-format.

--long
Give the output in the long-format. This is the default.

# git diff : Shows the changes in the working directory that are not yet staged for the next commit

# git diff : Shows the changes in the working directory that are not yet staged for the next commit

# git diff --staged or git diff --cached: Shows the changes between the staging area and the last commit

# git diff <commit>: changes between working directory and a specific commit

# git diff <commit1> <commit2>: changes between 2 commits

# git log : give the details of the commit (Author, Date, Commit Hash)

# git notes add -m "message": add note to most recent commit

# git notes add -f -m "message": to overwrite on added note to recent commit

# git notes show : show the recent note to most recent commit

# git notes list: list notes 

# git notes remove: Remove a Note from the Most Recent Commit

# git notes add -m "This is a note" <commit_hash>
# git notes show <commit_hash>
# git notes remove <commit_hash>


# git restore README.md : restore file to last commit
# git restore . : restore all files to last commit


 git restore --staged README.md: it will restore from the staging area

 git restore --staged . : Restore All Files from Staging Area

 git restore --source=<commit_hash> <file>: Restore a File to a Specific Commit eg: 7b09e30

 # git-reset - Reset current HEAD to the specified state

git reset HEAD README.md: Unstages the changes in the staging area but keeps the changes in the working directory.

git reset --hard <commit_hash> Revert to a Previous Commit and Discard Changes (hard reset)
git reset --soft <commit_hash> Revert to a Previous Commit (mixed reset)





