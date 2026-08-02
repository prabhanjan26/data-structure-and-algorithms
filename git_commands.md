#When want to create a new project.
git init
git add .
git commit -m "Initial commit"

git branch -M main

git remote add origin <repo-url>

git push -u origin main

#Common work flow
git add .

git commit -m "comments"

git push

#Some useful commands
git status            # Check changes

git add .             # Stage all changes

git commit -m "msg"   # Save changes locally

git push              # Upload to GitHub

git pull              # Download latest changes

git log --oneline     # View commit history

git remote -v         # Show connected repository

git branch            # Show current branch