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

    
