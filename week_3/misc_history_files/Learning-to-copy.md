# Learning to copy a file to a different directory
    1  cd hello-world
    2  ls
    3  cp experiment.md CraftingDH (Did not work)
    4  cd
    5  cd CraftingDH
    6  ls
    7  cd
    8  cd hello-world
    9  cp -F experiment.md CraftingDH (did not WORK)
    10  cp --help
    11  cp -f experiment.md CraftingDH
    12  cd
    13  cd CraftingDH
    14  ls
    15  cd
    16  cd hello-world
    17  nano aaahhh.md
    18  cp aaahhh.md /CraftingDH
    19  cp aaahhh.md /CraftingDH/week_3
    20  cd
    21  cd CraftingDH
    22  cd week_3
    23  pwd (wow look I found out how to find the proper path I needed!!)
    24  cd
    25  cd /home/maggiesherwin/CraftingDH/week_3
    26  cd
    27  cd hello-world
    28  ls
    29  cp aaahhh.md /home/maggiesherwin/CraftingDH/week_3
    30  cd
    31  cd /home/maggiesherwin/CraftingDH/week_3
    32  ls (IT'S THERE!!)
