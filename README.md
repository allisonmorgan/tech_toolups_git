# Introduction to Version Control

Git is powerful and complicated. We could spend a whole day talking about git, but it is also quite possible to harness its powers using just three commands: `add`, `commit`, `push`. The goal of this document is not to explain deeply how git works, but to highlight how you can get started using git for your projects.

This document is inspired by materials from the [Software Carpentry](https://swcarpentry.github.io/git-novice/index.html) foundation and Rochelle Terman's [Introduction to Computational Tools & Techniques for Social Research](https://github.com/rochelleterman/PS239T). If you are hoping to learn more, these are great places to start.

**Learning Objectives:**
1. Configure git for the first time it is used on your computer.
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
