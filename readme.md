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

## Working on Group Projects

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

