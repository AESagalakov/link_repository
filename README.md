# link_repository
This file describes how to connect local repository with remote one.
1. Go to the remote repository page, select the SSH type and copy the URL.
2. Open a console, navigate to your local repository directory and type: **git remote add**. The command needs to pass two parameters: the name of the remote repository and its URL. Use the word _origin_ as the name. And you copied the URL from the remote repository page.
3. Make sure the repositories are linked with command: **git remote -v**
4. Push changes to a remote repository type:  **git push**. The first time this command needs to be called with the _-u_ flag and the parameters _origin_ (the name of the remote repository) and _main_ or _master_ (the name of the current branch). The _-u_ flag will link the local branch to the remote branch of the same name. In the future, when working with a remote repository, the _-u_ flag can be omitted and just write **git push**.

#hash

The **hash** is the main commit identifier and allows you to find out its author, date and contents of the committed files.
Git converts information about commits using the SHA-1 algorithm and for each of them calculates a unique identifier - a hash.
All hashes, as well as the hash table → information about the commit, Git stores in the .git folder.