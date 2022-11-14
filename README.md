# Introduction to Version Control

Git is powerful and complicated. We could spend a whole day talking about git, but it is also quite possible to harness its powers using just three commands: `add`, `commit`, `push`. The goal of this document is not to explain deeply how git works, but to highlight how you can get started using git for your projects.

This document is inspired by materials from the [Software Carpentry](https://swcarpentry.github.io/git-novice/index.html) foundation and Rochelle Terman's [Introduction to Computational Tools & Techniques for Social Research](https://github.com/rochelleterman/PS239T). If you are hoping to learn more, these are great places to start.

**Learning Objectives:**
1. Configure git the first time it is used on your computer.
2. Create a git repository.
3. Go through the modify-add-commit cycle for one or more files.
4. Explain how to collaborate with others using git.

## Setting up git

Git is installed by default on many Mac and Linux-based machines. You can check if git is installed by running `git --version`. If that doesn't work, follow the steps outlined [here](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) to install git for your machine.

If it is your first time running git, you'll need to configure a few things. For example, here is how the Doyle Owl would set up git:

```{bash}
git config --global user.name "Doyle Owl"
git config --global user.email "dowle@reed.edu"
```

You should use your own name and email address. The email address should be the same email you chose when you [set up your Github account](https://github.com/signup). (If you haven't set up a Github account, please do so.) 

If you aren't sure whether you have already added this information to your git config, you can run `git config --list` to see your machine's configuration. The flag `--global` tells git to use the settings for every project, in your user account, on this computer. There are [a lot more things](https://swcarpentry.github.io/git-novice/02-setup/index.html) you can provide here (e.g., default text editor).

## Creating a repository

Once git is configured, we can start using it to share code on [GitHub](https://github.com). There is more than one way to create a repository, I usually start from the web UI and [follow these steps](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-new-repository).

For the purposes of this exercise, call your new public repository (or "repo" for short): `tech_toolups`. Check the box that says to add a README file. You do not need to [choose a license](https://choosealicense.com) right now.

Next, clone this repo onto your machine in a location you will remember. [Here](https://help.github.com/articles/cloning-a-repository/) are some more detailed instructions on how to do that, but typically something like the following will do it:

```
git clone https://github.com/<YOUR_GITHUB_USERNAME>/tech_toolups.git
```

Next, navigate into that repository with

```
cd tech_toolups
```
