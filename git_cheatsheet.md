# Notes from Foundations: Git Basics
## Cheetsheet for commonly used git commands
Commands related to a remote repository
- `git clone git@github.com:<user_name>/<repository_name>.git`
- `git push` or `git push origin main` (Both accomplish the same goal in this context)
Commands related to the workflow
- `git add .`
- `git commit -m "A message dsecribing what you have done to make this snapshot different"
Commands related to checking status or log history
- ` git status`
- ` git log`
The basic Git syntax is `program | action | destination`
For example, 
- `git add .` is read as `git | add | .`, where the period represents everthing in the current directory
- `git commit -m "message"` is read as `git | commit -m | "message"`
- `git status` is read as `git | status | (no destination)`
## Git Best Practices
Atomic Commits:
- includes changes related to only one feature or task of your program
- Makes it easier to revert breaking changes without losing other work
- Enables you to write better commit messages
## Knowledge Check
How do you create a new repository on GitHub
- You click create repository from your repo list on GitHub
How do you copy a repositry onto your local machine from GitHub
- `git clone git@github.com:<user_name>/<repository_name>.git`
What is the default name of your remote connection?
- origin
Explain what `origin` is in `git push origin main`
- origin is the name of the remote connection
Explain what `main` is in `git push origin main`
- main is the branch that is being pushed to the remote connection
Explain the two stage system that Git uses to save files
- Files that have been changed are in the modified state.
- Adding those files changes them to the staged state
- They can then be committed to create a snapshot
How do you check the status of your current repository?
- Use `git status`
How do you add files to the staging area in git?
- Use `git add <file_name>`
How do you commit the files in the staging area and add a descriptive message?
- Use `git commit -m "message"` or `git commit` to write message in text editor
How do you push your changes to your repository on GitHub?
- Use `git push` 
How do you look at the history of your previous commits?
