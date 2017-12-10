### INTERNAL CONTRIBUTING RULES FOR OPP TEAM MEMBERS

## NEVER PUSH TO MASTER

Prototypical git branch structure  
**master** - The main production line, release from here, most recent commits here will be what should be on live-server.    
**development** - This will be the main development branch off which all other working branches will start. 
All other branches must catch up to, and resolve conflicts with this branch before having a valid pull request.  
**yourname-dev** - Your personal development branch on this remote.  
**somefeature** - Some collaborative/focused effort around feature 'somefeature'  



* Work on your own branch, or branch for specific isolated collaborative/related work.  
* Submit PULL REQUESTS to merge to any shared intermediate or Develoment branches  
* ALL Pull Requests require REVIEW BEFORE accepting.  
* ALL pull requests must be a clean merge.  Author is responsible for catching up branch to match and merge cleanly.  



## How-to git  
https://git-scm.com/  

Common commands and conventions to adopt: (apply same convention to GUI tools too!)
```
git init 
//creates local repo (repository)

git remote add name-of-remote https://.....git
//add remote to your local repo (to push to)
//by convention your main/default remote should be called 'origin'

----Branches----
git branch -v
//shows all current branches on local repo

git branch branch-name
//make a branch FROM THE CURRENT BRANCH (at whatever commit)

git checkout branch-name
//Moves HEAD (where changes you make go) to this branch

git merge from-branch-name
//merge to CURRENT checked-out branch from other branch
//conflicts will need to be resolved and commited

git add .
//adds -everything- new/deleted changed inside of the repo the git-staging

git add path/file.ext
//add specific file

git add folder/
//add folder and all contents
//To NOT add files (binaries, build artifacts, IDE garbage files)
//use either .gitignore to mask them out from any 'add' command
//OR only selectively add to the git tracker

git status 
//Always use this to verify what you are going to commit!
//show current state of local repo
//red - not tracked, or not added
//green - added, ready to commit (staged)

git reset
//unstages all adds 

git commit -m "commit message"
//commit to LOCAL repo with commit message
//commits changes as a result of git add

----to the remote---

First:
git pull origin branch-name
//pulls from branch to your local branch
//if there are changes, there might be CONFLICTS!
//Ideally, no one but you will be pushing to this branch, conflicts are best found and examined in pull requests
//This is not always avoidable

git push origin branch-name
//always specify remote and branch to push to
//Convention, push from local/branch-A to remote/branch-A
//having different local branchnames/structures can make it confusing, and you could push to another remote branch by mistake




