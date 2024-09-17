# 10 - Conflicts

**Key terms/commands:**

* **Conflict**: when the same portion of a file is edited, it creates a conflict that has to be manually resolved before it can be merged together. This often is the reason why you cannot `push` a commit.

## Create a conflict

Go into your fake collaborator's folder and add a line to `foo.txt`.

```
cd ~/workdir_fake_collab
echo fake_colab >> foo.txt
```

Add & commit your change.

```
git add foo.txt
git commit -m "Add fake collab line to foo.txt"
```

Push the change to the remote repository

```
git push origin main
```

Now go into the original `workdir` and add a different line to `foo.txt`

```
cd ~/workdir
echo real_me >> foo.txt
```

Add and commit the change

```
git add foo.txt
git commit -m "Add real me line to foo.txt"
```

Try to push it, and you should get an error

```
git push origin main
```


* Note that if you have get an error from git, it tries to give you hints on how to fix the error.
* It tells you that there is something in the remote repo. It suggests that you should integrate changes first by using `git pull`.

## Resolving a conflict

Pull the changes your fake collaborator made in the remote server

```
git pull
```


The output shows there is a **Conflict Message**!

When this situation happens, Git will merge the conflicting changes into the file in question (i.e., `foo.txt`), and tells you that manual intervention is needed.


### Look at the file with conflict and understanding the conflict message

```
cat foo.txt
```

* The conflicted portion of the file is indicated by `<<<<<<<` and `=======`
  + Changes you made in your **local copy** is between `<<<<<<< HEAD` and `=======`
  + Changes from the **remote copy** is between `=======` and `>>>>>>> <commit identifier>`

Manually edit the file using a text editor (here we use `nano`) to the state where you want the file to be.

```
nano foo.txt
```

Make the resulting file look like this:

```
printf "hello\nworld\nwhales are good\n" > foo.txt
```

Add and commit the edited file

```
git add foo.txt
git commit -m "Merge changes from Github, whales are good"
```

Push your changes to the remote repo

```
git push
```

Now your fake collaborator can `pull` from the remote repo again

```
cd ~/workdir_fake_collab
git pull
```

Both you and your fake collaborator now have the updated `foo.txt`. Check by printing the file

```
cat foo.txt
```

## Tips to prevent conflicts

* Always fetch/merge (or pull) before making changes locally
* Use **branches** (see upcoming chapter)
* Commit often (so people can pull your changes frequently as well)
* Have smaller files, so it is less likely for multiple people to edit the same file.
* Communicate often with your collaborators :)

***
**You have now resolved conflicted commits on git. Follow the tips above and hopefully you don't have to do this often.**
