# Introduction

Planetary scientists tend to write their own software, and many choose to without employing version control. Git [1] was developed to help manage version control for software development, yet it's in acadedmia remains inconsistent [2, 3]. This work attemts to ease the entry of understanding Git by providing three different workflows, disigned for the solo-researcher up to a large collaborative group of 5+ people. 




## Workflow 1
A single programmer doesn't need much to get value from Git. 

A researching working alone can initiate changes to their own work as they complete tasks. 
To commit a change, all you need is three commands: 
> git add [path/to/additions]
> git commit -m [commit message]
> git push

You can now work, by yourslef, on multiple machines without worry!
To update your repository on another machine, cd into the correct directory and type:
> git pull
> [git pull update message]

Congradulations! You now have a complete, recoverable history of every change made to a codebase, 
along with a growing record  of why those changes were made. 




## Workflow 2

When working with more than one person, additional version control organization is required to preved overwrite conflicts. This is when understanding *branches* in git becomes necessary. Branches are seperate timelines of changes to a repository based on some specific previous commit. 

In this example, there are two types of branches. The `main` branch, which records your code in a usable state, and the `feature` branches, which records *temporary* code written by collaborators.

For a group between 2-5 people, we suggest a simple branch-per-feature approach, which mimics the normal academic development cycle. When a collaborator is assigned a feature to implement (e.g. making a tidal forces module), they create a new branch to develope that feature. 
> git branch Alice-Tidal-Forces
> git switch Alice-Tidal-Forces

To ensure that the new branch appears in everyone's next `git pull`, type:
> git push -u origin Alice-Tidal-Forces

After a new feature is implemented, a "pull request" is required to merge two branches, which allows you to see how your changes modify the main branch. This is equivalent to requesting the `main` branch to *pull* in the changes made on your branch. 

We recommend researchers unfamilliar with git to initiate a pull request with some user interface, usually either in GitHub or GitLab.




## Workflow 3
Workflow 3 is designed for 5+ people. For a group this large, we suggest one additional layer of organization to prevent conflicts. 

An intermediary `develop` branch is placed between the temporary `feature` branch and the more permanent `main` branch. Based on our previous example, your environment may look something like this:
> git branch
> *Alice-Tidal-Forces
> develop
> main

When a new feature is being *developed*, a new branch is made off of `develop`. After a group of new features have been made to `develope`, it is merged into `main`. Think of software with version numbers. A version increase from `15.0` to `16.0` is equivalent to merging `develop` into `main`, while a version increase from `15.5` to `15.6` is like merging `Alice-Tidal-Forces` into `develop`. 

This structure allows for groups of new features (e.g. heating module), which are made up of smaller feature additions (e.g. tidal, radioactive, primordial) to be implemented with careful purpose, and facilitates intelligent software design. 




# Conclusion

Version control philosophy is heavily debated (especially in industry [5]), and any team, academic or otherwise, will make team-specific adjustments that fit their culture and project structure. 

We claim that academic programming culture loses significant value to undocumented software, unrecoverable changes, and the low-grade embarrassment that leads researchers to preface every software-sharing interaction with an apology. 

Structured version control does not solve everything, but it is a concrete, teachable, and immediately applicable step forward that enables researchers to feel confident in their software development [6,7].