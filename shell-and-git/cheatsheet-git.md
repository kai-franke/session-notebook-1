## Basic Shell commands

| command                             | functionality                                                              |
| ----------------------------------- | -------------------------------------------------------------------------- |
| `ls`                                | list the content of the current directory                                  |
| `ls -l`                             | list the content of the current directory detailed                         |
| `ls -a`                             | list the content of the current directory including hidden                 |
| `cd <folder name>`                  | change directory into a folder                                             |
| `cd ..`                             | change into the parent folder                                              |
| `cd ~`                              | change into your home directory                                            |
| `pwd`                               | print the current directory path                                           |
| `touch example.md`                  | create a file called "example.md"                                          |
| `mkdir newFolder`                   | create a folder called "newFolder"                                         |
| `rm <file name>`                    | delete a file permanently (there is no trash bin to recover files!)        |
| `rm -r <name>`                      | delete empty folder                                                        |
| `rm -rf <name>`                     | delete repository/directory (incl. .git).                                  |
| `open .`                            | open the current folder in the finder                                      |
| `cat <file name>`                   | prints the content of a specific file                                      |
| `curl <url>`                        | prints the received content from the specified url. (try `curl ipinfo.io`) |
| `mv <filename> <filename>`          | renames file                                                               |
| `mv <filename> <path/to/somewhere>` | moves file to different folder                                             |

## Committing in a local repository

| Git command                      | Git task                                         |
| -------------------------------- | ------------------------------------------------ |
| `git init`                       | Initializes a git repository                     |
| `git status`                     | List all files that have changed and their state |
| `git add <filename>`             | Add a file to the stage                          |
| `git commit -m "Commit message"` | Create a commit including all staged files       |
| `git log --oneline`              | Show the commit history                          |

## Synchronizing local & remote repositories

| Git command       | Git task                                                     |
| ----------------- | ------------------------------------------------------------ |
| `git clone <url>` | Create a copy of the remote repository on your local machine |
| `git push`        | Upload content to the remote repository                      |
| `git pull`        | Download content from the remote repository                  |

## Git `branch` commands

| command                        | functionality                                 |
| ------------------------------ | --------------------------------------------- |
| `git branch`                   | list your branches                            |
| `git branch -a`                | list all branches (local and remote)          |
| `git branch <branchname>`      | create a new branch                           |
| `git branch -d <branchname>`   | delete a branch                               |
| `git switch -c <branchname>`   | create a new branch with the switch command   |
| `git checkout -b <branchname>` | create a new branch with the checkout command |
| `git switch <branchname>`      | switch branches                               |
| `git checkout <branchname>`    | another way to switch branches                |

## Restore

| Git command               | Git task                                                 |
| ------------------------- | -------------------------------------------------------- |
| `git restore .`           | Return to the last committed state of the entire project |
| `git restore <file name>` | Restore individual filesy                                |

## Links

- https://github.com/RehanSaeed/Bash-Cheat-Sheet
- [terminal basics](https://mrkaluzny.com/blog/terminal-101-getting-started-with-terminal/)
- [command line cheat sheet](https://github.com/0nn0/terminal-mac-cheatsheet#english-version)

- [Connect with SSH Docs on GitHub](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/about-ssh)
- [Git SCM](https://git-scm.com/)
- [Git book](https://git-scm.com/book/en/v2)
- [Git Cheatsheet](https://training.github.com/downloads/github-git-cheat-sheet/)

## Merge Conflict

- navigate into your repository locally into the main branch and pull the updates from remote:
  1. git switch main
  2. git pull
- switch to the feature branch that causes the merge conflict with the main branch
  1. git switch feature-branch-name
- merge the main branch into the feature branch
  1. git merge main
- you will now have to solve the merge conflict locally on the feature branch
- after you have solved the merge conflict create a new commit on the feature branch and push to remote
  1. git add .
  2. git commit -m "solve merge conflict"
  3. git push -u origin feature-branch-name
- you should now be able to merge the feature branch into main on GitHub
  1. (after merge) git switch main
  2. git pull
  3. git branch -d feature-branch-name
