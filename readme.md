# IXD students learn GitHub

## Resources

Version Control with Git https://gumroad.com/l/rXch
http://ohshitgit.com/
Request a discount https://education.github.com/discount_requests/new
Github Hello World https://guides.github.com/activities/hello-world/
https://services.github.com/on-demand/downloads/github-git-cheat-sheet.pdf
https://try.github.io

https://gist.github.com/ryanwprice/1e4c2dc7ffe8ac5041a9aa3e1b243ce9

## About

- Git is a "Distributed version control system" = every user has a complete copy of the repo on their computer
- originally created by Linus Torvalds 
- a repo is like a database with a record of every change ever made
- Most of the work is done locally, instead of on a server, so it is fast (and can be worked on offline)
- Everything is checksummed (like a unique barcode)
- Free and opensource
- Files cannot be overwritten
- There is a common repository that holds all the latest files
- People can work on the same files simultaneously without conflict
- Allows you to revert back to an older version of the file/project if needed

## Terminal basics

cd
Pwd
Ls
Ls -a shows hidden files
Sudo (superuser)

## Getting setup

-signup for GitHub https://education.github.com/discount_requests/new

- `git --version` (installs git)
- git config --global user.name "Your name"
- git config --global user.email "ryan@ryanprice.net"
- git config --list

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

