# 0 - Preface
## What is this git/GitLab Tutorial about?

The goal of this tutorial is to help physicists to **(1) start using [git](https://git-scm.com/) locally for [version-control](https://en.wikipedia.org/wiki/Version_control) of your code**, and **(2) begin using [GitLab](http://git.science.uu.nl/) to share your code and collaborate with others.**


Note: If we try to wait until we have perfect codes to share, more likely than not, we will end up never sharing them.

## Why is git important for physicists?

Git facilitates (1) **documentation**, and (2) **sharing/collaborating**. Both of these are important in science.

### I. Version-control for code = the lab notebook of experiments

In scientific experiments, we are trained to record every parameter that we modified and tested, as it ensures consistency  within an experiment and facilitates reproducible results. While we often record the experimental part of our experiments meticulously, the preprocessing and analysing of data are often ‘assumed’ to be recorded in our scripts.

Here are a few scenarios where we wish a detailed history of how codes were developed is available:

#### Scenario A: Things were working, now they are not!
You have 5 people collaborating on a single script. That script now results in an error after someone changed a few lines over the weekend. They have no recollection what was changed.

#### Scenario B: Why were changes made?
You joined a new lab, and were given a pipeline/script to modify that dated years back. The script is named cool_script_version25000.sh, with few comments. Whoever made it has quit academia and is travelling the world, soul searching, and won’t answer emails.

#### Scenario C: We made changes a long time ago…
Collaborator BigName wants to know what preprocessing parameters were used in your manuscript from 5 years ago.  You have since changed multiple parameters in your default processing pipeline.

![](https://phdcomics.com/comics/archive/phd101212s.gif "Final.doc")

Saving something as Final.doc is bad...but Final_script.py is just as bad (Image Credit: [PhD Comic](https://phdcomics.com/comics/archive.php?comicid=1531))


### II. Git and Remote Hosts (e.g., GitLab) makes sharing/collaborating easier

#### Share codes
The traditional method of sharing scientific results, manuscripts, is a difficult form to share scripts. For example, while you can share the general processes of how things are done, but the actual 1000+ lines scripts are usually not printed.

Remote Hosts such as GitLab (or other alternatives such as GitHub) makes sharing your codes very easy. It’s a link. People can choose to follow your code, and if you update it, they get a notification.

#### Facilitates new collaboration
If you found a way to speed up some toolbox, git/GitLab helps you to suggest this change to the author of the toolbox, even if you don’t know each other.

#### Encourages open source and open science

[Open source](https://en.wikipedia.org/wiki/Open-source_software) is typically a term used in software development, where it means the source code are open to the public. People can freely look at how a program was written, make improvements with them, etc.

Given a common goal of wanting more people to understand, reproduce, and build on top of previous work, an **'open’** approach to your code is certainly a good place to start. Git/GitLab will help facilitate your code being shared publicly. It also enables you to easily contribute to other projects, and incorporate ideas and contribution from others in a systematic way (even strangers!).


## Acknowledgment
* This tutorial is a fork of the tutorial on git & GitHub for scientists without formal programming background: https://gitbookdown.dallasdatascience.com, authored by Micaela Chan [@mychan24](https://github.com/mychan24) & Ekarin Pongpipat [@epongpipat](https://github.com/epongpipat)

  * Their tutorial borrows heavily from [Software Carpentry's git novice course](https://swcarpentry.github.io/git-novice/). Software Carpentry provides a lot of resources for other courses and teaching in general. Check them out!

  * Special thanks to [@jennywxyz](https://github.com/jennywxyz) for providing feedback and proofreading to their tutorial.


## Other helpful links
* [GitHub Education](https://education.github.com/) provides additional features to students & researchers for free (e.g., Pro account with unlimited collaborators)!
* [Git the Simple Guide](https://rogerdudler.github.io/git-guide/) provides all the necessary commands to use git.
