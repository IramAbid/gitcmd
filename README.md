# gitcmd
This repository contains usage of important git commands used during development.

# git init : Initialized empty Git repository 

# git config --local user.name "IramAbid" : Sets the user name only for the current repository. 

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

