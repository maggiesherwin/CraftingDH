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
- Make sure the 80 new files are there (All 80 were there!!)
- `history > WGET_Commands.md`
- Check to see if the file is there with `ls`
- `cp WGET_Commands.md /home/maggiesherwin/CraftingDH/week_3`
- `cd /home/maggiesherwin/CraftingDH/week_3`
- use `ls` to make sure `WGET_Commands.md` is there
#### TEI
- Open the blanktemplate.txt file in Sublime Text, and have the pamphlet you chose also open
- Choose a page to transcribe
- find this `<biblScope>1</biblScope>` and replace the 1 with the page number of the page you have chosen
- find and highlight
    - Any persons mentioned (including any he/she if they refer to a specific person)
    - Any places mentioned
    - Any claims, assertions or arguments made
- Add detail to the information you found using code:
    - For a person: `<persName key="Last, First" from="YYYY" to="YYYY" role="Occupation" ref="http://www.website.com/webpage.html"> (text)</persName>`
    - For a place: `<placeName key="Sheffield, United Kingdom" ref="http://tools.wmflabs.org/geohack/geohack.php?pagename=Sheffield&params=53_23_01_N_1_28_01_W_type:city_region:GB">(text)</placeName>`
- Rename your file as a .xml file
- Save it and the .xsi file to your repository

#### APIs
##### Part 1
- Open the 'Chronicling America API' notebook. 
- Run through its various steps so that you end up with a json file of results. 
- Imagine that you are writing a paper on the public reception of archaeology in the 19th century in the United States. Alter the notebook so that you can find primary source material for your study. 
- Going further: Find another API for historical newspapers somewhere else in the world. 
- Duplicate the notebook, and alter it to search this other API so that you can have material for a cross-cultural comparison.
##### Part 2
- Open the 'Open Context API'. 
- Notice how similar it is to the first notebook! 
- Run through the steps so that you can see it work. 
- Study the [Open Context API documentation]. 
- Modify the search to return materials from a particular project or site.
##### Part 3
- Open 'Open Context Measurements'
- Search for zoological data held in Open Context, using standardised vocabularies from that field that described faunal remains. 
- Examine the code carefully - do you see a series of nested 'if' statements? 
- Run each section of the code. 
- Do you see the section that defines how to make a plot? This code is called on later in the notebook, enabling us to plot the counts of the different kinds of faunal data. 
- Try plotting different categories.
##### Part 4
- The [Portable Antiquities Scheme] database also has an API. 
- Launch this [binder] and open the 'Retrieving Data from the Portable Antiquities Scheme Database' notebook (courtesy of Daniel Pett). 
- Work out how to make the query search for medieval materials, and write a csv to keep more of the data fields.
- Do this: https://programminghistorian.org/en/lessons/creating-apis-with-python-and-flask

#### Mining Twitter
- Go to the Twitter apps page
- Click on 'New App'
- Name your app `my-twarc`
- For the website, enter `site.craftingdigitalhistory.ca`
- Leave all other fields blank
- Click on the tab labelled Keys and Access Tokens.
- Copy the 'Consumer Key (API Key)' (the consumer secret) to a text file.
- Click on the button labelled Create Access Tokens at the bottom of the page.
- Copy those to your text file and save it. 
- Right-click the following Binder link and select Open in new tab: [Binder]
- It is setting up your new virtual computer. When it's loaded up, it will resemble the following image: 
![alt text][Completed Virtual Computer]
- Click the 'New' button, and select 'Terminal'.
- Type `twarc configure` into the terminal







#### Tesseract
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque vitae fermentum mauris. Morbi ac purus eget lorem congue tincidunt. Praesent in massa vulputate, pretium massa ac, aliquet nulla. Suspendisse condimentum nisl in sapien mattis, nec ullamcorper ipsum elementum. Suspendisse potenti. Aenean mattis sapien non vulputate dictum. Praesent aliquam ligula non est pulvinar posuere. Morbi faucibus est nec turpis ultrices vehicula. Duis bibendum felis tellus, at sodales enim congue quis. Nam imperdiet, nibh suscipit tempus consequat, nisi diam sagittis arcu, eu cursus lectus urna sed ligula. Nunc pharetra orci molestie nunc finibus, at eleifend ligula dictum.

<!---
Links
-->
[Epigraphic Database Heidelberg]: <http://edh-www.adw.uni-heidelberg.de/inschrift/suche>
[Commwealth War Graves Commission, Find War Dead]: <https://www.cwgc.org/find/find-war-dead>
[Link to annotation]: <enter-link-here>
[Open Context API documentation]: <https://opencontext.org/about/services>
[Portable Antiquities Scheme]: <https://finds.org.uk/>
[binder]: <https://mybinder.org/v2/gh/o-date/notebooks-archdata/master>
[Binder]: <https://mybinder.org/v2/gh/o-date/social-media-work/master>
[Completed Virtual Computer]: http://www.screencast-o-matic.com/screenshots/u/e7i1/1539304640402-48607.png "VC"


