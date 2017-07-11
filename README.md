# learnGit
Learn git form lynda.com
## What is Git?
### Understanding version control
  - Keep track of change
    * Compare what changes in new version
    * Version 1, 2, 3,...
  - Version control system(VCS) and Source code management(SCM) use manage source code. They can definitely dealt with version control
  ### The history of Git
  - Source code control system( SCCS)
    * 1972, closed source, free in Unix
    * Save original document and update version. Update version were shown by snapshot what the changes were.
   - Revision control system (RCS)
      * 1982, open source
      * Speed and smarter SCCS
   - Concurrent versions system(CVS)
      * 1986-1990, open souce
      * Can work multiple file, same time, same file and anywhere
   - Apache subversion(SVN)
       * 2000
       * Can rename, delete change easier. It can know what file changed.
   - BitKeeper SCM
      * 2000, closed source
    - Git
      * 2005, open soucre
      * Compatible woth most platforms
    ### Who use Git
      - Tracking file
      - Share changes with conllaboration
      - Programing developer
## Install Git
### Configuring Git
- Set name and email in Git: 
  > git config --system user.name "Your name"
- Show name and email in Git: 
  > cat .gitconfig
### Git help
   - Guide use git: 
      > git help
   - Show commit log: 
      > git help log
   - Forward: F ; Backward: B ; Quit: Q
## Getting started
### Initializing a repository
- Initializing a repository: 
  > git init
- Show file in foder:
  > ls -la
- Add all of files in the current directory:
  > git add . 
- Commit with a message: 
  > git commit -m "Initial commit"
- Show information of repository
  > git log
- Show info of repository with conditions: 
  > git log --since==2017-07-10
  
  > git log --author=="name"
  
  > git log --grep=="message"
## Git concepts and architecture
### The three trees achitecture
  - Working-> staging index-> repository : add -> commit 
### Workflow
  - Working-> staging index-> repository
  - v1
  - _________v1
  - __________________________v1
  - v2_______v1_______________v1
  - _________v2_______________v1 v2
### Using hash value ( SHA-1)
  - Git use algorithm Hash to get ID for each file. So each file have an unique ID.
  - There is HEAD pointer always point to the tip of the current branch in our repository.
## Making changes to files
  - Show status of repository:
    > git status
  - Compare file in working and in repo: 
    > git diff
  - Compare file in stage and repo:
    > git diff --staged
  - Delete file:
    > git rm #nameFile
  - Rename file not in command: add that file to "staging index" then remove old file. Enter "git status" if file have more 50% same, git will know that is rename.
  - Rename file: 
    > git mv #file1 #file2
  - Add and commit file by one step: 
     > git commit -am "Message"
## Undoing changes
  - To undo from staged:
    > git checkout -- #nameFile
  - Amending commits (last commit):
    > git commit --amend -m "message"
  - To see the file from the old commit
    > git checkout ID_Hash nameFile
  - Anything that was added will be deleted, anything that was deleted will be added back in again, and anything that was modified will be changed back to its previous state:
    > git revert / git reset
  - Does not change staging index or working directory:
    > git reset --soft
  - Changes staging index to match repository, does not change working directory
    > git reset --mixed (defalt)
  - Changes staging index and working directory to match repository
    > git reset --hard
  - Delete file untracked:
    * Show git will delete what: 
      > git clean -n
    * Git sure delete that file showed:
      > git clean -f
## Ignoring file
### How to ignore: 
  - Onpen place to ignore which need ignore:
    > nano gitignore
  - Then enter which file/foder ignore:
    > Ex: *.txt asset/video ... 
### Ignore tracked file
  - After commit file to repository, we ignore file as a normal file. But file still in staging index so file will be tracked. To really ignore that file, we remove from staging index.
  - Remove file from the staging index, not repository:
    > git rm --cached <file>
### Ignore file in global
  - To ignore file global. It mean when many people work together a project and use same repository. We will ignore file for all user like as:
    * Add all file in ".ignore_global"
    * Then enter:
      > git config --globel core.excludesfile ~/.gitignore_global" 
### Tracking empty directories
  - Atually, git don't care abou directories. Git only track file which tracked and directories like path to detect file. So to tracking directories, we need add a new file(small) and ignore it. Following that way, git will tracking directories.
## Navigating the commit tree
### Tre-ish
  - Full SHA-1 hash
  - Short SHA-1 hash
    * at least 4 char
    * unambiguous ( 8-10 char)
  - HEAD pointer
  - Branch reference, tag reference
  - Ancestry
  - Parent commit
    * HEAD^, acd2f3g4^, master^
    * HEAD~1, HEAD~
   - Grandparent commit
    * HEAD^^, d34rw43^^
    * HEAD~
### Exploring tree listings
  - Show list tree
    > git ls-tree HEAD
    * blod: is file
    * tree: is directory
    > git ls-tree <name>/<path>
### Getting more from the commit log
  - Show commit in one line:
    > git log --oneline
  - Show commit of a repo
    > git log IDhash
  - Show what changed in each one:
    > git log --stat --summary
  - More...
### Compare commits
  - Comparing file:
    > git diff IDhash
  - between two file:
    > git diff IDhash..nameFile
## Branching
### Branching overview
  - Branches are cheap
    * Try new ideas
    * Ioslate feature or sections of work
  - One working directory
  - Fast context switching
### Create branch
  - Create branch:
    > git branch <name file>
  - Switching branches
    > git checkout <nameBranch>
  - Check switched? :
    > cat .git/HEAD
      * ref: refs/heads/master -> if head in master
      * ref: refs/heads/new_branch -> if head in branch
   - -b means both created and switch at the same time:
    > git checkout -b <name branch>
### Compare branch
  - Compare:  
    > git diff master..new_feature
    > git diff <branch1>..<branch2>
    > git diff --color-words <branch1>..<branch2>
  - Merge among branches: following step
    > git branch --merged
    > git checkout <branch1>
    > git branch --merged
    > git checkout <branch2>
    > git branch --merged
### Renaming branches
  - Renaming branches:
    > git branch -m <branch1> <branch2>
### Deleting branches
  - To see Git what say: 
    > git branch -d <branch_to_delete>
  - Deleting branches:
    > git branch -D <branch_to_delete>
## Merging code
  - Merging branch
    > git branch --merged
  - Fast-forward merged and true merged
### Merged conflicts
  - A conflict occurs when there are two changes to the same line or set of lines in two different commits. 
  - Merged conflicts when Git don't know to choose which between two file tto merge.
  - Resolving merge conflicts:  
    * Abort merge
      > git merge --abort
    * resolve the conflicts manually
    * Use a merge tool 
  - Strategies to reduce merge conflicts
    * Keep lines short
    * Keep commits small and focused
    * Beware stray small and focuesd
      - spaces, tabs, line returns
    * Merge ofen 
    * Track changes to master
    
    
    
    
    
    
  
