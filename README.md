# kottans-frontend

## Repository dedicated to participation in [Kottans frontend course](https://github.com/kottans/frontend)
## My progress :rocket:

 1. **GENERAL**
    - [x] [Git and Github](#1-git-and-github)
    - [x] [Linux CLI and Networking](#2-linux-cli-and-networking)
    - [x] [VCS (hello gitty), GitHub and Collaboration](#3-vcs-hello-gitty-github-and-collaboration)
  
 2. **FRONT-END BASICS**
  
    - [ ] [Intro to HTML & CSS](#4-intro-to-html-css)
    - [ ] [Responsive Web Design](#5-responsive-web-design)
    - [ ] [HTML & CSS Practice](#6-html-css-practice)
    - [ ] [JavaScript Basics](#7-javascript-basics)
    - [ ] [Document Object Model - practice](#8-document-object-model-practice)
  
 3. **ADVANCED TOPICS**

    - [ ] [Building a Tiny JS World (pre-OOP) - practice](#9-building-a-tiny-js-world-pre-oop-practice)
    - [ ] [Object oriented JS - practice](#10-object-oriented-js-practice)
    - [ ] [OOP exercise - practice](#11-oop-exercise-practice)
    - [ ] [Offline Web Applications](#12-offline-web-applications)
    - [ ] [Memory pair game — real project!](#13-memory-pair-game-real-project)
    - [ ] [Website Performance Optimization](#14-website-performance-optimization)
    - [ ] [Friends App - real project!](#15-friends-app-real-project)
  
![box-shadow-bottom](./markdown-styling/box-shadow-bottom.png)


## GENERAL

### 1. Git and GitHub

***

#### 1.1. Course [Version Control with Git](https://www.udacity.com/course/version-control-with-git--ud123)

[![screenshot-image-link](./task_git_collaboration/Version_Control_with_Git_1.png)

[![screenshot-image-link](./task_git_collaboration/Version_Control_with_Git_2.png)]

During this course I:

- Learned from zero Git. All the commands were new for me. I enjoyed studying Git very much.
- Learned basic concepts of git (working directory, index, repository areas and their workflow). Got acquainted with the contents of the hidden `.git` folder. Learned how to add files into `.gitignore` manually and with using special symbols.
- Updated git version and checked config info.
- Discovered new terminal commands:
  | Command | Usage |
  | --- | --- |
  | `rmdir` | remove directory |
  | `ls -a` | list hidden files |
  | `mkdir -p parent/child` | create nested directories with single command |
- Repeated and used next git commands:
  | Command | Usage |
  | --- | --- |
  | `git log`, `git show` | inspecting commits |
  | `git rm --cached <filename>` | unstaging files |
  | `git diff` | difference between working directory and last commit |

- Worked with git documentation to find neccessary command options.
- Got acquainted with Less command line pager and it's commands for navigating through the history of commits:
  | Key | Usage |
  | --- | --- |
  | `j` or `↓` | scroll :arrow_down: by a line |
  | `d` | scroll :arrow_down: by a half-page |
  | `f` | scroll :arrow_down: by a page |
  | `k` or `↑` | scroll :arrow_up: by a line |
  | `u` | scroll :arrow_up: by a half-page |
  | `b` | scroll :arrow_up: by a page |
- Learned and used commands for commits investigation:
  | Command | Usage |
  | --- | --- |
  | `git log --oneline`, `git log --stat`, `git log --patch/-p`, `git log --stat -patch` | display all commits i  certain form |
  | `git log --oneline <commit-ref>`, `git log --stat <commit-ref>`, `git log -p <commit-ref>` | display commit  from the point where specific commit placed |
  | `git show <commit-ref>`, `git show --stat <commit-ref>`, `git show --stat --patch <commit-ref>` | ge  specific commit |
- Realized that each commit should make a change to just **ONE** aspect of the project. **Single-unit change** principle.

  > Work on one change first, commit that, and then change the second one.  
  >  
  > The best way that I've found to think about what should be in a commit is to think, "What if all changes  introduced in this commit were erased?". If a commit were erased, it should only remove one thing.
- Learned about commit naming:
  | Do :white_check_mark: | Don't :x: |
  |----|----|
  | make it *short* | don't use *and* |
  | response *what* was done | don't tell *how* and *why* it was done |
  
  > The best way that I've found to come up with a commit message is to finish this phrase, "This commit will...". However, you finish that phrase, use that as your commit message.
- Learned about entities used for organizing commits structure:
  | Entity | Description |
  | --- | --- |
  | tags  | static commit pointers  |
  | branches | dynamic commit pointers |
  | `HEAD` | dynamic branch/commit pointer |
- Practiced in creating and deleting tags/branches and switching between branches. Practiced in linking tags and branches with specific commits. Practiced working with multiple feature branches.
- Learned useful commands for work with branches:
  | Command | Usage |
  | --- | --- |
  | `git checkout -b <new-branch-name>` | create branch and switch to it |
  | `git checkout -b <new-branch-name> <existing-branch-name>` | create branch pointing on another  branch's las  commit and switch to it |
  | `git checkout -b <new-branch-name> <SHA>` | create branch pointing on specific commit and  switch to it |
  | `git log --oneline/--patch/--stat --all --graph` | log commits for all branches using graph |
- Executed fast-forward and regular merges using `git merge <other-branch>` command. If we merge 2 branches commits will be added to the one which under `HEAD` pointer (current branch). `Branch we merge into === current branch`.
  > When we merge, we're merging *some other branch* ***into the current (checked-out) branch***.
  >
  > Fast-forward merge – the branch being 'merged in' must be ahead of the current branch. Current branch'    pointer will just be moved forward to point to the same commit as the other branch.
  >
  > Regular merge - two divergent branches are combined, merge commit is created.
- Forced and resolved merge conflict. Realized thay Git tracks lines in files and merge conflict happens when the same lines are changed in separate branches.
- Learned how to undo changes using commands:
  - **git amend** - replace last commit with new one (new one created by changing last commit's index).
    | Command | Usage |
    | --- | --- |
    | `git commit --ammend -m='...'` | update recent commit message if index is empty since last   commit |
    | `git add <updated-file>` -> `git commit --amend -m='...'` | add changes made after commit to index -  update recent commit content and message |
    | `git add <updated-file>` -> `git commit --amend --no-edit` | add changes made after commit to index -  update recent commit content |
  - **git revert** - create new commit with removed last/specific commit's changes. If 'a' character is added i  commit A, if Git reverts commit A, then Git will make a new commit where 'a' character is deleted.
    | Command | Usage |
    | --- | --- |
    | `git revert <commit-ref> -m='...'` | create new commit with removed/reversed changes made within define  commi |  
  - **git reset** :warning: - erase commit from memory by moving HEAD and current branch pointer to anothe  commit. Erased commit's fate defined by `--mixed` (default), `--soft` and `--hard` options. It is better t  create backup branch for using this command.
    | Command | Usage |
    | --- | --- |
    | `git reset <commit-ref>` | move HEAD and current branch pointer to defined commit, place erased commit i  working directory |
    | `git reset <commit-ref> --soft` | move HEAD and current branch pointer to defined commit, place erase  commit in index |
    | `git reset <commit-ref> --hard` | move HEAD and current branch pointer to defined commit, place erased i  trash area |
- Learned that to reference commits we can use not only SHA/tags/branches/HEAD, but also relative path. All types of references can be integrated in commands where indicator of specific commit needed.
  
**Most of all in the course I liked presence of simple analogies  and visualizations of how git workflow works.**

   I discovered for myself [GitHub Learning Lab](https://lab.github.com/) and i will used it to practise my skills.  For me visual representation of any thing is much better than any amount of text material.

***

### 2. Linux CLI and Networking

***

#### 2.1 Course [Linux Survival (4 modules)](https://linuxsurvival.com/linux-tutorial-introduction/)


- **What was new**
Everything was new for me. Is my first Linux study. It wasn't easy but for that I have my notes here.
  - `more <file>` to show file content.
  - `mv <any> <dir>` to move file/directory in another directory.
  - `mv <any> <new-name>` to rename file/directory.
  - `cp <file> <dir>`/`cp -r <dir> <dir>` to copy file/directory in another directory.
  - `pwd` to show current directory.
  - `rm <file>`/`rmdir <dir>`/`rm -r <dir>` to remove file/empty directory/non-empty directory.
  - `ls -l` for detailed file listing.
  - `chmod` for managing security permissions on files.
  - `~` as shortcut for current user home directory, `~<user-id>` as shortcut for another user home directory, `.` as a shortcut for current directory, `..` as a shortcut for parent directory.
  - `man <command>`, `man man` for cli commands searching.
  - `cd` with no arg for navigating to current user home directory.
  - `ps`/`pr aux` to show process status/list all processes.
  - `<com-1> | <com-2>` to send output from one command as input to another command (pipe commands).  For instance, `ps aux | grep <text>` means:
    1. execute `ps aux` and instead of logging its result in terminal pass it as arg to the next command.
    2. execute `grep <text>` with `<arg>` where arg is the one which received from previous command (if this command wouldn't be part og commands pipe, we should specify arg manually - `grep <text> <arg>`).
  - `grep <text> <file>` to show lines of the containing defined text.
  - `kill <process-id>`, `kill -9 <process-id>` to kill processes.

- **What surprised**
  I was surprised that absolute path starts from `/`. I always used relative paths starting with `./` and used to think that `./` === `/`. By making some experements in terminal i understood that *absolute path* starts from  `/` and *relative path* starts from `./` or right from file/directory name. I also realized that each command has both input and output where input - set or arguments defined with command and output - content printed in terminal. 
- **What will be used in practice**
  I will use most of the commands i acquainted with because it represents 20% of commands which can cover up to 80% of work to do in terminal.

![linux-screenshot](task_linux_cli/Screenshot_1.png)
![linux-screenshot](task_linux_cli/Screenshot_2.png)
![linux-screenshot](task_linux_cli/Screenshot_3.png)
![linux-screenshot](task_linux_cli/Screenshot_4.png)
![linux-screenshot](task_linux_cli/Screenshot_5.png)


***

#### 3.1 Course [GitHub & Collaboration](https://classroom.udacity.com/courses/ud456)

- **What was new for me**
 - I learned that local representation of remote branch is called 'tracking branch'.
 > tracking branch is local branch which represents remote branch.
 
 > origin/master in the local repository is called a *tracking branch* because it's tracking the progress of the master branch on the remote repository.

 - I compared fork vs clone. Fork is copy of somebody's repo on your GitHub account (you owner of copy, you can link local repo to it and push changes in it). Clone is just way to link you local repo with any GitHub repository (if you linked to somebody's repo, you can only fetch changes and create pull requests for making changes). Simply saying, forking is copying on the GitHub level, cloning - on local machine level.
 - I learned how to keep local, origin and upstream repos sync. Pull changes from upstream in local -> push changes from local in remote.


I learned new information about forks.
To get commits from a source repository into forked repository on GitHub I need to:

* Get the cloneable URL of the source repository
* Create a new remote with the git remote add command
* Use the shortname upstream to point to the source repository
* Provide the URL of the source repository
* Fetch the new upstream remote
* Merge the upstream's branch into a local branch
* Push the newly updated local branch to your origin repo

I was surprised how many different and useful commands that I can do with git rebase:

- use `p` or `pick` – to keep the commit as is
- use `r` or `reword` – to keep the commit's content but alter the commit message
- use `e` or `edit` – to keep the commit's content but stop before committing so that you can:
  * add new content or files
  * remove content or files
  * alter the content that was going to be committed
- use `s` or `squash` – to combine this commit's changes into the previous commit (the commit above it in the list)
- use `f` or `fixup` – to combine this commit's change into the previous one but drop the commit message
- use `x` or `exec` – to run a shell command
- use `d` or `drop` – to delete the commit.

I'm sure that most of the commands I will use in future.

![Git Collaboration Screenshot](task_git_collaboration/GitHub_collaboration.png)