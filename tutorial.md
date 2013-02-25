#Your first Git cheatsheet
##Fork it, improve it and send me a pull request

Before you start, configure ssh on your machine and connect to Github. Follow these simple tutorials to get set up, [Part 1] (https://help.github.com/articles/set-up-git) and [Part 2] (https://help.github.com/articles/generating-ssh-keys)

###Make an existing directory on your local machine a git repo:
	git init 
(ie: initialize this folder as a git repository)

###Make a new repo out of thin air: 
	git init PROJECT_DIR_NAME_HERE

###Connect your local repository to the remote on Github
Make the repo in github and grab the ssh address

	git remote add NAME_THE_REMOTE_HOST git@github.com:GITHUB_ACCOUNT_NAME/NAME_OF_REPO.git
	git remote add origin git@github.com:tommeagher/gitintro.git

<em>For more on the "origin" remote, [read this] (http://gitimmersion.com/lab_39.html)</em>

###Take a snapshot of your changed files with "commit":
Create new files in your local repository folder

	git status
(tells you what files have changed)

	git add FILENAME
(stages individual files to be committed or git add . to stage them all)

	git commit –m "COMMIT MESSAGE"

After you've added the file to staging once, you can do both of these commands in one:

	git commit -am "NEW COMMIT MESSAGE"

###Send your committed file changes to the remote host at Github by pushing:
	git push –u NAME_THE_REMOTE_HOST BRANCH_TO_COMMIT

	git push –u origin master

###Grab and merge changes from the remote host to your local repo:
	Git pull NAME_THE_REMOTE_HOST BRANCH_TO_COMMIT
	
	git pull origin master 
(or simply git pull)

Alternatively, you can fetch the changes and merge them in manually, which some users suggest to avoid painful merges. 
	
	git fetch origin
	
	git merge origin master

###Clone an existing repo from Github to your local machine:
**git clone REPO_ADDRESS**

	git clone git@github.com:tommeagher/gitintro.git

###Branching
	git branch
(shows you all the branch names and which one you are working on) 

	git branch BRANCHNAME
(creates new branch. Name can be whatever you want)

	git checkout BRANCHNAME
(switches to branch)

Note: when you want to push changes from your branch, you would use

	git push origin BRANCHNAME

###Merging back to master
	git checkout master
(switch back to master branch)

	git merge BRANCHNAME
(merge your branch to master)

	git push origin master


##Great resources for further reading
+ [An easy intro guide to git] (http://rogerdudler.github.com/git-guide/)
+ [Git reference] (http://gitref.org/)
+ [Pro Git] (http://git-scm.com/), the free html book
+ Code Schools free [Try Git] (http://www.codeschool.com/courses/try-git) course
+ A good [cheat sheet] (http://martinadams.tumblr.com/post/37209901794/git-cheat-sheet)
+ [Lord of the Files] (http://www.wired.com/wiredenterprise/2012/02/github/all/), the Wired story on git and Github
+ News apps team's [best commit messages of 2012] (http://www.niemanlab.org/2012/12/updated-horse-parser-the-year-in-journo-code-commit-messages/), from Nieman Lab.
+ [Commit logs from last night] (http://www.commitlogsfromlastnight.com/)


##Cheats from the experts
git fetch --all git reset --hard origin/master

from Matt Terenzio, "for a complete fresh start"

Always fetch and merge instead of pulling. "Takes a little more time, but prevents many headaches."

from Al Shaw

"Resolving merge conflicts with git checkout --(ours|theirs). Cause that’s what you want 99% of the time."

from Al Shaw. More on this technique [here](http://gitready.com/advanced/2009/02/25/keep-either-file-in-merge-conflicts.html).

git mergetools

from Jeff Larson, which pops open a GUI to help resolve merge conflicts

git blame

tells you who made the changes to each file in a commit. This [and a bunch more good ones] (http://sunlightfoundation.com/blog/2010/07/16/a-few-git-tips/) are from Sunlight Foundation.