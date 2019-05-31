# Week 3
## Activities
### Regex & Texas
    1  mkdir regex
    2  cd regex
    3  curl http://archive.org/stream/diplomaticcorre33statgoog/diplomaticcorre33statgoog_djvu.txt > texas.txt
    4  Donwloaded texas.txt and edited it in SublimeText
    5  grep '\b to \b' texas.txt
    6  sed -r -i.bak 's/(.+\bto\b.+)/~\1/g' texas.txt
    7  ls
    8  grep '~' texas.txt > index.txt
    9  sed -r -i.bak 's/(,)( [0-9]{4})(.+)/\2/g index.txt
    10  sed -r -i.bak 's/(,)( [0-9]{4})(.+)/\2/g' index.txt
    11  sed -r -i.bak 's/~//g' index.txt
    12  nano index.txt
    13  sed -r -i.bak 's/(to\b)/,/g' index.txt
    14  nano index.txt
    15  too many spaces...
    16  sed -r -i.bak 's/ , /, /g' index.txt
    17  nano index.txt
    18  fixed it!
    19  sed -r -i.bak 's/c6|c\^/ce/g' index.txt
    20  nano index.txt
    21  sed -r -i.bak 's/ Alce / Alcee /g' index.txt
    22  grep -r ".+,.+,.+," index.txt
    23  nano index.txt (Manually fixing stuff)
    24  cp index.txt cleaned-correspondence.csv
    25  history > regex.md

THIS WORKED
`sed -r -i.bak 's/(,)( [0-9]{4})(.+)/\2/g' index.txt`

THIS DID NOT
`sed -r -i.bak 's/(,)( [0-9]{4})(.+)/\2/g index.txt` Missed that one extra '!
### Open Refine
- Loaded my `.csv` into Open Refine
- Set facet for sender and reciepeint to `text facet`
- Went through and merged clusters
- Noticed that some are not showing up as clusters
- Reordered the list by sender's name to see if I can group any names together manually
- Found all of the indirectly named people and found their full names, and changed their entry to that
- Using the nearest neighbour method in Open Refine really helped to find similar entries
- Got down to 141 senders and 137 recipients
- Removed extra whitespace `triangle > edit cells > common transformations > trim leading and trailing whitespace`
- Learned NOT to use the common transformations to turn dates into `dates` as they become almost unreadable. 
### Capstone exercise
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi aliquet mi nisl, malesuada mollis arcu pharetra sit amet. Mauris non nibh orci. Fusce quam nibh, venenatis eget erat ut, dapibus venenatis sapien. Suspendisse laoreet nibh in molestie finibus. Fusce lorem dui, volutpat ac lacus et, lobortis tristique sem. Phasellus vulputate augue vel aliquam eleifend. Vestibulum semper convallis sapien a ultrices. Praesent tincidunt cursus faucibus. Sed finibus lorem cursus sodales iaculis. Aliquam ut augue vel velit auctor euismod. Nulla et neque mi. Vestibulum non dolor in ante suscipit dapibus nec non dolor.
###  Named Entity Recognizer
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi aliquet mi nisl, malesuada mollis arcu pharetra sit amet. Mauris non nibh orci. Fusce quam nibh, venenatis eget erat ut, dapibus venenatis sapien. Suspendisse laoreet nibh in molestie finibus. Fusce lorem dui, volutpat ac lacus et, lobortis tristique sem. Phasellus vulputate augue vel aliquam eleifend. Vestibulum semper convallis sapien a ultrices. Praesent tincidunt cursus faucibus. Sed finibus lorem cursus sodales iaculis. Aliquam ut augue vel velit auctor euismod. Nulla et neque mi. Vestibulum non dolor in ante suscipit dapibus nec non dolor.
### Counting and Mining Data with Unix
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi aliquet mi nisl, malesuada mollis arcu pharetra sit amet. Mauris non nibh orci. Fusce quam nibh, venenatis eget erat ut, dapibus venenatis sapien. Suspendisse laoreet nibh in molestie finibus. Fusce lorem dui, volutpat ac lacus et, lobortis tristique sem. Phasellus vulputate augue vel aliquam eleifend. Vestibulum semper convallis sapien a ultrices. Praesent tincidunt cursus faucibus. Sed finibus lorem cursus sodales iaculis. Aliquam ut augue vel velit auctor euismod. Nulla et neque mi. Vestibulum non dolor in ante suscipit dapibus nec non dolor.
