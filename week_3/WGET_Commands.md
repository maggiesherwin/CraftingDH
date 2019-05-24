# WGET Commands for pulling images from Collections Canada
    1  mkdir war-diary
    2  cd war-diary
    3  nano urls.py
    4  python urls.py
    5  ls (They are all there!)
    6  nano urls.txt
    7  wget -i urls.txt -r --no-parent -nd -w 2 --limit-rate=100k
    8  ls
    9  history > WGET_Commands.md
