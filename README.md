Git workflow is a recipe for how to use git to accomplish work in a consistent and productive manner.
#### Merge types
- Merge
- Fast Forward Merge
- Squash and Merge
- Rebase and Merge
##### Merge
- Branch 1 and Branch 2 will be mix as history
- It add to the history of the based on the timestamp of when they were created
##### Fast Forward Merge
- It ignore new Branch 1 commit, and will using Branch 2 as the latest commit
##### Squash and Merge
- Branch 1 only get latest 'SINGLE' commit of branch 2, rather full piece of work of commit
- Good for MAIN/MASTER branch
##### Rebase and Merge
- It like basic merge but instead of mix, the history will be branch 1 first than branch 2 of commit

### Short description of workflow
#### Centralized workflow
- Where all team members work with a single central "main" repository and a single main branch
#### Feature branching
- All feature development should take place in a dedicated branch instead of the main branch
- Encapsulation make it easy for multiple developers to work on particular feature without disturbing the main codebase
- Main branch will never contain broken code
- Huge advantage for continuous integration environments
- Pull Request
	- Branches make it possible to discuss changes via pull request
	- Not immediately merge into main branch
	- Interested parties will be notified automatically
	- Make sure your local main is synchronized with the upstream main

#### Gitflow workflow
- Version control strategy design to manage Git branch
- To Initialize all branch if don't have:
```
git flow init
```
- Main branches
	- main - Contains production - ready code.
	- develop - Integrates feature and prepares for the next release
- Supporting branches
	- Hotfix - Create from 'main' for immediate fix to production. Merge into both 'main' and 'develop'
	- Feature branches - Create from develop for new features or tasks. Merge back into develop once complete
	- Release Branches - Create from develop when preparing a new release. Allow for final bug fixes and documentations updates. Merged into both 'main' and 'develop'
	- Support - Create from specific tag in 'main' for long-term maintenance for a particular version. used for applying critical fixes and updates to that version without affecting the main development flow
	- Version Tag - Each release from the 'main' branch is tagged with a version number for easy to identification and rollback if necessary

#### Forking workflow
- Using a single server-side repository to act as the "central" codebase
- Every developer their own server-side repository
- To push new code into official repository
	- The developer need open a pull request from that new code branch to the official repository
	- The pull request get approved for merge and is merge into the original server-side repository

### Setup Git flutter and azure
Step 1: Create New project name Kiosk
Step 2: Go to Repos
Step 3: Create new flutter project name kiosk
Step 4: Open terminal to current path, or open android studio terminal
Step 5: run this command line
This for initialize git, it create hidden file of git:
```
git init
```
Get URL from repo, this for add remove URL, origin mean original which is name of the remote:
```
git remote add origin https://syazwan0684@dev.azure.com/syazwan0684/Kiosk/_git/Kiosk
```
To add all file into git:
```
git add .
```
To commit into current branch, with message "First commit"
```
git commit -m"First commit"
```
To upload code into azure website, master is name branch
```
git push origin master
```
If you open your azure again you will see all code file upload

### Setup branch
It will have 6 total of branch, and main branch is will be name of release
```
main
develop
hotfix
feature_branch
release_branch
support
```

After create all branch, then we replace default to main, which we make main as production code
1. Go to branches
2. Click more options at main branch
3. Press set as default branch
4. Remove master branch

### Desktop GIT
Source file: https://desktop.github.com/

To use git GUI, 
1. Add exisiting repository that we create kiosk, get path from it and add repository
2. Fetch origin latest from azure, It need password
3. To get password, go to azure website, press repos and press clone button
4. After that press generate Git Credentials button and get password from there
5. And paste to the password it need

Delete master branch that we create from local repository

### Set security to other people only can fork and new pull request only
Open settings
1. To go settings press Kiosk at the top
2. Press manage repositories

Create two group
1. Admin is for responsibility of the repository
2. Developer only can be fork and pull request

Create Group Admin
1. If you already at manage repositories
2. Press button permission at general
3. Create new group for Admin
4. And all give allow

Create Group Developer
1. Create new group for Developer
2. Then all give deny

Deny contribute
### Fork from git, Create new Repository
1. Click fork beside clone
2. Choose all branches and click fork button
3. Now you can clone your project and update your code

### Get your latest

### To merge your code from your repository to

```
git pull upstream main
```
```
git remote add upstream <clone URL>
```
```
git remote set-url upstream <clone URL>
```


Further Reading
https://www.atlassian.com/git/tutorials/comparing-workflows
https://www.atlassian.com/git/tutorials/comparing-workflows/feature-branch-workflow
https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow
https://www.atlassian.com/git/tutorials/comparing-workflows/forking-workflow
https://learn.microsoft.com/en-us/azure/devops/repos/git/pull-requests?view=azure-devops&tabs=browser
https://learn.microsoft.com/en-us/azure/devops/repos/git/about-pull-requests?view=azure-devops
https://learn.microsoft.com/en-us/azure/devops/repos/git/branch-policies-overview?view=azure-devops
https://learn.microsoft.com/en-us/azure/devops/repos/git/git-tags?view=azure-devops&tabs=browser
https://lukemerrett.com/different-merge-types-in-git/
https://learn.microsoft.com/en-us/azure/devops/repos/git/forks?view=azure-devops&tabs=visual-studio#the-forking-workflow
https://learn.microsoft.com/en-us/azure/devops/repos/git/pulling?view=azure-devops&tabs=visual-studio-2022

Not complete
1. Set Security User
2. Git Flow workflow
3. Tags

https://trapeye.github.io/knowledge/
