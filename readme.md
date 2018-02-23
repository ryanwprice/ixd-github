# IXD students learn GitHub

## About Git (not GitHub)

- Git is a "Distributed version control system", which means that every user has their own, complete, copy of the repository stored on their computer. A repository is like a database with a record of every change _ever_ made.

Git was originally created by Linus Torvalds, the same guy that created Linux, which is (probably) why it is free and opensource. 
- 
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

- cd to the Desktop (show GUI shortcut)
- make a root folder, 
`mkdir -p root folder/{css,img,js}
- touch index.html css/style.css js/script.js
- git init
- git status
- git add . **empty folder are ignored**
- git commit -m "initial commit"
- git status
- touch .gitignore (in the root) and list files & folders to ignore, one per line Add .DS_Store )

*if you forget to add new files, you can `git add` and `git commit --amend`

- `git log` shows you the commit history
- `git stat` gives more details
- `git log -p -2` displays differences for the last 2 commits

## Adding in GitHub

- Create a new repo on GH
- Follow the instructions
- `git push -u origin master` (origin is the name of the remote for GH)
- `-u` links the local and remote branches so you don't have to type out the Long form each time
- git push for all other changes

# Working in groups

- Add collaborators
- Collabs can push & pull to GH repo

### Fork & Pull
- Collaborators don't have to fork & pull on Public repos 
- Fork = get a copy of a repo
- Pull = original author can review changes made in forked copy before combining it into the original repo
- git pull

Note: You can cache your password using the osxkeychain credential helper. GitHub help contains instructions on how to install it
# Branching

# Mentions

- GitHub pages
- markdown

