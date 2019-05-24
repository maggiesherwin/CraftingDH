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
    17  nano testing.md
    18  ls
    19  cp testing.md Home/maggiesherwin/blog-log/blog-log (did not work) (the H in home is capitalized, and I believe that that was the issue)
    20  cd cp testing.md Home/maggiesherwin/blog-log/blog-log
    21  cd Home/maggiesherwin/blog-log/blog-log
    22  cd Home/maggiesherwin/blog-log/
    23  cd
    24  cd Home/maggiesherwin/blog-log/
    25  nano test.md
    26  cp test.md CraftingDH (didn't work)
    27  cd CraftingDH
    28  ls
    29  cp test.md cp testing.md hello-world
    30  cp test.md hello-world (Still not working)
    31  pwd (wow look I found out how to find the proper path I needed!!)
    32  cd
    33  cd /home/maggiesherwin/CraftingDH/week_3
    34  cd
    35  cd hello-world
    36  ls
    37  cp aaahhh.md /home/maggiesherwin/CraftingDH/week_3 (IT WORKED!!!)
    38  cd
    39  cd /home/maggiesherwin/CraftingDH/week_3
    40  ls (ITS THERE!!)
