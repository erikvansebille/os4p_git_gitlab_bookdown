# 7- Putting codes on Github

**Key terms/commands:**

* **git push**: upload your commits to a remote repository (like GitHub!)

## Push an existing repository from your local computer
Go back to the local directory, workdir that we made in previous sections.


```
cd ~/workdir
```

Add the github repo you just made as a remote repository that you want to push your data to.

* **Replace** your_username with your github username (=Solis-ID)

```{bash}
git remote add origin https://git.science.uu.nl/your_username/workdir.git
```

Check what is listed as your remote repository now.
```
git remote -v
```

Push your local repository to your GitLab repository.

```
git push -u origin main
```

**Note** that if you encounter an `error: src refspec main does not match any` error, you may need to first create a commit in your local repository.

```
git add .gitignore
git commit -m "Add .gitignore"
```

Then try to push again.

```
git push -u origin main
```

Further note that if you encounter a problem with authentication, you may want to create and add an SSH-keypair. See [here](https://docs.gitlab.com/ee/user/ssh.html) for a tutorial how to do that on GitLab.

***
**Your code is now available on GitLab!**
