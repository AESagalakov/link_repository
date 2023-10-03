# USEFUL COMMANDs for git
This file describes how to connect local repository with remote one.
1. Go to the remote repository page, select the SSH type and copy the URL.
2. Open a console, navigate to your local repository directory and type: **git remote add**. The command needs to pass two parameters: the name of the remote repository and its URL. Use the word _origin_ as the name. And you copied the URL from the remote repository page.
3. Make sure the repositories are linked with command: **git remote -v**
4. Push changes to a remote repository type:  **git push**. The first time this command needs to be called with the _-u_ flag and the parameters _origin_ (the name of the remote repository) and _main_ or _master_ (the name of the current branch). The _-u_ flag will link the local branch to the remote branch of the same name. In the future, when working with a remote repository, the _-u_ flag can be omitted and just write **git push**.


#hash

The **hash** is the main commit identifier and allows you to find out its author, date and contents of the committed files.
Git converts information about commits using the SHA-1 algorithm and for each of them calculates a unique identifier - a hash.
All hashes, as well as the hash table → information about the commit, Git stores in the .git folder.


#log

You can call not only the full _log_, but also the abbreviated one - this is done with the **git log --oneline** command.
In the abbreviated _log_, abbreviated hashes are displayed - they can be used in the same way as full hashes.


#HEAD

Among other files in the .git folder there is a _HEAD_ service file. It points to the most recent commit.
Instead of the hash of the last commit, you can write the word HEAD - Git will understand you.


#status

* The untracked status marks a file that Git knows about, but doesn't track changes to. This status is the opposite of tracked, which includes all files tracked by Git.
* The file becomes staged after *git add* is executed.
* The modified status means that the file has been modified.
* Most files in projects go through the following cycle: “changed” → “added to the commit list” → “committed” → “changed” → and so on.


#commits rules

* the commit message is easy to read;
* it is informative;
* All messages are in the same style.

#Working with branches

Cloning someone else's repository
**git clone** _git@github.com:project.git_ - clone the repository with the URL project.git from account to my local computer.

#Creating branches

**git branch** _feature/the-finest-branch_ - create a branch from the current one with the name feature/the-finest-branch;
**git checkout -b** _feature/the-finest-branch_ - create a branch feature/the-finest-branch and immediately switch to it.

#Branch navigation

**git branch** - show what branches there are in the repository and which one I’m in (the current branch will be marked with a *);
**git branch -a** - show all known branches, both local (in the local repository) and remote (in origin, or on GitHub).
**git checkout** _feature/br_ - switch to the feature/br branch.

#Branch comparison

**git diff** _main_ _HEAD_ - show the difference between the main branch and the pointer to HEAD;
**git diff** _HEAD~2_ _HEAD_ - show the difference between the commit that was two commits ago and the current one.

#Removing branches

**git branch -d** _br-name_ - delete the br-name branch, but only if it is part of main;
**git branch -D** _br-name_ - Delete the br-name branch, even if it is not merged into main.

#Merging branches

**git merge** _main_ - merge the main branch with the current active branch.

#Working with a remote repository

**git push -u origin** _my-branch_ - push the new branch my-branch to the remote repository and link the local branch with the remote one, so that with additional commits you can simply write git push without -u;
**git push** _my-branch_ - push additional changes to the my-branch branch that already exists in the remote repository;
**git pull** - pull changes to the current branch from a remote repository.

#Adding changes to the latest commit

**git commit --amend --no-edit** - add changes to the last commit and leave the message the same;
**git commit --amend -m** _"New message"_ - change the message for the last commit to New message.

#Rolling back files and commits

**git restore --staged** _hello.txt_ — move the hello.txt file from the staged state back to untracked or modified;
**git restore** _hello.txt_ - return the hello.txt file to the latest version that was saved via git commit or git add;
**git reset --hard** _b576d89_ - remove all uncommitted changes from staging and the “working area” up to the specified commit.

#View changes

**git diff** - show changes in the “working area”, that is, in modified files;
**git diff** _a9928ab_ _11bada1_ - print the difference between two commits;
**git diff --staged** - show changes that have been added to staged files.
