
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