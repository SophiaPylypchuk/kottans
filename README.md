# kottans-frontend

## Repository dedicated to participation in [Kottans frontend course](https://github.com/kottans/frontend)
## My progress :rocket:

 1. **GENERAL**
    - [x] [Git and Github](#1-git-and-github)
    - [ ] [Linux CLI and Networking](#2-linux-cli-and-networking)
    - [ ] [VCS (hello gitty), GitHub and Collaboration](#3-vcs-hello-gitty-github-and-collaboration)
  
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

[![screenshot-image-link](./markdown-styling/screenshot-image-link.png)](./task_git_intro/version-control-with-git.png)


During this course i:

- Used just learned commands while trying to add 'after-commit' changes to the last commit of this review.
- Realized that 'versions' is not only about highly specialized software such as git and version control to varying degree can be found in almost every program.
- Worked with versions of a document (called revisions) in google docs.
- Repeated and clarified the basic concepts of git (working directory, index, repository areas and their workflow). Got acquainted with the contents of the hidden `.git` folder. Learned how to add files into `.gitignore` manually and with using special symbols.
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
- Installed and first used [HTML linter](https://htmlhint.com/), [CSS linter](https://stylelint.io/), [JS linter](https://eslint.org/). While googling discovered command `npm init -y` for generating empty npm project.
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
  > The best way that I've found to think about what should be in a commit is to think, "What if all chang  introduced in this commit were erased?". If a commit were erased, it should only remove one thing.
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

#### 1.2 Materials [try.gihub.io](https://try.github.io/)

[![screenshot-image-link](./markdown-styling/screenshot-image-link.png)](./task_git_intro/git-branching.png)

- **What was new**
  - I understood that tags used as "milestones"/permanent commit marks/"anchors" in the codebase. I also learned `git describe` to see the nearest tag.
  - I understood `git fetch` aim.
    > remote branches (their representaion on local machine) reflect the state of the remote repositories since you last talked to those remotes (how relevant is your info about remote branches). `git fetch` is the way you talk to these remotes!
  - I acquainted with teams and organizations; GitHub models of collaborative development (Shared repository, Fork and pull); `git log --follow [file]` command to list version history of file.
  - I learned that git don't allow to push changes in remote if the changes you try to push aren't based on the latest varsion of remote branch. So you need to base your work on the most recent version of the remote branch (f.e. through rebasing/merging).
    1. update local representation of the remote with `git fetch`;
    2. rebase our work to reflect the new changes in the remote with `git merge` or `git rebase`;
    3. push synced changes with `git push`.
  Or just use `git pull --rebase`(fetch + rebase) -> `git push`  or `git pull` (fetch + merge) -> `git push`.
  - It was new for me that work from different branches can be combined by not only merging but also by *rebasing* (`git rebase`) which provides linear sequence of commits.

    > Rebasing essentially takes a set of commits, *"copies"* them, and plops them down somewhere else. Take commits of current branch, change them somehow and insert copies somewhere in another branch. No merge conflicts.

    I understood that rebasing is great when you work on a feature branch, and the master branch has been updated. You can rebase start point of feature branch and get all the updates main branch, which would prevent future merging conflicts.

  - I learned  `git rebase -i` for *interactive rebase* (when we use flags to perform some actions like reordering,combining, omitting, editing etc on the commits we're rebasing).
  - I learned `git cherry pick` command which provide ability to include changes of specific commit into current branch.
  - I understood that *Detaching HEAD* just means attaching it to a commit instead of a branch.
  - I discovered that git refs can be used relative to branches/tags.
  - I summed up my knowledge of branche meging:
    - **fast-forward** merge happens when merged branch contains all commits from current branch. No new commit created.
    - **non-fast-forward** merge happens when doesn't contain all commits from current branch. New commit (representing combined changes from 2 parent commits) created on current branch.

- **What surprised**
  - I understood that, for example, `git diff` command is not only about 'get difference between working directory and last commit'. By warying its flags this command can be used to get difference between working area and stage; between working area and specific commit; between different commits; between different trees and much more. While inspecting git documentation for different command i realized that each well-known git command is much more that we read about it in tutorials.
  - I also liked a thought that branches are simply pointers to a specific commit and nothing more. I sure it's better to think of branch not as about line but as about dynamic end point which can form line of linked commits (pointed commit + it's parents) and from which specific set of commits can be reached. Each commit is specific context and by moving pointer we can switch between contexts and change the working directory content in one click.
  - I discovered easy way to reassign branch pointer to another commit - `git branch -f master HEAD~3`.

- **What will be used in practice**
  - 'single-unit-change per commit' approach (no more combined commits!).
  - [Git playground](https://learngitbranching.js.org/) to recheck my understanding of already known commands or to understand new ones.
  - `git rebase` with its flags for interactive rebasing and `git cherry-pick` to copy a series of commits below HEAD.
  - `git fetch` to fetch changes from remote and udpate local representation of the remote.
  - `git reflog` to inspect repository changes history and know what to reset if needed.
  - `git branch -f <branch> <commit-ref>` to reassign branch pointer to another commit.
  - `git checkout <commit-ref>` to reassign HEAD pointer to commit.
  - `git pull` (fetch and a merge).
  - `git pull --rebase` (fetch and a rebase, creates linear commits history).

- **General overview**
  Content of this materials wasn't new for me at all. It was rather repetition of what i learned before and ability to check how well structured and 'close to real picture' are my knowledge. But while investigating extra materials i found many new new commands and practices to use. I understood that principle of 'single unit change per commit' should be followed for not only commits history readability and transparency, but also for ability to roll back specific changes with no influence on other parts of code. It is espesially important for me because in my previous pet projects i used to combine changes of different parts in single commits (shame on me :no_mouth:). I also clarified confusion about 'pull request' and 'git pull'. Git pull request is **request** for merge changes in some branch on remote. `Git pull` is **command** (combination of `git fetch` + `git merge`) which fetches changes from remote branch and automatically merges this changes in local branch if needed.

  > Pull request - is a *place to compare and discuss* the differences introduced on a branch with reviews, comments, integrated tests, and more.
  
   I discovered for myself [GitHub Learning Lab](https://lab.github.com/) and i will used it to practise my skills (i already improved using of relative refs here). I also rediscovered [Git playground](https://learngitbranching.js.org/) (actually i found this resource earlier while searching for online environment for executing git commands). For me visual representation of any thing is much better than any amount of text material.

***