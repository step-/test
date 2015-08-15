## Importing a Git repository using the command line
If [GitHub's import tool](https://help.github.com/articles/importing-from-other-version-control-systems-to-github) is not suitable for your purposes, such as if your existing code is hosted on a private network, then we recommend importing using the command line.

Before you start, make sure you know:

 * Your GitHub user name.
 * The clone URL for the external repository, such as `https://otherhost.com/user/repo.git` or `git://otherhost.org/user/repo.git` (perhaps with a `user@` in front of the `otherhost.org` domain name).

For purposes of demonstration, we'll use:

 * An external account named **extuser**
 * A GitHub personal user account named **ghuser**
 * A GitHub repository named **repo.git**

 # [Create a new repository on GitHub](https://help.github.com/articles/creating-a-new-repository). You'll import your external Git repository to this new repository.
 #  On the command line, make a "bare" clone of the repository using the external clone URL. This creates a full copy of the data, but without a working directory for editing files, and ensures a clean, fresh export of all the old data.
```
git clone --bare https://githost.org/extuser/repo.git
# Makes a bare clone of the external repository in a local directory
```
 # Push the locally cloned repository to GitHub using the "mirror" option, which ensures that all references, such as branches and tags, are copied to the imported repository.
```
cd *repo.git*
git push --mirror https://github.com/ghuser/repo.git
# Pushes the mirror to the new GitHub repository
```
 # Remove the temporary local repository.
```
cd ..
rm -rf repo.git
```

[source](https://help.github.com/articles/importing-a-git-repository-using-the-command-line/)
