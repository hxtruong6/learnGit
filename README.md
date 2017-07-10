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
   - Format: F ; Backward: B ; Quit: Q
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
  - To undo:
    > git checkout -- #nameFile
  - Amendind commits (last commit):
    > git commit --amend -m "message"
  - To see the file from the old commit
    > git checkout ID_Hash nameFile
  - Undo any undesired changes from old commit:
    > git revert / git reset
  - Undo multiple commit:
    > 
   
