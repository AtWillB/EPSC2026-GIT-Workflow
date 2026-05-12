### Intro bit

- Writing code is becoming more and more common for incoming students, and has been relevant for academics for years
- With the development of code, it also become more and more important to track the changes made to a collection of software
- The idea of a source control repository came, with the dominant market tool being a service called "Git". (small git history lesson?)
- Git has been used to help scale software professionally (in the private sector) for the last 2 decades, but has yet to be universally picked up by academia
- In the interest of introducing academics in planetary science specifically to source control, and git specifically, we suggest 3 workflows for different scales of software development that can be employed by any sized team in academia

### Main Components

1. A workflow for a single software developer, which involves committing to a single branch
   - This is generally not a professionally recommend workflow, and does not optimally make use of git as it was designed
   - But, it is helpful to get one's feet wet
   - Technical aspects
     - git fetch
     - git add *
     - git commit -m ""
     - git push
     - git pull
   - Why use this workflow?
     - pitch benefits
     - TIME SAVOR
     - COMMUNICATION
     - CLARITY ON CHANGES
     - INCENTIVES WRITING CLEAN CODE
2. A workflow for a small team of developers (say between 2-5)
   - Slightly less technical
   - Introduce branch theory
   - Technical Components
     - git merge
     - git rebase
       - You should not be scared of merges
     - Pull requests
     - git issue
   - What a merge conflict is (maybe too much)
   - General workflow
     - have a single master branch that everything gets merged onto
     - have separate development branches for adding large-scale features
     - separate into small teams, and have each team work on one feature branch
       - ONE ISSUE PER FEATURE/DEV BRANCH!!!!
       - issue gets closed once feature is implemented
     - try and implement recurring (daily, weekly) commits, improves clarity
     - Push your dev branches to master when you finish that feature
     - Have back-and-forth in the pull-request stage
       - in general, if there are no comments on a pull-request, you are doing something wrong!!
3. A workflow diagram for a large team (5+)
   - much less technical, basically just a diagram
   - One  branch called "main", one called "develop"
     - "develop" is what your software developer's push to
     - after n number of features are implemented, you put "develop" through a testing suite (can do this at the commit/PR level, but this is easier to explain)
     - After the test comes back clean, you merge "develop" into "main"
     - Main is what users interact with

### Conclusion

- The goal of this abstract is to inform academics about a potential programming philosophy involving source control, not the optimal/an optimal one
- There are many, many source control philosophies
- However, git has not yet been universally implemented into the programming process for academics, and that includes planetary science
- We hope a brief exploration into a potential philosophy, along with a description of the basic technical functionality of git as a tool enables planetary scientists to write code at the professional level without the fear of writing bad code

# GOAL

- Minimize the number of times people say "Please don't look at my code"
- We instead want the response to be "I'm not sure this is optimized well, but please take a look"
- We want the programming process itself to include the academic philosophy
- Fear prevents that

















---



# Draft:





**Introduction**

Planetary scientists write more code than ever, and most of them do it alone, without version control, and with the quiet anxiety that comes from knowing their software would not survive scrutiny. Git has been the standard tool for collaborative software development in industry for two decades, yet its adoption in academic research remains inconsistent; not because researchers lack the ability to use it, but because no one has made a concrete case for how it fits into the academic workflow specifically. This abstract presents three Git-based workflows of increasing complexity, designed for planetary science teams ranging from a single graduate student to a large collaborative group, and argues that the barrier to adoption is lower than it appears.

**The Single Developer**

The entry point is deliberately minimal. A researcher working alone commits to a single branch, using a handful of commands in a repeatable loop: `git fetch` to check for remote changes without overwriting local work, `git pull` to sync, `git add`, `git commit`, and `git push`. The payoff is immediate; a complete, recoverable history of every change made to a codebase, along with a growing record of why those changes were made. In practice, this habit also improves code quality: writing a commit message, even a short one, asks the developer to justify their edit, which quietly discourages the kind of sprawling, uncommented changes that make code difficult to share or revisit. For researchers who have never used version control, this workflow is the on-ramp.

**The Small Team**

For groups of two to five, Figure 1 illustrates a branching workflow that introduces the core of what makes Git genuinely powerful. Development happens on short-lived feature branches, each tied to a single tracked issue, while a protected `main` branch holds only tested, stable code. Merging back into `main` happens through a pull request ; a structured, documented conversation about whether the work is ready. This is where the workflow earns its place in an academic context: the pull request stage is peer review applied to code. Merge conflicts, which have a reputation for being intimidating, are in practice a straightforward ask: Git has found two competing versions of the same line and wants a human to decide which one is correct. They become rarer the more regularly a team commits. Teams that adopt this pattern consistently report that it reduces the fear of breaking things, distributes ownership across contributors, and creates an audit trail of technical decisions that survives student turnover ; one of the most persistent and underacknowledged problems in academic software development.

**The Large Tea**

Figure 2 extends this logic to groups of five or more by inserting a `develop` branch between active development and the stable `main`. Feature branches merge into `develop` continuously; `develop` merges into `main` only after passing a test suite. The result is a release rhythm ; periods of open development followed by deliberate consolidation ; that maps naturally onto how research projects are actually structured. Collaborators and users always have access to a working version of the software, and the test suite acts as a lightweight, automated form of the same quality control the pull request provides at the individual feature level.

**Conclusion**

The goal of this abstract is not to prescribe a single correct approach to scientific software development ; version control philosophy is genuinely varied and any team will adapt these patterns to their own needs. The narrower claim is that the academic programming culture, in planetary science and beyond, loses significant value to undocumented code, unrecoverable changes, and the low-grade embarrassment that leads researchers to preface every code-sharing interaction with an apology. Structured version control does not solve all of that, but it is a concrete, teachable, and immediately applicable step toward code that researchers feel comfortable standing behind.