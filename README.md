### **Git**

**Trunk vs Branch Dev**

- Branch is seen more in larger teams and/or large projects
- Allows features to be implemented as they are reviewed and completed
Issues
- Can have conflicting errors as the main branch is updated with new commits and pushes

**Pull Requests**

- Requests that notifies a team that the developer has completed a feature branch
- Notifies team that their feature branch is ready for reaview and to be merged with the main branch
- Creates a forum where the request can be discussed while also giving the ability for follow up commits to be pushed directly to the merge reques

**Commands**
```
git clone - Locate repo and clone it
git pull - working in a repo and pulling it
git add (staging)- working in a repo and adding or modifying files
git commit (sealing file to be send - message goes with commit to show changes)- working in repo and sealing changes made
git commit -m “Message goes here”
git push - Sends changes
git status - shows status of changes ready to be committed
git log:  shows log of commits
git log —oneline : shows log in a more readable way
git revert: 
 -When using revert - VI is opened and commit message is edited at the top line.
```
Commit messages should identify who did it, what file was modify, and what will happen if commit is pushed.
Keep messages uniform following the same formula each time.


**git branch**
```
git branch - shows current branches
git branch <name of branch> - creates branch
git checkout <name of branch> - to work in branch
git switch <branch name> - change branches
```
An error will pop when trying to push while in the branch. The proper command will display - copy and use that command
```
git push --set-upstream origin <branch name>
```

deleting branch from local machine
```
git switch main - Cannot be in the branch you are deleting.
git branch -d <branch name>
```

Branch to merge flow
- Dev creates branch
- Dev completes task, adds, commits, and push (the branch way)
- Go to github
- Go to repo you are working on
- Select pull request


- git stash - Use example
```
git add <file/s>
git stash
```
 - Do other work, add, commit
```
git stash pop
```
 - Work on original file, add, commit
 ```
git push
 ```

git stash temporarily shelves (or stashes) changes you've made to your 
working copy so you can work on something else, and then come back and re-apply them later on. 
Stashing is handy if you need to quickly switch context and work on something else, 
but you're mid-way through a code change and aren't quite ready to commit.

******************
### AWS

**IAM**

Identity and Access Management
- Create users with specific permissions set
- Can create IAM users for multiple situations or positions (ie. dev)
- Can limit access and resources
- IAM users are denied access by default until privilegs are added
- Can create groups and add users to them with permissions

**Route 53**
- Cloud Domain Service for routing end users to internet applications
- A way of routing users to aws infrastructure (and outside insfrastructures)
- Ability to register domain names
- Can automatically configure DNS settings for your domains

**aws cli**

Creating new profile in aws for terraform
```
aws configure --profile **profile name**
```
Example - create an s3 bucket:
```
aws s3api create-bucket --bucket **NAME** --region us-east-1
```

******************
### Terraform

**commands/arguments**
```
terraform init
terraform validate - checks code loacally for errors. Checks only syntax and variables
terraform plan - green + = creating, yellow ~ = modifying, red - = destroying
terraform appply
terraform destroy 
terraform fmt - formats typed code in a way to be easy to read
```

**Variables**

var types
- string
- map() ex: map(string)
 - Can create variables in seperate files, it variable.tf w/ region var
 - Calling variable require var. infront of variable name
 - Do not need to reference other files within direcroty
 - Data sources - asking for info 
 - Best practice: Declare providers in terraform

**State**
- Maps configured resouce instances and remote objects
- Make sure to communicate with team when adding hardware changes to instance
```
Terraform Import - can import changes
```

**Best practices**
- State files can contain secrets
- use git ignore to prevent state file from being pushed
- Dont share statefile

Show state of recource in CLI
```
terraform state show **resource**
```
