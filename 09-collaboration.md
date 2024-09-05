# 9 - Collaborating (`git fetch & merge (or pull)`)

**Key terms/commands:**

* **git fetch**: fetches the changes that is in your remote repository GitHub. This command download the changes into the `.git/` folder so you can compare changes to your local files, but it does not actually modify your files (i.e., files outside of the `.git/` folder).

* **git merge**: implement the changes you have *fetched* into your local files.

* **git pull**: `git fetch` + `git merge`. However, it is recommended that you fetch first, check that you want to implement the changes, and then merge.


## Setup a fake collaborator, yourself in another directory :)

Clone the **workdir** repo into your local computer but a different folder as if you have a collaborator

```
git clone https://git.science.uu.nl/your_username/workdir.git ~/workdir_fake_collab
```

Let's pretend you are the collaborator, and you will make some changes and push it to GitLab.
Here we go into the collab directory, make a new file `foofoo.txt`, then `add` & `commit` it.

```
cd ~/workdir_fake_collab
touch foofoo.txt
git add foofoo.txt
git commit -m "Add foofoo.txt"
```

Push this change to GitLab

```
git push origin master
```

Lets check what is in the current folder

```
ls
```

Check what is on the workdir repository on GitHub. It should contain `foofoo.txt`

But what about the original `workdir` folder?

```
cd  ~/workdir
ls
```

`foofoo.txt` should be missing. Now let's say you want to check and incorporate the changes your collaborator made in your original folder.

## Implement the changes your fake collaborator made

**fetch** the changes your fake collaborator pushed to GitLab onto your local computer.

```
git fetch
```

NOTE that this does not change the files in your directory. But now you can use check to see what your collaborator has changed

```
git diff master origin/master`
```

If you decided these are changes you want in your local directory (the original `workdir`)

```
git merge
```

## FAQ
* What if `git merge` returns message "Already up to date."
	+ `git merge` implement the changes that were fetched by `git fetch`, so fetch first.
* Will `git fetch` change my stuff?
	+ Fetching does not change your local file until you pull.

## BONUS - What is my remote?
What is your remote?

```
git remote -v
```

Adding a different remote

```
git add remote [name] [url]
```

Changing the URL of the remote (e.g., you change the remote repository)

```
git remote set-url [name] [newurl]
```

## Really collaborating on GitLab

![](img/ch9_collab_fig.png)


Icons made by [Smashicons](https://www.flaticon.com/authors/smashicons), [Dave Gandy](https://www.flaticon.com/authors/dave-gandy), [Iconnice](https://www.flaticon.com/authors/iconnice) from Flaticon.

* **Using pull request (advance)**, useful for collaborating with anyone, including strangers!
	+ **fork** a repository you want to make changes
	+ **git clone** it to your local computer
	+ Make changes, **git add**, **git commit** and **git push** it to your forked remote repo
	+ Make a [Pull Request](https://docs.gitlab.com/ee/user/project/merge_requests/creating_merge_requests.html) in the original repository so the owner can review and decide whether they want to incorporate the changes you made.

* Adding collaborators in your GitHub repository
	+ Click **Manage** and then **Members** in your repository
	+ Click **Invite members** and add them (they need to be on GitLab)


***
**You have now `fetch` and `merge` changes from different people (or yourself on a different computer/folder)!**


