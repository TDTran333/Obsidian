https://happygitwithr.com/git-commands.html

New local git repo from a repo on GitHub:

git clone https://github.com/jennybc/happy-git-with-r.git

Check the remote was cloned successfully:

* git remote --verbose

Stage local changes, commit:

* git add foo.txt
* git commit --message "A commit message"

Check on the state of the Git world:

* git status
* git log
* git log --oneline

Compare versions:

* git diff

Add a remote to existing local repo:

* git remote add origin https://github.com/jennybc/happy-git-with-r
* git remote --verbose
* git remote show origin

Push local master to GitHub master and have local master track master on GitHub:

* git push --set-upstream origin master
#' shorter form
* git push -u origin master
#' you only need to set upstream tracking once!

Regular push:

* git push 
#' the above usually implies (and certainly does in our tutorial)
* git push origin master
#'' git push [remote-name] [branch-name]

Pull commits from GitHub:

* git pull

Pull commits and don’t let it put you in a merge conflict pickle:

* git pull --ff-only

Fetch commits

* git fetch

Switch to a branch

* git checkout [branch-name]

Checking remote and branch tracking

* git remote -v
* git branch -vv