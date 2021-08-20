# Software_Engineering_Practices

## Version Control

Step 1: Andrew commits his changes to the documentation branch, switches to the development branch, and pulls down the latest changes from the cloud on this development branch, including the change I merged previously for the friends group feature.
Commit the changes on the documentation branch
git commit -m "standardized all docstrings in process.py"

Switch to the develop branch

`git checkout develop`

Pull the latest changes on the develop branch down

`git pull`

Step 2: Andrew merges his documentation branch into the develop branch on his local repository, and then pushes his changes up to update the develop branch on the remote repository.
Merge the documentation branch into the develop branch

`git merge --no-ff documentation`

Push the changes up to the remote repository

`git push origin develop`

Step 3: After the team reviews your work and Andrew's work, they merge the updates from the development branch into the master branch. Then, they push the changes to the master branch on the remote repository. These changes are now in production.
Merge the develop branch into the master branch

`git merge --no-ff develop`

Push the changes up to the remote repository

`git push origin master`