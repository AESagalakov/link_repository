# link_repository
This file describes how to connect local repository with remote repository.
1. Go to the remote repository page, select the SSH type and copy the URL.
2. Open a console, navigate to your local repository directory and type: **git remote add**. The command needs to pass two parameters: the name of the remote repository and its URL. Use the word _origin_ as the name. And you copied the URL from the remote repository page.
3. Make sure the repositories are linked with command: **git remote -v**
4. Push changes to a remote repository type:  **git push**. The first time this command needs to be called with the _-u_ flag and the parameters _origin_ (the name of the remote repository) and _main_ or _master_ (the name of the current branch). The _-u_ flag will link the local branch to the remote branch of the same name. In the future, when working with a remote repository, the _-u_ flag can be omitted and just write **git push**.
