# Branching (`git branch`)

**Key terms/command**

* **Branch**: independent line of development typically used to develop new features without disturbing the rest of the repository. The default branch is called the **"Master"** branch.

* **git branch**: handles the creation, renaming and deletion of branches. Note that `git checkout` is used to switch between branches.

Want to create or edit a new script or function but not ready to make it live (available to everyone) just yet?

Create a new branch!

![](img/git_branch_merge.png)


## Check what branch you're on

If you've never changed a branch. You're likely using the `master` or main branch.

It's always a good idea to check what branch you're using:

```
git branch
```

The one marked with the `*` is the name of branch that you're currently on, also known as the active branch.


## Create new branch

To create a new branch, we can enter:

```
git branch <branch_name>
```

For example, if we want to make a test a new function on a new branch, we can create the new branch by entering:
```
git branch cool_new_function
```

To make sure the branch exists, we can enter:
```
git branch
```

<br>

## Switch between branches (`git checkout`)

To switch to the new branch, use `git checkout <branch_name>`

Example:
```
git checkout cool_new_function
```

Let's check that we actually switched.
```
git branch
```

Notice that the * is now on cool_new_function.

Note: You can also create and switch to a branch in one command using:

```
git checkout -b <branch_name>
```

Now that you're in your new branch, you can make, edit, and commit script(s) as you want without affecting anything on the master branch.

```
touch cool_new_function.sh
git add cool_new_function.sh
git commit -m "added cool new function"
ls
```

## Merge branch

Ready to make the modification available to everyone? Let's merge the change back to the master branch.

First, we have to switch back to the master branch `git checkout master` and then merge the commit `git merge <branch_name>`

```
git checkout master
ls
```

Notice that there is no cool_new_function.sh file in the master branch.

```
git merge cool_new_function
ls
```

The cool_new_function.sh file is now available on the master branch after merging.

## Delete a branch

Done using a branch or created one by accident?

Delete the branch by entering:

```
git branch -d <branch_name>
```

```
git branch -d cool_new_function
```

```
git branch
```

## BONUS (Advanced x 2 topic) - detached HEAD

Remember the previous chapter mentioned a concept about 'detached HEAD'? Now you have tried branching, you could understand a bit more how detached HEAD can occur, and how branching can help preventing commit loss.

### Purposely enter a detached HEAD and create a commit
```
git checkout HEAD~2
```

```
touch loss.txt
git add loss.txt
git commit -m "Adding loss.txt while in detached HEAD"
```

### Return to master branch
```
git checkout master
```

> The output would warn you that you are "leaving 1 commit behind".

### You are now back in the 'master' branch, and `loss.txt` is gone (check with `ls`)

Luckily, the output message actually tells you how to recover those changes (for now, before Git eventually deletes it).
```
git branch recover_loss_branch <commit identifier>
```

Now if you switch to that branch you just created (use `git checkout`), you will see `loss.txt`.


***
**You have started using branches in Git!**