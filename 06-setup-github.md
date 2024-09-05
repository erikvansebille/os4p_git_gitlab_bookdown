# 6- Git ≠ GitLab (≠ GitHub)

Thus far, everything is within your local computer and done using `git`. That is the **version control** portion of git, which is important and powerful. However, what makes git a efficient tool for collaboration is its power to share through remote hosts like **GitLab**.

* GitLab is not the only option, there are other companies that offer free remote hosting, here are a few alternatives like [GitHub](http://github.com) and [Bitbucket](https://bitbucket.org/). However, in this course we use the GitLab server of the Faculty of Science](https://git.science.uu.nl/) because it can be accessed through Solis-id.

## Git is a remote server that hosts a repository (remote host)

Remember `git init` makes a `.git/` folder in your project. That is a local repository (local=lives on your computer).

GitLab is essentially a remote server that hosts a `.git/` folder.

But GitLab furthermore also comes with tons of tools to help you visualize and manage your repository.

## Create a repository on github (a remote repo)

* Navigate to https://git.science.uu.nl/ and login with your Solis-id and password
	+ Click **New Project**
	+ Choose **Create blank project**
	+ Enter `workdir` as the **Project name**
	+ Choose your email address as the **Namespace** in the project url (not os4p)
	+ Set it to **Internal**
	+ Untick the **Initialize repository with a README** box, we will be importing a repo onto GitLab
	+ Click **Create repository**

***
**You now have an empty remote repository and some instructions to populate it!**