   ## Learning to clone, branch, change, commit, and push .git repositories
   
    1  git clone https://github.com/maggiesherwin/hello-world.git
    2  ls
    3  cd hello-world
    4  git checkout -b experiment
    5  git push origin experiment
    6  nano test1.md
    7  nano test2.md
    8  git add -A
    9  git status
    10  git push origin experiment
    11  git push -u origin experiment
    12  git status
    13  git push origin experiment
    14  ls
    15  nano experiment.md
    16  ls
    17  git commit
    18  git push origin experiment
    19  git add -A
    20  git commit
    21  git push origin experiment
    22  git remote add upstream https://github.com/maggiesherwin/hello-world.git
    23 git pull origin master
    24  cd
    25  history > recentcommands.md
