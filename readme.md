# IXD students learn GitHub

## About Git (not GitHub)

Git is a "Distributed version control system", which means that every user has their own, complete, copy of the repository stored on their computer. A repository is like a database with a record of every change _ever_ made.

Git was originally created by Linus Torvalds, the same guy that created Linux, which is (probably) why it is free and opensource. 

Git is fast because most of the work is done locally rather than on a server. Best of all, it can be worked on offline! 

Because files are versioned, you can't overwrite any file.

Git is great for groups and teams because people can work on the same files simultaneously without conflict (due to the local repo).

When everything goes wrong with the current version of files, git allows you to revert back to an older version of the file/project whenver things hit the fan!

## Terminal Basics

`cd` = change directory    
`pwd` = print working directory     
`ls` = list files     
`ls -a` = shows hidden files     
`sudo` = superuser (prefix commands that need admin control)

## Getting Setup

1. Signup for [GitHub](https://github.com/join) and then apply for a [GitHub Education discount](https://education.github.com/discount_requests/new)
2. From your Mac terminal, type `git --version` to install git
3. Set your Name `git config --global user.name "Your name"`
4. Set your email `git config --global user.email "you@email.com"`
5. Check to make sure you got things correct: `git config --list`

## Using Git

1. `cd` to the Desktop (`cd ~/Desktop` or try typing `cd ` and dragging the folder from Finder into the Terminal)
2. Create a new folder for your first git project: `mkdir -p git-project /{css,img,js}`
3. Add build a home page, css, & js file: `touch index.html css/style.css js/script.js`
4. Connect git to the folder: `git init`
5. Check to see what the status of your repository is: `git status`
6. Add your files to the repo: `git add .` Note: empty folders, such as the `img` folder are ignored
    - We could also add single files. Example: `git add filename.html`
7. Git is ready and waiting, but we need to commit our files to the first version in the repo: `git commit -m "initial commit"`
8. Let's see how we're doing by checking `git status` again
9. Macs love to dadd `.DS_Store` files so lets make sure git doesn't waste time saving them by creating an ignore list: `touch .gitignore` _Note: Make sure you are in the root!_
10. Open `.gitignore` and list files & folders to ignore, one per line. Add `.DS_Store`

_Note: If you forget to add new files, rather than creating another commit, you can `git add` and `git commit --amend` to sneak them into the last commit_

### Extra Git Commands

- `git log` shows you the commit history
- `git stat` gives more details on that history
- `git log -p -2` displays differences for the last 2 commits (feel free to change the number)

## Adding in GitHub

_If you didn't already, signup for [GitHub](https://github.com/join) and then apply for a [GitHub Education discount](https://education.github.com/discount_requests/new)_

1. Create a new repo on GitHub and follow the instructions they give you. They should look something like this:
    
        git init
        git add README.md
        git commit -m "first commit"
        git remote add origin https://github.com/username/repo-name.git
        git push -u origin master
    
The last step is `git push -u origin master`: 
- origin is the name of the "remote" for your repository. When you link your repo to GitHub, you have a local copy on your computer, and a remote copy on GitHub.
- `-u` links the local and remote copies so you don't have to type out the long form each time. From now on, `git push` is all you need to type to get your last commit copied to GitHub.

**Protip:** You can cache your password using the osxkeychain credential helper. [GitHub Help](https://help.github.com/articles/updating-credentials-from-the-osx-keychain/) contains instructions on how to take care of this.

## Working on Group Projects

Working with your peers on group projects is super easy to setup: Once one of you has built a repo on GitHub, you can go to `Settings > Collaborators` and add the usernames of each member of the group. Once they connect to the repo, everyone can `push` and `pull` files to the same repository.

Watch out for merge conflicts. If you commit an update that has code that directly conflicts with someone else's commit, you will get a "merge conflict". These can be tricky to sort out at times, but as long as everyone is working on their own area of code, it shouldn't be a problem. 

If you do encounter a conflict, try [GitHub Help](https://help.github.com/articles/resolving-a-merge-conflict-using-the-command-line/) for some tips on getting outta hot water!

**Protip:** Always `git pull` before editing group code. That way you'll be sure to have the latest and greatest version of the group project. This will also drastically reduce the odds of merge conflicts!

## Forking & Pulling

"Fork" is GitHub lingo for getting a copy of an existing repo. This is a way for people to share access with strangers who may want to contribute to a large project (like Linux, for example). "Pulling" allows the original author to control who's code updates will be brought into the fold and added to the project. 

Forking is way more complicated than anything we need for group projects, but worth noting as something to explore down the road.

## Branching

Branching is a way to work on a project without affecting the regular [flow](https://guides.github.com/introduction/flow/) of the project. You are _branching_ off from the main project and your commits do not affect the master version of the repository.

- When you create a new Git repo, you begin on the `Master` branch
- `git status` confirms this for us
- add a new branch: `git branch branchName`
- switch to new branch `git checkout branchName`
- Protip: DO both steps at once `git checkout -b branchName`
- confirm which branch we are on: `git branch` or `git status`
- To merge, we need to be on the branch receiving the the commits from the other branch `git checkout master`
- merge: `git merge branchName`
- After you have successfully merged the branch into the Master, you should delete it: `git branch -d branchName`
	- If you are giving up on the branch and don't want to merge it: `git branch -D branchName` to force the delete
**Protip:** Never work directly in the master branch of a repo. The master should be for production code only.

**Protip:** Working on the wrong branch? `git stash` to toss all your changes into memory. Switch over to the correct branch and `git stash apply` to move your edits over to the right place

## Mistakes

## Conflicts

- Git will flag a merge conflict
- It will show the differences in the file (i.e. index.html)
- the "HEAD" is the master branch/main repo
- Fix the conflict in the file by deleting the wrong/outdated code and save.
- You will need to add the file again `git add file path/filename.html` and commit the changes `git commit -m"Fixed merge conflict`

### Resets

`git reset --hard HEAD` will force a reset to the last commit
`git reset --hard HEAD~3` will force the repo back 3 commits
`git reset --hard 39cdcd0339c122c0307930de9e5cc08217726cee` will let us to revert to a specific repo (We can find the log checksum with `git log`)

Reverting is non-destructive. The reset command will create a new commit in the log showing which commit was reverted.

## GitHub Pages & Markdown

Markdown is, for our purposes, a simplified way to write HTML. It was designed to be an "easy-to-read and easy-to-write" syntax. It can be converted easily to HTML, Word Docs, ePubs, and many other file formats. A great Markdown writer is [iA Writer](https://ia.net/writer/), though Brackets (and many other editors) provides syntax highlighting for Markdown. It is easy to learn as the [Markdown syntax](https://daringfireball.net/projects/markdown/syntax) reflects HTML hierarchy structures. Markdown is also used for project ReadMe files.

[GitHub Pages](https://pages.github.com/) is a way to share documentation and projects as Web sites directly through GitHub. Any static site (HTML, CSS, JS) can be hosted through GitHub Pages, and there is a template engine to make sites & blogs easier to maintain and produce called [Jekyll](https://jekyllrb.com/). Jekyll is a static site generator. It takes a template directory and Markdown files to create a complete, ready-to-publish static website. It is maintained by GitHub and integrates easily. [MkDocs](http://www.mkdocs.org/) is another static site generator, designed specifically to presenting project documentation. It is ridiculously simple to get running, but out of the box it isn't as customizable as Jekyll.

**Fun Fact:** Did you know that Sheridan has its own [Git server](http://bender.sheridanc.on.ca/)? 

