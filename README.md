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
cd tech_toolups/
```

If you type `ls -a` you can see the whole contents of that folder. The `-a` flag returns all files and directories that may be hidden. You should see a `README.md` file that was created automatically, as well as a folder called `.git`. 

Git uses this special subdirectory to store all the information about the project, including the tracked files. If we ever delete the `.git` subdirectory, we will lose the project’s history.

Let's check that we've got git setup correctly by asking about the status of this project:

```
git status
```

## Tracking Changes

Let's create a new .txt file using the command `touch`. Then check how that changed the status of our repository.

```
touch file.txt
git status
```

The final command should list the new untracked file called `file.txt`. Untracked means that git isn't tracking any changes to that file. Let's tell git to record all changes to it with the following:

```
git add file.txt
git status
```

Now, git lists this new file as one of the "changes to be committed." In other words, we've told git that we want to start tracking changes on this file.

Git now knows that it’s supposed to keep track of `file.txt`, but it hasn’t recorded these changes as a commit yet. To get it to do that, we need to run one more command:

```
git commit -m "Adding new text file"

[main 45f446e] Adding new text file
1 file changed, 0 insertions(+), 0 deletions(-)
create mode 100644 file.txt
```

When we run git commit, git takes everything we have told it to save by using git add and stores a copy permanently inside the special `.git` directory. This permanent copy is called a revision and it has a short identifier `45f446e`. (Your revision may have another identifier.)

Finally, we'll want to push this change up to the remote directory (`https://github.com/<YOUR_GITHUB_USERNAME>/tech_toolups`). To copy our changes from our laptop to our GitHub repo, we can use the following:

```
git push origin master

Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 8 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 288 bytes | 288.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To https://github.com/allisonmorgan/tech_toolups.git
   74119db..45f446e  main -> main
```

(If you run into [trouble here](https://stackoverflow.com/questions/17659206/git-push-results-in-authentication-failed#answer-21027728) with authentication, you might need to create a person authentication token. Follow the steps [here](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token) and supply that token as your password when asked.)

Now check out your change to the online directory. If it worked, you should see that our local version of the repository has been pushed up to the repository's "origin" (i.e., the copy on GitHub) and the `file.txt` has been added. Congrats! You've just made your first commit! Remember this basic workflow, after you've made your changes:

1. `git add .` (The period adds all changed files. It's typically safer to add individual files here like we did above)
2. `git commit -m "<COMMIT_MESSAGE>"`
3. `git push origin main`

You can (I always do) use the command `git status` in between these steps to make sure that you are (I am) still in the right spot.

## Ignoring Things


## Collaborating

