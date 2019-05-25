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
- Transcribed the page
- Searched for HTML entities so I could use long dahses and parentheses. 
- Had a lot of trouble finding information about people mentioned
	- Finally found a worldcat entry for Lt. Hall, but could not find anything about the mentioned "Mr. Duff"
- Recieved an error when first trying to load the .xml file
	- I was using HTML enteties which do not work in .xml files
- Found the correct codes for special characters [here] 
- It loaded!! And the text encoding worked as well!
### APIs
- Went through all of the APIs
- Came across issues when trying to input query parameters
- Found the solution for some of the binders, but not all
### Mining Twitter
- Relatively straightforward
- Word cloud would not load in chrome, but when I tried it in Firefox it worked
### Tesseract
    1  mkdir ocr-test
    2  cd ocr-test
    3  sudo apt-get install tesseract-ocr
    4  sudo apt-get install imagemagick
    5  apt-get update
    6  sudo apt-get update
    7  sudo apt-get install imagemagick
    8  convert -density 300 ~/war-diary/e001518087.jpg -depth 8 -strip -background white -alpha off e001518087.tiff
    9  tesseract e001518087.tiff output.txt (omg it is SO bad)
- Installed all dependencies
- Ended up updating EVERYTHING (took about 2 hours)
```
1 sudo apt-get install libcurl4-gnutls-dev
2 sudo apt-get install libmagick++-dev
3 sudo apt-get install libtesseract-dev
4 sudo apt-get install libleptonica-dev
5 sudo apt-get install tesseract-ocr-eng
6 sudo apt-get install libpoppler-cpp-dev
7 sudo apt-get update
8 sudo apt-get upgrade
9 history > upgradingeverything.md
```
- Ran the script and opened the RStudio file (Somehow even worse than the command line one??)
- Made screenshots of the text files and ran them both through their respective programs
- Both were bad again, but the RStudio one was better
- Trying to batch convert all the images
- Fell into trouble with this script, but was able to change it by adding a ~ to `"~/war-diary"`
### DID NOT WORK
```
    library(magick) 
    library(magrittr)
    library(pdftools)
    library(tesseract)

    dest <- "/war-diary"
    myfiles <- list.files(path = dest, pattern = "jpg", full.names = TRUE)

    # improve the images
    # ocr 'em
    # write the output to text file

    lapply(myfiles, function(i){
        text <- image_read(i) %>%
        image_resize("3000x") %>%
        image_convert(type = 'Grayscale') %>%
        image_trim(fuzz = 40) %>%
        image_write(format = 'png', density = '300x300') %>%
        tesseract::ocr()

    outfile <- paste(i,"-ocr.txt",sep="")
    cat(text, file=outfile, sep="\n")

    })
```

### DID WORK
```
    library(magick) 
    library(magrittr)
    library(pdftools)
    library(tesseract)

    dest <- "~/war-diary"
    myfiles <- list.files(path = dest, pattern = "jpg", full.names = TRUE)

    # improve the images
    # ocr 'em
    # write the output to text file

    lapply(myfiles, function(i){
        text <- image_read(i) %>%
        image_resize("3000x") %>%
        image_convert(type = 'Grayscale') %>%
        image_trim(fuzz = 40) %>%
        image_write(format = 'png', density = '300x300') %>%
        tesseract::ocr()

    outfile <- paste(i,"-ocr.txt",sep="")
    cat(text, file=outfile, sep="\n")

    })
```

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

[here]: <https://dvteclipse.com/documentation/svlinter/How_to_use_special_characters_in_XML.3F.html>
