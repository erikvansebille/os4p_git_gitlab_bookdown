# 1- Setting up git

## Command-line vs. GUI

In this tutorial we are going to use the command-line version of git, which is the most basic (and powerful) way to use git. Note, however, that for most of the commands you can also use a graphical user interface (GUI) like [GitHub Desktop](https://desktop.github.com/) or [GitKraken](https://www.gitkraken.com/). If you use Visual Studio Code, you can also use the built-in git functionality.

## Download git

See https://git-scm.com/book/en/v2/Getting-Started-Installing-Git for instructions on how to download and install git on your operating system. Note that git is already installed on most Unix-based systems (e.g., Linux, MacOS), so you may not even need to do this. You can check by opening a terminal and typing `git --version`.

_Note for Windows users_: You may also want to install [git bash](https://www.atlassian.com/git/tutorials/git-bash), which gives you a linux-like terminal that runs `bash`. Git can also be run from Power Shell, but git bash would allow you to run every command in this tutorial (e.g., functions such as `touch` or `echo` for making file and printing lines in a terminal).

## Configuring git
This user name and email is your identity when using git. Sometimes you don't want to use a personal email, a [no-reply email associated with Github](https://help.github.com/en/articles/setting-your-commit-email-address#setting-your-commit-email-address-on-github) is available for that. For now, just use your personal email.

### Setup username and email
```bash
## save your original user.name and email into text files.
## These will be restored after the entire Rmd is knitted.

nu=$(git config --global --list | grep user.name | wc -l)
ne=$(git config --global --list| grep user.email | wc -l)

mkdir ~/workdir_tmp

if [ $nu -gt 0 ];
then
  git config --global --list | grep user.name | cut -d"=" -f 2 > ~/workdir_tmp/username.txt
fi

if [ $ne -gt 0 ];
then
  git config --global --list | grep user.email | cut -d"=" -f 2 > ~/workdir_tmp/email.txt
fi

```

```bash
git config --global user.name "Shady Whale"

git config --global user.email "shadywhale@allthewhales.com"
```

### Setup the correct linebreaks encoding
Different operating systems (OS) uses different characters to encode new lines (linebreaks). Setting git to make sure it reads the correct type of characters as linebreaks.

**Mac/Linux**

```bash
git config --global core.autocrlf input
```


**Windows**

```bash
git config --global core.autocrlf true
```

### Setup "nano" as the text editor to interface with git
The default text editor for git is [Vim](https://eastmanreference.com/a-quick-start-guide-for-beginners-to-the-vim-text-editor), which is difficult to use. [nano](https://www.howtogeek.com/howto/42980/the-beginners-guide-to-nano-the-linux-command-line-text-editor/) is a good alternative that can still handle text editing within the terminal. (You could setup other text editors as your default).

```bash
git config --global core.editor "nano -w"
```

### Check to ensure settings are correct
```bash
git config --list
```

#### Helpful links to setting up git
https://help.github.com/en/articles/configuring-git-to-handle-line-endings#platform-all

***
**Now you should have git installed on your personal computer, with basic configurations all set and ready to go!**

