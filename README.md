# Projects

## About
Version control system, such as Git, is essential in software development, in order to develop applications together as a team. A newcomer could easily be confused about Git at first, but don't worry, here is a tutorial for you.

## Tutorial
Every repository has a master branch. In a team, changes should never be pushed directly to the master branch. Instead, teammates should create branches, which are copies of the master branch, and request pull request to be merged into master. How do we do it? Follow the steps below.

### Creating a branch from master
1. Use the terminal to go to the repository root on your local laptop:
    `cd Projects`

2. In order to keep your local code updated to the latest changes on master, use the following command:
    `git pull`

3. Use `git status` to confirm that you're on master branch. A output of `On branch main` should be shown.

4. Create new branch by using the following command `git checkout -b new-feature`, where `new-feature` is the name for the branch.

5. Using `git status` will show that you are currently in `new-feature` branch.

6. In order to switch to another branch, use either `git checkout master` / `git checkout new-feature` or `git switch`. Keep in mind that you can only `checkout` if all your changes are commited, else use `switch`.

7. Now, you can work on the branch!

### Create a pull request from branch to master

1. First, you need to be on a branch, which you can do by following the guide above. Use `git add .` to add all the changes, made in the repository. If you only want to add a specific file, use `git add mario.c` for example.

2. To commit the changes use `git commit -m "message"`. After executing the command, all your added files will be ready to be pushed.

3. How do I push to the destined branch? Easy. Use the following command `git push origin new-feature`.

4. Go to your github repository ➡ pull requests ➡ open pull request and select `new-feature`.

5. After opening a pull request, you and your teammates will be able to view the codes.

6. If everything is okay, press merge and it will merge changes to the master branch.

7. Finally, remember to switch to master branch with `git checkout master` and pull the changes to your local with `git pull`.

### I have trouble with merging my pull request because my branch is not up-to-date with the master (teammate merged his pull request before me). What should I do?

1. First, you need to pull the latest changes from master with `git pull`. Remember to be on the master branch.

2. Go back to your branch with `git checkout new-feature`.

3. Use rebase `git rebase master`. If your code is not colliding with the latest changes on master, then you do not to resolve the code. The master changes will be automatically added to your pull request.

4. What does resolving code mean? It means you have to manually choose which colliding code, that you want to keep. It's either the code from master branch or your current branch in-progress.

5. After resolving all the necessary code collisions, use `git rebase --continue`. Continue to resolve the code collisions until you are back to your branch by repeating step 4 to 5.

6. If you want to push out your pull request again, use `git push -f origin new-feature`. `-f` force pushes the changes to the remote server (github).

### View all branches

1. Use `git branch -a`. If you want to have all the latest created branches, on remote server, use `git fetch -all`.

### Switch to a existing remote branch

1. Use `git checkout --track origin/new-feature`. `new-feature` would be replaced by the remote branch that you want to connect to.