# gitcmd

This repository contains usage of important git commands used during development.

# Setup and Config

# git config 

git config --local user.name "IramAbid" : Sets the user name only for the current repository. 

git config --local user.email "irama4633@gmail.com" : Sets the user email only for the current repository. 

git config --global user.name "IramAbid" : Sets the user name for all repositories for the current user. 

git config --system user.name "IramAbid" : Sets the user name for all users on the system (requires admin/root privileges)

git help --all or -a: Print all the available commands on the standard output.

git help --all --no-external-commands: exclude the listing of external "git-*" commands found in the $PATH

# git help 

git help --all --no-verbose: When used with --all, print description for all recognized commands. This is the default.

git help --all -no-aliaises: When used with --all, exclude the listing of configured aliases.

git help -c or --config: List all available configuration variables. This is a short summary of the list in git-config

git help -g or --guides: Print a list of the Git concept guides on the standard output.

git help --user-interfaces: Print a list of the repository, command and file interfaces documentation on the standard output.


# Getting and Creating Projects

git init : Initialized empty Git repository 

git clone "github repository url"
eg: git clone "https://github.com/IramAbid/gitcmd.git" : Clone a repository into a new directory  (some flags: --local --shared)

# Basic Snapshotting

# git add <file>: Add file contents to the index. 

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

# git diff 

git diff : Shows the changes in the working directory that are not yet staged for the next commit

git diff : Shows the changes in the working directory that are not yet staged for the next commit

git diff --staged or git diff --cached: Shows the changes between the staging area and the last commit

git diff <commit>: changes between working directory and a specific commit

git diff <commit1> <commit2>: changes between 2 commits


# git log : give the details of the commit (Author, Date, Commit Hash)

# git notes

git notes add -m "message": add note to most recent commit

git notes add -f -m "message": to overwrite on added note to recent commit

git notes show : show the recent note to most recent commit

git notes list: list notes 

git notes remove: Remove a Note from the Most Recent Commit

git notes add -m "This is a note" <commit_hash>

git notes show <commit_hash>

git notes remove <commit_hash>

# git restore

git restore README.md : restore file to last commit

git restore . : restore all files to last commit

git restore --staged README.md: it will restore from the staging area

git restore --staged . : Restore All Files from Staging Area

git restore --source=<commit_hash> <file>: Restore a File to a Specific Commit eg: 7b09e30

# git reset - Reset current HEAD to the specified state

git reset HEAD README.md: Unstages the changes in the staging area but keeps the changes in the working directory.

git reset --hard <commit_hash> Revert to a Previous Commit and Discard Changes (hard reset)

git reset --soft <commit_hash> Revert to a Previous Commit (mixed reset)

# git rm: Remove files from the working tree and from the index

git rm <file>: Removes a file from the working directory and stages the removal for the next commit.

git rm --cached <file>: Removes a file from the staging area but leaves it in the working directory.

git rm -f <file>: Forces the removal of a file that has been modified or staged.

git rm *.log: Removes multiple files matching a pattern (e.g., all .log files).

-n
--dry-run
Don’t actually remove any file(s). Instead, just show if they exist in the index and would otherwise be removed by the command.

-r
Allow recursive removal when a leading directory name is given.

# git mv: Move or rename a file, a directory, or a symlink(A symlink (also called a symbolic link) is a type of file in Linux that points to another file or a folder on your computer.)

Move or rename a file, directory, or symlink.

git mv [-v] [-f] [-n] [-k] <source> <destination> : it renames <source>, which must exist and be either a file, symlink or directory, to <destination>
git mv [-v] [-f] [-n] [-k] <source> ... <destination-directory>: the last argument has to be an existing directory; the given sources will be moved into this directory.

-f
--force
Force renaming or moving of a file even if the <destination> exists.

-k
Skip move or rename actions which would lead to an error condition. An error happens when a source is neither existing nor controlled by Git, or when it would overwrite an existing file unless -f is given.

-n
--dry-run
Do nothing; only show what would happen

-v
--verbose
Report the names of files as they are moved.

eg: git mv -v  test2.txt testfile.txt  :change name of test2.txt to testfile.txt
eg:  git mv test2.txt directory/ : Move the test2.txt to directory

# Branching and Merging

# git branch

git branch branchName : create new branch

git branch -a : show all branches

git branch (-m | -M) [<oldbranch>] <newbranch>

git branch (-c | -C) [<oldbranch>] <newbranch>

git branch (-M | -m) : <oldbranch> will be renamed to <newbranch>. If <oldbranch> had a corresponding reflog, it is renamed to match <newbranch> and a reflog entry is created to remember the branch renaming. If <newbranch> exists, -M must be used to force the rename to happen.

-m
--move
Move/rename a branch, together with its config and reflog.

-M
Shortcut for --move --force.

-c

--copy

Copy a branch, together with its config and reflog.

-C

Shortcut for --copy --force.



# git checkout

git checkout -b branchname : creates a branch and switch to it

git checkout branchname : switch from current to branchname

git checkout -- README.md : restore a specific file to its state in the last commit


# git switch 

git switch [<options>] [--no-guess] <branch>
eg: git switch feature-branch

git switch [<options>] --detach [<start-point>] : Switching to a Specific Commit (Detached HEAD)
eg: git switch --detach 1a2b3c4d

This command switches to a specific commit, detaching the HEAD.

git switch [<options>] (-c|-C) <new-branch> [<start-point>] : To create a new branch and switch to it, use:
-c creates a new branch.
-C creates a new branch or resets it if it already exists.
Example: git switch -c new-feature-branch : This command creates a new branch named new-feature-branch and switches to it.
Example with start-point: git switch -c new-feature-branch 1a2b3c4d. This command creates a new branch named new-feature-branch at the specified commit 1a2b3c4d and switches to it.

git switch [<options>] --orphan <new-branch> : To create an orphan branch, use:
Example: git switch --orphan new-orphan-branch
This command creates a new orphan branch named new-orphan-branch. An orphan branch starts with no commit history.

# git merge command is used to combine multiple branches into one

1. Basic merge 

git merge <branch_name>: To merge a branch into your current branch

2. Fast-Forward Merge

git merge feature-branch : If there are no conflicts and the branches haven't diverged, this will be a fast-forward merge.


3. Three-Way Merge
If there are commits on both branches since their divergence, Git will perform a three-way merge.

git merge feature-branch: This command will combine the histories of both branches and create a new merge commit.

4. Merging with a Commit Message
To provide a custom commit message for the merge commit:

git merge -m "Your custom merge message" <branch_name>

Example: git merge -m "Merging feature-branch into main" feature-branch

5. Abort a Merge
If you encounter conflicts and decide to abort the merge:

git merge --abort: This command stops the merge process and returns the branch to its previous state.


# git mergetool

git config --global merge.tool kdiff3

git mergetool --tool=<tool_name>

# git log

1. Basic Log
To view the commit history:

git log: This command shows the list of commits in the repository in reverse chronological order (most recent commits first).

2. Log with One Line Per Commit

To view a simplified log with one line per commit:
git log --oneline: This command displays each commit on a single line, showing the abbreviated commit hash and commit message.

3. Log with Graph
To view the log with a graphical representation of the branch history:
git log --graph: This command adds a graphical representation of the commit history.

4. Log with Author Information

To view the commit history with author information:
git log --author=<author_name>
Example: git log --author="John Doe"
This command shows commits made by "John Doe".

5. Log with Date Range
To view commits made within a specific date range:

git log --since=<date> --until=<date>
Example: git log --since="2024-01-01" --until="2024-06-21"
This command shows commits made between January 1, 2024, and June 1, 2024.

6. Log with Patch
To view the log with the changes (diffs) introduced in each commit:

git log -p: This command displays the diffs for each commit in the log.

# The git stash command is used to save the changes in working directory temporarily so we can work on something else and then come back and reapply the changes later

1. Stash Your Changes
To stash your changes:

git stash
This command saves local modifications and reverts the working directory to match the HEAD commit.

2. List Stashes


git stash list: This command shows a list of all stashed changes.

3. Apply Stash
To reapply the latest stashed changes:

git stash apply
This command reapplies the latest stash to  working directory. 

If want to apply a specific stash, use the stash reference from git stash list:
git stash apply stash@{<index>}
Example: git stash apply stash@{0}

4. Pop Stash

To apply the latest stash and remove it from the stash list:
git stash pop: This command reapplies the latest stash and then removes it from the stash list. we can also specify a particular stash to pop:
git stash pop stash@{<index>}
Example: git stash pop stash@{0}

5. Drop Stash
To remove a stash from the list without applying it:
git stash drop stash@{<index>}

Example:git stash drop stash@{0}
To drop the latest stash:

git stash drop

6. Clear All Stashes
To remove all stashes:
git stash clear

# git tag :  is used to create, list, delete, and manage tags in Git. Tags are used to mark specific points in a repository’s history

1. List Tags:

git tag
2. Create a Lightweight Tag:

git tag v1.0
3. Create an Annotated Tag:

git tag -a v1.0 -m "Version 1.0 release"

4. Tagging a Specific Commit:

git tag v1.0 abc1234

5. Push All Tags to Remote Repository:

git push origin --tags

6. Push a Specific Tag:

git push origin v1.0

7. Delete a Tag Locally:

git tag -d v1.0

8. Delete a Tag from Remote Repository:

git push origin --delete v1.0

# git worktree : Manage multiple working trees attached to the same repository.

1. Add a New Worktree

To create a new worktree:
git worktree add <path> <branch>
Example:git worktree add ../new-feature-branch new-feature
This command creates a new worktree at the specified path and checks out the specified branch.

2. List Worktrees

To list all the worktrees associated with the repository:
git worktree list
This command shows the paths and branches of all existing worktrees.

3. Remove a Worktree
To remove a worktree:
git worktree remove <path>
Example:

git worktree remove ../new-feature-branch
This command removes the specified worktree. Note that the worktree must be clean (no uncommitted changes) before it can be removed.

4. Prune Worktrees
To clean up worktrees that are no longer accessible:

git worktree prune
This command removes any references to worktrees that no longer exist.

# git fetch:It is used to download commits, files, and refs from a remote repository into your local repository. It updates remote-tracking branches but does not modify working directory or current branch.


1. Fetch from All Remotes
To fetch updates from all remotes:

git fetch --all
This command retrieves updates from all configured remote repositories.

2. Fetch from a Specific Remote
To fetch updates from a specific remote:

git fetch <remote>
Example:

git fetch origin
This command fetches updates from the origin remote.

3. Fetch Specific Branches
To fetch a specific branch from a remote:

git fetch <remote> <branch>
Example:

git fetch origin main
This command fetches the main branch from the origin remote.

4. Prune Deleted References
To prune deleted references on the remote while fetching:

git fetch --prune
This command removes any remote-tracking references that no longer exist on the remote.

5. Fetch and Rebase
To fetch updates and rebase your current branch onto the fetched branch:

git fetch <remote> <branch> && git rebase <remote>/<branch>

Example: git fetch origin main && git rebase origin/main
This command fetches the main branch from the origin remote and rebases your current branch onto origin/main.

# git pull: This command combines git fetch (which downloads commits, files, and refs from a remote repository) with git merge (which integrates the fetched changes into your current branch).

git pull origin

1. Push to the Default Remote Repository
To push your changes to the default remote repository (usually named origin):

git push: This command pushes all local commits that are not yet in the remote repository.

2. Push to a Specific Remote and Branch
To push changes to a specific remote repository and branch:

git push <remote_name> <branch_name>
Example: git push origin main
This command pushes the local changes from the main branch to the origin remote repository.

3. Pushing Tags
To push tags to the remote repository:

git push --tags
This command pushes all local tags to the remote repository.

4. Force Pushing
In some cases, you might need to force push to overwrite remote changes (use with caution):

git push --force
5. Pushing Specific Commits
To push specific commits instead of all local changes:

git push <remote_name> <commit_hash>:<branch_name>
Example: git push origin abc1234:main
This command pushes the specific commit abc1234 to the main branch of the origin remote.

# git remote command is used to manage the set of tracked repositories (remotes) for local repository. It allows you to add, remove, and modify remotes.


1. List All Remotes
To list all remote repositories associated with local repository:


git remote -v
This command shows the names of all remotes and their URLs.

2. Add a New Remote
To add a new remote repository:

git remote add <name> <url>
Example:

git remote add origin https://github.com/user/repo.git
This command adds a new remote named origin with the specified URL.

3. Remove a Remote
To remove a remote repository:

git remote remove <name>
Example:

git remote remove origin
This command removes the remote named origin.

4. Rename a Remote
To rename a remote repository:

git remote rename <old_name> <new_name>
Example:

git remote rename origin upstream
This command renames the remote from origin to upstream.

5. Show Remote Information
To show detailed information about a remote:

git remote show <name>
Example:

git remote show origin

# git submodule

The git submodule command is used to manage external repositories embedded within main repository. These external repositories, called submodules, are often used to include dependencies or libraries within a project.

1. Add a Submodule
To add a submodule to your repository:

git submodule add <repository_url> <path>
Example:

git submodule add https://github.com/user/library.git libs/library
This command adds the repository at the specified URL as a submodule located in the libs/library directory of your project.

2. Initialize and Update Submodules
To initialize and fetch data for a submodule:

git submodule update --init
To initialize and update all submodules recursively:

git submodule update --init --recursive
3. Cloning a Repository with Submodules
When cloning a repository that contains submodules, use:

git clone --recurse-submodules <repository_url>
Example:

git clone --recurse-submodules https://github.com/user/project.git
This command clones the repository and initializes, fetches, and checks out all submodules.

4. Updating Submodules
To update submodules to the latest commit in their respective repositories:

git submodule update --remote
To update all submodules recursively:

git submodule update --remote --recursive
5. Removing a Submodule
To remove a submodule, you need to:

1.Delete the relevant section from the .gitmodules file.

2.Delete the relevant section from .git/config.

3.run
git rm --cached <path_to_submodule>
rm -rf <path_to_submodule>

4.Commit the changes:
git commit -m "Removed submodule <name>"

# git show command is used to display various types of objects in Git. Typically, it is used to show the details of a specific commit, including the commit message, the author, and the changes made (diff). It can also be used to show the contents of tags, trees, and blobs.


1. Show a Specific Commit
To display the details of a specific commit, you need the commit hash:

git show <commit_hash>
Example:

git show abc1234
This command shows the commit message, author information, and the diff of the commit with hash abc1234.

2. Show the Latest Commit
To display the details of the latest commit:


git show
This command shows the most recent commit on the current branch.

3. Show a Specific File from a Commit
To display the details of a specific file from a particular commit:

git show <commit_hash>:<file_path>
Example:

git show abc1234:README.md
This command shows the contents of the README.md file as it was in the commit with hash abc1234.

4. Show a Tag
To display the details of a tag:

git show <tag_name>

# git range-diff command is used to compare two ranges of commits. It shows the differences between the commits in the two ranges, allowing you to see what has changed between them.

1. Basic Usage
To compare two ranges of commits:

git range-diff <range1> <range2>
Example:

git range-diff origin/main...feature-branch1 origin/main...feature-branch2
This command compares the changes between the origin/main branch and feature-branch1 with the changes between origin/main and feature-branch2.

2. Compare Two Branches
To compare the commit history between two branches:

git range-diff <branch1> <branch2>
Exa

git range-diff feature-branch1 feature-branch2
This command shows the differences between the commit history of feature-branch1 and feature-branch2.

3. Compare a Range and a Commit
To compare a range of commits to a single commit:

git range-diff <range> <commit>
Example:

git range-diff origin/main...feature-branch abc1234
This command compares the changes between origin/main and feature-branch with the changes in commit abc1234.

# git shortlog command is used to summarize git log output, typically grouping the commits by author and optionally by the commit message. It provides a concise view of the contributions to a project, making it easier to see who contributed and how many commits they made.


1. Basic Usage
To view a summary of commits grouped by author:rest

git shortlog
This command shows a list of authors and the commits they've made.

2. Group by Commit Messages
To group the commits by author and show commit messages:

git shortlog -n -s
-n sorts the output by the number of commits per author.
-s displays the number of commits per author.
3. Specify a Range

To view the shortlog for a specific range of commits:
git shortlog <range>
Example:

git shortlog HEAD~10..HEAD
This command shows the shortlog for the last 10 commits.

4. Show Commit Messages
To include the commit messages in the shortlog output:

git shortlog -n
This command shows the commits grouped by author with commit messages.

5. Format the Output
To format the output in a specific way, use:

git shortlog --format='%h %s'
%h is the abbreviated commit hash.
%s is the commit subject.

# git describe

git describe
git describe <commit>
git describe abc1234
git describe --tags

# git apply

The git apply command is used to apply a patch to files and/or the index. It is useful for applying changes created by git diff or patches shared between team members. It allows you to apply changes without creating a commit, giving you the flexibility to review and test the changes first.

git apply <patchfile>

git diff --cached > fix_bug.patch
# git cherry-pick <commit-hash>

The git cherry-pick command is used to apply the changes introduced by an existing commit onto the current branch. This is particularly useful when you want to apply a specific commit from one branch to another without merging the entire branch.

# rebase : The git rebase command is used to integrate changes from one branch into another. It helps to maintain a clean and linear project history by applying commits from one branch on top of another. Rebasing can be used to move or combine commits to streamline the history of your repository.

# git revert <commit-hash>: The git revert command is used to create a new commit that undoes the changes made by a previous commit. Unlike git reset, which alters the commit history, git revert maintains the history and adds a new commit to reverse the changes. This is useful when need to undo changes but keep the history intact.

