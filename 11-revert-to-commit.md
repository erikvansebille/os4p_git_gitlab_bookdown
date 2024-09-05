# Revert to a previous commit (`git checkout`)

**Key terms/commands:**

* **git checkout**: checkout a file means to see how was in a previous commit. You can also checkout your entire folder, but it is potentially a dangerous move (puts you in a detached HEAD; read the end of this chapter). Git checkout is also used for switching branches, but that will be covered in the next chapter.

* **git revert**: revert changes and commit the reverted actions as a record.

## Going back to a specific version of a file (`git checkout`)

Make sure you are in your original `workdir`
```
cd ~/workdir
```

Make some changes to `foo.txt`

```
echo "A whole new world" >> foo.txt
cat foo.txt
```


Let assume we want to go back to a previous version of foo.txt.

**Before going back to a previous state of a file, COMMIT what you have now!**

```
git add foo.txt
git commit -m "Add 'A whole new world' to foo.txt"
```

Recover the `foo.txt` that doesn't have "A whole new world" in it (use HEAD~1 or unique identifier)

```
git checkout HEAD~1 foo.txt
```

Check what is in `foo.txt`

```
cat foo.txt
```

Go back to the state where "A whole new world" is in the file

```
git checkout HEAD foo.txt
cat foo.txt
```

## Going back to an entire commit - Detached HEAD (CAUTION)

If you `git checkout` a previous commit without also specifying a file, you will revert the entire directory to a previous condition

```
git checkout HEAD~1
```

You should see a warning message about being in a **'detached HEAD'**. (Refer to the Glossary section in the Appendix for a brief overview on "HEAD" and "detached HEAD".)

Use `git checkout master` to return to most recent state.

```
git checkout master
```

## BONUS - Detached HEAD

**CAUTION 1**: If you make commits while you are in a detached HEAD, returning to "master" (or any other branch)  means those changes are loss (again, we will talk about branches soon).

A [detached HEAD](https://www.git-tower.com/learn/git/faq/detached-head-when-checkout-commit) means you are not in a branch, and any changes you make will disappear when you switch back to a real branch (e.g., `git checkout master`). More about branching and how to prevent your works from disappearing in the next chapter!

## Reverting back to a past commit (`git revert`)

At some point, you might create a commit (or several commits) that you want to undo.
Perhaps it's a new feature that turns out to be more of a bug, so you want to go back to a stable version of your code.
At the same time, you may want to keep the bad code in your commit history, so that you can refer back to it later to see what went wrong or how you can fix it.

Let's create a bug in our files and commit it.

```
touch bug.txt
echo "Brand new feature, surely nothing wrong here..." >> bug.txt
git add bug.txt
git commit -m "added bug.txt"
```

`HEAD` now has a bug in it, so we are going to undo the last commit (going back to how things were in `HEAD~1`) using `git revert`.

```
git revert --no-commit HEAD
```

```
ls
```

`bug.txt` is no longer in our directory, so the revert worked. Now we can commit.

```
git commit -m "revert 'added bug.txt'"
```

Using the `--no-commit` argument for `git revert` allowed us to check what the result of the revert was before we committed it. If you don't include `--no-commit`, `revert` will go straight to committing the change.
After `--no-commit` we specified which commit we want to undo; in this case it was `HEAD`.

So, we undid a single commit, but what if we wanted to undo several commits?
We can use `revert` with a range of commits.
Let's say we added in three commits that are not good.

```
touch badjoke.txt
echo "In case of fire," >> badjoke.txt
git add badjoke.txt
git commit -m "badjoke 1"
```

```
echo "git commit, git push," >> badjoke.txt
git add badjoke.txt
git commit -m "badjoke 2"
```

```
echo "and git out of there!" >> badjoke.txt
git add badjoke.txt
git commit -m "badjoke 3"
```

```
cat badjoke.txt
```

We want to remove our bad joke, so we use a `git revert` with a range `HEAD~3..`.

```
git revert --no-commit HEAD~3..
```

`HEAD~3..` specifies a range from `HEAD~3` to `HEAD` (the `..` is what indicates it is a range). We are trying to go back to how things were in `HEAD~3`, so when we specify `HEAD~#..` as our range, `HEAD~#` is the commit you would like to go back to.

Don't forget to commit!
```
git commit -m "undo 3 commits to get rid of bad joke"
```


***
**You have now used `checkout` to look at the past version of a file, and `revert` to undo commits!**
