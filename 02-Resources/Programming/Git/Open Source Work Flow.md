---
tags:
  - git
---
# Open Source Work Flow
This document hightlights the workflow when working on a open source project or working with multiple people.

[Reference](https://www.digitalocean.com/community/tutorials/how-to-create-a-pull-request-on-github)

1) **Fork Repository** - On the page or repository, click the **fork** button. With the repo now forked you can **clone** it to the local machine.
2) **Clone Repository** - Copy the link of the url and use the *git clone* command. 
   ```sh
   git clone https://github.com/yourusername/repository.git
```
3) **Create a New Branch** - when working on a collaborative project *never work on the main branch*. It's very important to create a new branch.
```sh
git branch <new-branch>

git checkout <new-branch>

#or

git checkout -b <new-branch>

```
4) **Make Changes** 
5) **Push Changes** - push the local changes to your forked github repo.
```sh
git push --set-upstream origin new-branch
```
6) **Updating Local Repository** - while working on project alongside other contributors, it's *very* import to keep your local repository up-to-date with the project. You'll need to configure a **remote**. You'll need to sync to the up-stream repository.
```sh
git remote add upstream https://github.com/original-owner-username/original-repository.git

##verify with 

git remote -v
```
7) **Sync The Fork** - once the remote is configured with references to the original repo
```sh
git fetch upstream

git merge upstream/main
```
8) **Sync The Branch on The Fork** *if necessary* - sync the main / master branch then change to the branch and use 
```sh
git merge main
```

9) **Create Pull Request** - navigate to your forked repositoryon github and press *new pull request*.  

------
# Reverting A File
Sometimes unneccessary changes are made and you'll need to revert a file back to the orginal condition
```sh
git checkout [commit ID ] -- path/to/file
```
[Reference](https://dev.to/lofiandcode/git-and-github-how-to-revert-a-single-file-dha)

