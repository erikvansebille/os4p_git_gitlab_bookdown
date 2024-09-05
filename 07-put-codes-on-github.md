# 7- Putting codes on Github

**Key terms/commands:**

* **git push**: upload your commits to a remote repository (like GitHub!)

## Push an existing repository from your local computer
Go back to the local directory, workdir that we made in previous sections.


```
cd ~/workdir
```

Add the github repo you just made as a remote repository that you want to push your data to.

* **Replace** your_username with your github username

```{bash}
git remote add origin https://git.science.uu.nl/your_username/workdir.git
```

Check what is listed as your remote repository now.
```
git remote -v
```

Push your local repository to your GitLab repository.

```
git push –u origin master
```

***
**Your code is now available on GitLab!**