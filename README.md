# git_recipes
Useful git commands I use a lot and forget more often that I'd like to

Create a new branch in a local repo ([more info](https://stackoverflow.com/questions/1519006/how-do-you-create-a-remote-git-branch/27185855#27185855 "Stackoverflow, what else?")):

    $ git checkout -b <new_branch_name>
    
You want your local branch to be tracked in the remote:

    $ git push -u <name_of_remote> <name_of_branch>
    
There is a remote branch you want to track in your local repo (keeping its original name) ([more info](https://stackoverflow.com/questions/9537392/git-fetch-remote-branch "Yes, it's Stackoverflow again. What a big surprise!")):

    $ git checkout --track <name_of_remote>/<name_of_remote_branch_to_track>
    
Remove a local branch (if it is tracking a remote one, it is not deleted) ([more info](https://makandracards.com/makandra/621-git-delete-a-branch-local-or-remote "No, no Stackoverflow this time! Gotcha!")):
   
   First, you must pull:
    
    $ git pull
   
   Then, do your magic:
   
    $ git branch -d <name_of_branch>
    
Get only the list of files that are different between two checkpoints (working copy, commits, branches...):

    $ git diff --name-only <branch_name>
    
or (this one is almost the same as git status):
    
    $ git diff --name-only HEAD
    
or:

    $ git diff --name-only <commit_1> <commit_2>
    
One of the infinite ways to get meaningful information from your log history (you get : short hash, committer name, commit short date and commit message :

    $ git log --date=short --pretty=format:"%h %cn %cd %s"
 
