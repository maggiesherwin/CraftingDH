# Week 3
## Activities
### The Dream Case
    1  cd /home/maggiesherwin/CraftingDH/week_3
    2  git pull (updating my repo on DHBox)
    3  ls
    4  nano the-dream-case.md
    5  git add -A
    6  git commit
    7  git oush (misspelled that!)
    8  git push
    9  nano the-dream-case.md (editing the file to make it look nicer)
    10  git add -A
    11  git commit
    12  git push (pushing my updates to the repo)
    13  history > making-and-pushing.md

### Wget
#### Programming Historian Tutorial
	1  mkdir wget-activehistory
	2  cd wget-activehistory
	3  wget http://activehistory.ca/papers/
	4  wget -r --no-parent -w 2 --limit-rate=20k http://activehistory.ca/papers/
	5  ls
	6  history > WGET_CommandsTutorial.md
#### WGET Commands for pulling images from Collections Canada
    1  mkdir war-diary
    2  cd war-diary
    3  nano urls.py
    4  python urls.py
    5  ls (They are all there!)
    6  nano urls.txt
    7  wget -i urls.txt -r --no-parent -nd -w 2 --limit-rate=100k
    8  ls (ALL 80 WERE THERE!)
    9  history > WGET_Commands.md
	
	
### TEI
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque vitae fermentum mauris. Morbi ac purus eget lorem congue tincidunt. Praesent in massa vulputate, pretium massa ac, aliquet nulla. Suspendisse condimentum nisl in sapien mattis, nec ullamcorper ipsum elementum. Suspendisse potenti. Aenean mattis sapien non vulputate dictum. Praesent aliquam ligula non est pulvinar posuere. Morbi faucibus est nec turpis ultrices vehicula. Duis bibendum felis tellus, at sodales enim congue quis. Nam imperdiet, nibh suscipit tempus consequat, nisi diam sagittis arcu, eu cursus lectus urna sed ligula. Nunc pharetra orci molestie nunc finibus, at eleifend ligula dictum.
### APIs
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque vitae fermentum mauris. Morbi ac purus eget lorem congue tincidunt. Praesent in massa vulputate, pretium massa ac, aliquet nulla. Suspendisse condimentum nisl in sapien mattis, nec ullamcorper ipsum elementum. Suspendisse potenti. Aenean mattis sapien non vulputate dictum. Praesent aliquam ligula non est pulvinar posuere. Morbi faucibus est nec turpis ultrices vehicula. Duis bibendum felis tellus, at sodales enim congue quis. Nam imperdiet, nibh suscipit tempus consequat, nisi diam sagittis arcu, eu cursus lectus urna sed ligula. Nunc pharetra orci molestie nunc finibus, at eleifend ligula dictum.
### Mining Twitter
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque vitae fermentum mauris. Morbi ac purus eget lorem congue tincidunt. Praesent in massa vulputate, pretium massa ac, aliquet nulla. Suspendisse condimentum nisl in sapien mattis, nec ullamcorper ipsum elementum. Suspendisse potenti. Aenean mattis sapien non vulputate dictum. Praesent aliquam ligula non est pulvinar posuere. Morbi faucibus est nec turpis ultrices vehicula. Duis bibendum felis tellus, at sodales enim congue quis. Nam imperdiet, nibh suscipit tempus consequat, nisi diam sagittis arcu, eu cursus lectus urna sed ligula. Nunc pharetra orci molestie nunc finibus, at eleifend ligula dictum.
### Tesseract
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque vitae fermentum mauris. Morbi ac purus eget lorem congue tincidunt. Praesent in massa vulputate, pretium massa ac, aliquet nulla. Suspendisse condimentum nisl in sapien mattis, nec ullamcorper ipsum elementum. Suspendisse potenti. Aenean mattis sapien non vulputate dictum. Praesent aliquam ligula non est pulvinar posuere. Morbi faucibus est nec turpis ultrices vehicula. Duis bibendum felis tellus, at sodales enim congue quis. Nam imperdiet, nibh suscipit tempus consequat, nisi diam sagittis arcu, eu cursus lectus urna sed ligula. Nunc pharetra orci molestie nunc finibus, at eleifend ligula dictum.
### Figuring out how to copy a file to a different directory
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
### Connecting my Repo to my DHBox
List of commands I used to connect my GitHub Repository to my DHBox

	1 git clone https://github.com/maggiesherwin/CraftingDH.git
	2  cd CraftingDH
	3  cd week_3
	4  nano History.md
	5  git add -A
	6  git commit
	7  git push
	8  history > Connecting-Repo.md

