#### The Dream Case
[Epigraphic Database Heidelberg]

[Commwealth War Graves Commission, Find War Dead]

- Explore both databases. 
- Perform a search of interest to you. 
- In the case of the epigraphic database, if you've done any Latin, try searching for terms related to occupations; or you could search Figlina.
- In the CWGC database, search your own surname. Download your results. You now have data that you can explore!
- Using the Nano text editor in your DH Box, make a record (or records) of what you searched, the URL for your search and its results, and where you're keeping your data.
- Lodge a copy of this record in your repository.
#### Wget
##### Part 1
- `mkdir wget-activehistory`
- `cd wget-activehistory`
- `wget http://activehistory.ca/papers/`
- After some initial messages, you should see the following (figures, dates and some details will be different, however):
```
Saving to: `index.html.1'

[] 37,668 --.-K/s in 0.1s

2012-05-15 15:50:26 (374 KB/s) - `index.html.1' saved [37668]
```
- `wget -r --no-parent -w 2 --limit-rate=20k http://activehistory.ca/papers/` This will download all papers (files) on this site
- `wget -m -w 2 --limit-rate=20k http://activehistory.ca` This will mirror the entire site
- Record history and save as .md file in repository
- `history > WGET_CommandsTutorial.md`
- Check to see if the file is there with `ls`
- `cp WGET_CommandsTutorial.md /home/maggiesherwin/CraftingDH/week_3`
- `cd /home/maggiesherwin/CraftingDH/week_3`
- use `ls` to make sure `WGET_CommandsTutorial.md` is there
##### Part 2
- `~`
- `mkdir war-diary`
- `cd war-diary`
- `nano urls.py`
- Paste this:
```
urls = '';
f=open('urls.txt','w')
for x in range(8029, 8110):
    urls = 'http://data2.collectionscanada.ca/e/e061/e00151%d.jpg\n' % (x)
    f.write(urls)
f.close
```
- ctrl+x, Y, enter
- `python urls.py`
- `ls`
- Note the new file called `urls.txt`
- Look at the file by typing `nano urls.txt` and exit nano
- `wget -i urls.txt -r --no-parent -nd -w 2 --limit-rate=100k`
- `ls`
- Make sure the 80 new files are there
- `history > WGET_Commands.md`
- Check to see if the file is there with `ls`
- `cp WGET_Commands.md /home/maggiesherwin/CraftingDH/week_3`
- `cd /home/maggiesherwin/CraftingDH/week_3`
- use `ls` to make sure `WGET_Commands.md` is there








#### TEI
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque vitae fermentum mauris. Morbi ac purus eget lorem congue tincidunt. Praesent in massa vulputate, pretium massa ac, aliquet nulla. Suspendisse condimentum nisl in sapien mattis, nec ullamcorper ipsum elementum. Suspendisse potenti. Aenean mattis sapien non vulputate dictum. Praesent aliquam ligula non est pulvinar posuere. Morbi faucibus est nec turpis ultrices vehicula. Duis bibendum felis tellus, at sodales enim congue quis. Nam imperdiet, nibh suscipit tempus consequat, nisi diam sagittis arcu, eu cursus lectus urna sed ligula. Nunc pharetra orci molestie nunc finibus, at eleifend ligula dictum.
#### APIs
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque vitae fermentum mauris. Morbi ac purus eget lorem congue tincidunt. Praesent in massa vulputate, pretium massa ac, aliquet nulla. Suspendisse condimentum nisl in sapien mattis, nec ullamcorper ipsum elementum. Suspendisse potenti. Aenean mattis sapien non vulputate dictum. Praesent aliquam ligula non est pulvinar posuere. Morbi faucibus est nec turpis ultrices vehicula. Duis bibendum felis tellus, at sodales enim congue quis. Nam imperdiet, nibh suscipit tempus consequat, nisi diam sagittis arcu, eu cursus lectus urna sed ligula. Nunc pharetra orci molestie nunc finibus, at eleifend ligula dictum.
#### Mining Twitter
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque vitae fermentum mauris. Morbi ac purus eget lorem congue tincidunt. Praesent in massa vulputate, pretium massa ac, aliquet nulla. Suspendisse condimentum nisl in sapien mattis, nec ullamcorper ipsum elementum. Suspendisse potenti. Aenean mattis sapien non vulputate dictum. Praesent aliquam ligula non est pulvinar posuere. Morbi faucibus est nec turpis ultrices vehicula. Duis bibendum felis tellus, at sodales enim congue quis. Nam imperdiet, nibh suscipit tempus consequat, nisi diam sagittis arcu, eu cursus lectus urna sed ligula. Nunc pharetra orci molestie nunc finibus, at eleifend ligula dictum.
#### Tesseract
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque vitae fermentum mauris. Morbi ac purus eget lorem congue tincidunt. Praesent in massa vulputate, pretium massa ac, aliquet nulla. Suspendisse condimentum nisl in sapien mattis, nec ullamcorper ipsum elementum. Suspendisse potenti. Aenean mattis sapien non vulputate dictum. Praesent aliquam ligula non est pulvinar posuere. Morbi faucibus est nec turpis ultrices vehicula. Duis bibendum felis tellus, at sodales enim congue quis. Nam imperdiet, nibh suscipit tempus consequat, nisi diam sagittis arcu, eu cursus lectus urna sed ligula. Nunc pharetra orci molestie nunc finibus, at eleifend ligula dictum.

<!---
Links
-->
[Epigraphic Database Heidelberg]: <http://edh-www.adw.uni-heidelberg.de/inschrift/suche>
[Commwealth War Graves Commission, Find War Dead]: <https://www.cwgc.org/find/find-war-dead>
[Link to annotation]: <enter-link-here>


