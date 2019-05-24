# Programming Historian WGET tutorial
    1  mkdir wget-activehistory
    2  cd wget-activehistory
    3  wget http://activehistory.ca/papers/
    4  wget -r --no-parent -w 2 --limit-rate=20k http://activehistory.ca/papers/
    5  ls
    6  history > WGET_CommandsTutorial.md
