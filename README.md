# Script to follow for Git and GitHub class:

## Initialize repo
#### Initialize local repo from already created remote repo (GitHub)
To initialize a local repo from a remote repo we need to clone the remote repo. 

    `git clone https://github.com/josejuanWSB/test_repo.git master`

#### Initialize remote repo from already created local project (in your pc)
To initialize a remote repo in GitHub from a local repo we need to: 

1. Create the repo in GitHub 
2. Initialize local repo 
   
        `git init`

## Push changes to remote repo
It makes all the changes in the local repo be in the remote repo in GitHub

1. Stage all of the files:
   
   ```
   git add .
   ```
_"." is a key for all of the files in the directory_
   
2. Reflect the changes in the local repository (.git directory)
   
        ` git commit -m "First Commit" `
   
3. Push the changes to the remote repository
   
        `git push https://github.com/josejuanWSB/test_repo.git master`

## Pull changes
It synchronizes the remote repo in GitHub to the local repo, making available the last changes made in 
the remote repo to the local repo.

To try it you can change something in the remote repo by the GitHub editor (right corner inside of a file)
or someone of your team can make changes and then you can make a pull.

    `git pull https://github.com/josejuanWSB/test_repo.git master`
    
    
## Git merge/solving conflicts

When 2 developer introduce changes in the same line of code this can generate problems.

To reproduce this scenario you can:

I- Change a line in the remote repo and make a commit by GitHub editor, like before.

II. Change the same line in the local repo by adding something different than in the remote repo

III. Try to pull:

    `git pull https://github.com/josejuanWSB/test_repo.git master`


IV. If it fails, then:

    1. First you need to add and reflect the changes
    2. Then:
        `git add .
        git commit -m "Committing on local repo"
        ## If meanwhile pulling it prompts the vi/unix command line editor pres -> :wq (save and exit)
        git pull https://github.com/josejuanWSB/test_repo.git master`

V. There is a conflict, that needs to be solved manually.

    1. Go to the file and delete the comments by git and the code that you don't want
    2. Then:

        `git add .
        git commit -m "Conflict resolved"
        git push https://github.com/josejuanWSB/test_repo.git master`

        3. If now you try to git pull, it will display: "Already up to date"