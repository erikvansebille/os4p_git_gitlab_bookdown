# Glossary

***
**General Terms**

* **Repository (repo)**: a local repository tracks all the changes you made in that directory. In tangible form, it is a `.git/` folder that lives inside the directory.

* **Branch**: independent line of development typically used to develop new features without disturbing the rest of the repository. The default branch is called the **"Master"** branch.

* **Clone**: the concept of a "clone" just means to copy the entire repository.

* **Conflict**: when the same portion of a file is edited, it creates a conflict that has to be manually resolved before it can be merged together. This often is the reason why you cannot `push` a commit.

* **Commits**: a "commit" adds your latest changes to your repository. If a change is not committed, Git would not recognize the change.

* **Fork**: within the context of GitHub, to fork is to copy someone's GitHub repository and put it in your GitHub account. Under the hood, it is just cloning their repository.

* **HEAD**: refers to the latest commit in the branch you are at. By default, you are the most recent commit of the master branch. When you `git checkout different_branch`, HEAD is now at the most recent commit of `different_branch`. If you are not at the most recent commit of a branch (e.g., you `git checkout` a previous commit), you are now in a `detached HEAD`.
  + Note that changes made in a **detached HEAD** situation would not be recorded once you `git checkout` back to the HEAD of the branch or to a different branch.


***
**Git Commands**

* **git add**: tells git which file's changes you want to document. Formally, this is called adding a file to the "index/staging area".

* **git branch**: handles the creation, renaming and deletion of branches. Note that `git checkout` is used to switch between branches.

* **git checkout**: revert (i.e., checkout) a file to a previous state. You can also checkout your entire folder, but it is potentially a dangerous move (puts you in a detached HEAD).

* **git clone**: copies (download) a remote repo onto your local computer.

* **git commit**: tells git to document the changes you specified using `git add` (i.e., the files in the staging area), with an accompanying **commit message** that you **have to provide** to explain what changes were made.

* **git diff**: shows the difference between current state of a file/repository with a commit.

* **git fetch**: fetches the changes that is in your remote repository GitHub. This command download the changes into the `.git/` folder so you can compare changes to your local files, but it does not actually modify your files (i.e., files outside of the `.git/` folder).

* **git init**: creates a repository (the `.git/` folder).

* **git merge**: implement the changes you have *fetched* into your local files.

* **git pull**: `git fetch` + `git merge`. However, it is recommended that you fetch first, check that you want to implement the changes, and then merge.

* **git push**: upload your commits to a remote repository (like GitHub!)
