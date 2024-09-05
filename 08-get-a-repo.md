# 8- Getting a repository from GitLab (fork & `git clone`)

**Key terms/commands:**

* **Clone**: the concept of a "clone" just means to copy the entire repository.

* **Fork**: within the context of GitLab, to fork is to copy someone's GitLab repository and put it in your GitLab account. Under the hood, it is just cloning their repository.

* **git clone**: copies (download) a remote repo onto your local computer.

## Fork a repository (remote -> remote)

**Fork** [this repository](https://git.science.uu.nl/os4p-2023/git-tutorial) that hosts this bookdown you are reading into your GitLab.

* Go to https://git.science.uu.nl/os4p-2023/git-tutorial
* Click the **Fork** icon near the top right corner
* ...It will take a little while to load...
* You should be redirected to a copy of the same repository in YOUR GitLab account

## Cloning a repository (remote -> local)

**Clone** YOUR git_tutorial repository onto your local computer:

git clone https://git.science.uu.nl/your_username/git-tutorial ~/git-tutorial

***
**You have cloned someone else's repository! This is often how collaboration starts through GitLab.**