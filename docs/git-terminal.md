# Git Terminal Commands 

## Clone Repository

To do this we use the `git clone` command:

```bash
[coen@ArchLaptop Test]$ git clone https://github.com/coenraadhuman/git-github-dojo.git
Cloning into 'git-github-dojo'...
remote: Enumerating objects: 71, done.
remote: Counting objects: 100% (71/71), done.
remote: Compressing objects: 100% (67/67), done.
remote: Total 71 (delta 12), reused 48 (delta 0), pack-reused 0
Unpacking objects: 100% (71/71), done.
[coen@ArchLaptop Test]$ cd git-github-dojo/

```

## View Branches In Repository

To see the available branches in the repository use `git branch -a`

```bash 
[coen@ArchLaptop git-github-dojo]$ git branch -a  
* master
  remotes/origin/HEAD -> origin/master
  remotes/origin/gh-pages
  remotes/origin/gh-pages_angular-example
  remotes/origin/master
```

## Swith Banches

To swicth between branches on your git repository use `git checkout`

```bash
[coen@ArchLaptop git-github-dojo]$ git checkout gh-pages
Branch 'gh-pages' set up to track remote branch 'gh-pages' from 'origin'.
Switched to a new branch 'gh-pages'
```

## View Branches On Local Machine

It should be taken note of that not all the branches of the repository is on the local machine's storage.
When checking out with the previous command the branch `gh-pages` was made available.

```bash
[coen@ArchLaptop git-github-dojo]$ git branch
* gh-pages
  master
```

## Create A New Branch Locally

Sometimes you need to create a branch, to do this you still use the command `git branch`.

```bash
[coen@ArchLaptop git-github-dojo]$ git branch a-new-gh-branch
[coen@ArchLaptop git-github-dojo]$ git branch -a
  a-new-gh-branch
* gh-pages
  master
  remotes/origin/HEAD -> origin/master
  remotes/origin/gh-pages
  remotes/origin/gh-pages_angular-example
  remotes/origin/master
```
The above confirms that the branch has been created locally, but what is in the new branch?

* The current branch:
```bash
[coen@ArchLaptop git-github-dojo]$ echo "This is the gh-pages branch."
This is the gh-pages branch.
[coen@ArchLaptop git-github-dojo]$ ls
3rdpartylicenses.txt  CODEOWNERS   LICENSE                              polyfills-es2015.5cb1e996b2a376ba4548.js  runtime-es5.ee0aae13fb762b150814.js
404.html              favicon.ico  main-es2015.9404be0d8200ccb98034.js  polyfills-es5.14d3ef0587e16f38de72.js     styles.09e2c710755c8867a460.css
assets                index.html   main-es5.8ebc167ce6dbe8f0ae58.js     runtime-es2015.5bc68c0dd8cf137fbe82.js
```
* The new branch:
```bash
[coen@ArchLaptop git-github-dojo]$ git checkout a-new-gh-branch
Switched to branch 'a-new-gh-branch'
[coen@ArchLaptop git-github-dojo]$ ls
3rdpartylicenses.txt  CODEOWNERS   LICENSE                              polyfills-es2015.5cb1e996b2a376ba4548.js  runtime-es5.ee0aae13fb762b150814.js
404.html              favicon.ico  main-es2015.9404be0d8200ccb98034.js  polyfills-es5.14d3ef0587e16f38de72.js     styles.09e2c710755c8867a460.css
assets                index.html   main-es5.8ebc167ce6dbe8f0ae58.js     runtime-es2015.5bc68c0dd8cf137fbe82.js
```

In other words when creating a new branch it will make a duplicate of the current branch under the new name.

## Add The New Branch To The Repository

To add the branch to the repository use `git push`.

```bash
[coen@ArchLaptop git-github-dojo]$ git push origin a-new-gh-branch
Username for 'https://github.com': coenraadhuman
Password for 'https://coenraadhuman@github.com': 
Total 0 (delta 0), reused 0 (delta 0)
remote: 
remote: Create a pull request for 'a-new-gh-branch' on GitHub by visiting:
remote:      https://github.com/coenraadhuman/git-github-dojo/pull/new/a-new-gh-branch
remote: 
To https://github.com/coenraadhuman/git-github-dojo.git
 * [new branch]      a-new-gh-branch -> a-new-gh-branch
```

For more information in regards to branch management look this [site](https://github.com/Kunena/Kunena-Forum/wiki/Create-a-new-branch-with-git-and-manage-branches).

## Pull New Changes To Local Branch Copy

To get this done we use `git pull`.

```bash
[coen@ArchLaptop git-github-dojo]$ git checkout master
Switched to branch 'master'
Your branch is up to date with 'origin/master'.
[coen@ArchLaptop git-github-dojo]$ git pull
remote: Enumerating objects: 34, done.
remote: Counting objects: 100% (34/34), done.
remote: Compressing objects: 100% (25/25), done.
remote: Total 28 (delta 9), reused 15 (delta 1), pack-reused 0
Unpacking objects: 100% (28/28), done.
From https://github.com/coenraadhuman/git-github-dojo
   33b9266..563f50f  master                   -> origin/master
   df9b3d4..fee81af  gh-pages_angular-example -> origin/gh-pages_angular-example
Updating 33b9266..563f50f
Fast-forward
 docs/git-terminal.md | 106 ++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
 docs/gitkraken.md    |   1 +
 2 files changed, 107 insertions(+)
 create mode 100644 docs/git-terminal.md
 create mode 100644 docs/gitkraken.md
[coen@ArchLaptop git-github-dojo]$ 
```

## Add Changes From Local Branch Copy to Repository

We need more than one command to do this, namely `git add`, `git commit` and finally `git commit`.

```bash

```
