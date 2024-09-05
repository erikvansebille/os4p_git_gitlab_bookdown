# Tracking Changes (`git add & commit`)

The key commands for documenting changes are `git add` and `git commit`.

**Key terms/commands:**

* **Commits**: a "commit" adds your latest changes to your repository. If a change is not committed, Git would not recognize the change.

* **git add**: tells git which file's changes you want to document. Formally, this is called adding a file to the "index/staging area".

* **git commit**: tells git to document the changes you specified using `git add` (i.e., the files in the staging area), with an accompanying **commit message** that you **have to provide** to explain what changes were made.

While the process of adding and then committing seems redundant, overtime it will be apparent why we don't always just commit ALL changes that have been made to your files, and how the 'mandatory' commit message creates a good documentation for your project.

## Adding new files/modification (`git add`)

Make sure you are in the correct directory

```
cd ~/workdir
```

Make a new file `foo.txt`

```
touch foo.txt
```

Check the status
```
git status
```

> The status tells you `foo.txt` is not being tracked, and that you can use `git add` to start tracking it.

**If there are untracked files, we would like to add those files so git will track their changes:**

```
git add foo.txt
```

Check the status again, `foo.txt` should now be ready to get committed (a commit is a revision to your files).

```
git status
```

> The status now tells you there are "Changes to be commited", and `foo.txt` is listed as a new file (in green).

## Saving these changes to the repository (`git commit`)

Commit the file and note the identifier for this commit (e.g., `f22b25e`):

```bash
git commit -m "Add foo.txt to repo"
```

> The output of a commit will tell you what has changes has been commited to the repository. In this example, "1 file was changed". There is 0 insertions or deletions as the file is empty.
> "create mode" means that a file is being added to the repository (first time Git is being told this file exist).

What have we done so far? Let's check the log, which list all the commits made so far.

```
git log
```

> Each commit in the log is identified by a long unique identifier.
> The author (and their email) of this commit is listed
> Lastly, the commit message will appear under the identifier and author.

## PRACTICE - Let's add a line to the file and `add`/`commit` it
Add some text to the file `foo.txt`

```
echo hello >> foo.txt
```

Add & commit your changes to `foo.txt`

```
git add foo.txt
git commit -m "Add hello in foo.txt"
```

> The output tells you that you have added 1 file and there is 1 insertion(+)

Check the status and log again using `git status` and `git log`

##  Notes

* Git does not track an empty directory, so until a directory has a file in it, git would not track it.

* If you want to correct the **most recent** commit message, use `git commit --amend`


***
**You have now used Git to track the file `foo.txt`. You can use `git log` to read what you have done so far in this repository!**
