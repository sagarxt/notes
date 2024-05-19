# GIT USING COMMANDLINE

Check Git is properly installed or not :

```bash
git --version
```

Configure Git (Use GitHub account) :

```bash
git config --global user.name "Your Name"
git config --global user.email "Your Email"
```

Check Git configuration :

```bash
git config --list
```

Create a folder or directory and change to that directory :

```bash
mkdir gitdemo
cd gitdemo
```

Initialize Git on that directory :

```bash
git init
```

List all files in that directory :

```bash
ls
```

Create a file in that directory :

```bash
touch hello.txt
```

Git status to see the changes :

```bash
git status
```

Git status in short :
? - Untracked files
A - Files added to stage
M - Modified files
D - Deleted files

```bash
git status -s
```

```bash
git status --short
```

<b>Files in your Git repository folder can be in one of 2 states</b>

1. Tracked - files that Git knows about and are added to the repository
2. Untracked - files that are in your working directory, but not added to the repository<br><br>

### Git staging or to be tracked.

Add a specific file to be tracked :

```bash
git add hello.txt
```

Add all files to be tracked :

```bash
git add .
```

```bash
git add --all
```

```bash
git add -A
```

### Git commit or save point

Commit the changes. (-m "..." is the commit message) :

```bash
git commit -m "First commit"
```

Commit small changes with out staging or skiping the staging enviorment :

```bash
git commit -a -m "Small changes"
```

Git commit log (To check log or histry of commits from the repository) :

```bash
git log
```

### Git help

See all the available options for the specific command :

```bash
git command -help
```

See all commands :

```bash
git --help
```

### Git branch

Branch is a new/separate version of the main repository.
Branches allow you to work on different parts of a project without impacting the main branch.
<br>
Create a new branch :

```bash
git branch branch-name
```

Check current branches :

```bash
git branch
```

Switch to a branch :

```bash
git checkout branch-name
```

Switch to main branch :

```bash
git checkout main
```

Create and switch to new branch :

```bash
git checkout -b branch-name
```

See remote branches :

```bash
git branch -r
```

See all branches (remote and local) :

```bash
git branch -a
```

<br>
<b>After making changes in branch, use commit command to save the changes. Then switch back to main branch</b>

```bash
git commit
```

```bash
git checkout main
```

<br>

Merge new branch to main branch :

```bash
git merge branch-name
```

To delete a branch :

```bash
git branch -d branch-name
```

## Git remote

Here we save our local repo to github/remote repo.
Create a repo on github.
Add remote repo to local repo :

```bash
git remote add origin https://github.com/oupp/ouppnotes.git
```

Push local repo to remote repo :

```bash
git push --set -upstream origin main
```

```bash
git push -u origin main
```

Fetch remote repo (to get the latest changes) :

```bash
git fetch origin
```

Get changes of master or main branch :

```bash
git log origin/master
```

Difference of master and main branch :

```bash
git diff origin/master
```

Merge remote branch to local branch :

```bash
git merge origin/branch-name
```

<br>
<b>pull is a combination of fetch and merge. It is used to pull all changes from a remote repository into the branch you are working on.</b><br><br>
Pull remote to local master :

```bash
git pull origin
```

Pull remote branch to local branch :

```bash
git pull origin branch-name
```

Push local branch to remote :

```bash
git push origin
```

```bash
git push origin branch-name
```

Update our local repo with remote repo :

```bash
git pull
```

<br>
<i>Now go to GitHub, and confirm that the repository has a new branch.
now click on Compare & pull request to proceed to merge, here we can preview the files.
Then we can click on Create pull request.
On next page click on Merge pull request and then confirm the merge // to merge the branch with master branch.
as we merged successfully we cand delete the branch on clicking Delete Branch.</i>
<br><br>

### GitHub Flow

The GitHub flow works like this:

1. Create a new Branch
2. Make changes and add Commits
3. Open a Pull Request
4. Review
5. Deploy
6. Merge

### Git ignore

It ignores the files that are mentioned in .gitignore

Create a .gitignore file :

```bash
touch .gitignore
```

```bash
git add .gitignore
```

<i>Ignore ALL .log files</i>

```txt
*.log
```

<i>Ignore ALL files in ANY directory named temp</i>

```txt
temp/
```

Comment :

```txt
#comment
```

All name files, name folders, and files and folders in any name folder :

```txt
name
```

Ending with / specifies the pattern is for a folder. Matches all files and folders in any name folder :

```txt
name/
```

All files with the name.file :

```txt
name.file
```

Starting with / specifies the pattern matches only files in the root folder :

```txt
/name.file
```

All name folders, and files and folders in any name folder :

```txt
**/name
```

All files withe .file extention :

```txt
*.file
```

All folders ending with name :

```txt
*name/
```

! specifies a negation or exception. All files withe .file extention, except name.file :

```txt
*.file
!name.file
```

### Git revert
revert is the command we use when we want to take a previous commit and add it as a new commit, keeping the log intact.
Step 1: Find the previous commit
Step 2: Use it to make a new commit
<br>
To get logs of previous commits in one line :

```bash
git log --oneline
```

Revert previous commit :

```bash
git revert
```
Revert to a specific commit:

```bash
git revert commit-hash
```
REvert with no message:

```bash
git revert --no-commit
```
```bash
git revert --no-edit
```

### Git reset
Reset is the command we use when we want to move the repository back to a previous commit, discarding any changes made after that commit.
Step 1: Find the previous commit
Step 2: Move the repository back to that step
<br>
Reset to a specific commit:

```bash
git reset commit-hash
```