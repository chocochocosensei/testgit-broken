# How to use git merge --squash 

** from https://stackoverflow.com/questions/5308816/how-to-use-git-merge-squash

> Say your bug fix branch is called bugfix and you want to merge it into master:
> 
> ```
> git checkout master
> git merge --squash bugfix
> git commit
> 
> ```
> This will take all the commits from the bugfix branch, squash them into 1 commit, and merge it with your master branch.
> 

and 

> ```
> git checkout main
> git merge --squash feature
> ```
> is the equivalent of doing:
> 
> ```
> git checkout feature
> git diff main > feature.patch
> git checkout main
> patch -p1 < feature.patch
> git add .
>```
> When I want to merge a feature branch with 105(!!) commits and have them all squashed into one, I don't want to `git rebase -i origin/master` because I need to separately resolve merge conflicts for each of the intermediate commits (or at least the ones which git can't figure out itself). Using `git merge --squash` gets me the result I want, of a single commit for merging an entire feature branch. And, I only need to do at most one manual conflict resolution.



