# Creating a Repository (`git init`)

**Key terms/commands**

* **Repository (repo)**: a repo tracks all the changes you made in that directory. In tangible form, it is a `.git/` folder that lives inside the directory.

* **git init**: creates a repository (the `.git/` folder).


## Create a directory call `workdir` in your home directory for this tutorial

```bash
mkdir ~/workdir
cd ~/workdir
```

## Create a repository, where git store versions of your file

Create a repository within a folder

```bash
git init
```

Check that a hidden folder `.git` has been created

```bash
ls -a
```

Check the status of git

```bash
git status
```

> The status tells you have nothing to commit (last line).

***
**You now have a repository (i.e., a `.git/` folder) within a directory that you want to track!**