#### Regex introduction
- Open [RegeXr](http://www.regexr.com/)
- Go through the tutorial
- **Protip:** there are libraries of regular expressions, online. For example, if you want to find all postal codes, you can search “regular expression Canadian postal code” and learn what ‘formula’ to search for to find them.
- Let's say you're looking for all the instances of "cat" or "dog" in your document. When you type the vertical bar on your keyboard (it looks like `|`, shift+backslash), that means 'or' in regular expressions. So, if your query is dog|cat and you press 'find', it will show you the first time either dog or cat appears in your text.
- If you want to replace every instance of either "cat" or "dog" in your document with the world "animal", you would open your find-and-replace box, put `dog|cat` in the search query, put animal in the 'replace' box, hit 'replace all', and watch your entire document fill up with references to animals instead of dogs and cats.
- Simple searches don't differentiate between letters and spaces, in this case, the solution appears simple; put a space before and after your search query, so now it reads:
`dog | cat`
- To mark the beginning of a word use `\<` or for textwrangler, `\b`
- To mark the end of a word use `>\` or for textwrangler, `b\`
- You can also search for variations within a single word using parentheses. For example if you were looking for instances of "gray" or "grey", instead of the search query `gray|grey` you could type `gr(a|e)y`
- The period character `.` in regular expressions directs the search to just find any character at all. For example, if we searched for:
- the plus symbol `+` instructs the program to find any number of the previous character. If we search for `do+g` it would return any words that looked like "dog", "doog", "dooog", and so forth.
- If you search for `(dogs)( and )(cats)` your program would remember "dogs" is group 1, "and" is group 2, and "cats" is group 3. Notepad++ remembers them as `"\1"`, `"\2"`, and `"\3"` for each group respectively.
- If you wanted to switch the order of "dogs" and "cats" every time the phrase "dogs and cats" appeared in your document, you would type `(dogs)( and )(cats)` in the 'find' box, and `\3\2\1` in the 'replace' box. That would replace the entire string with group 3 ("cats") in the first spot, group 2 (" and ") in the second spot, and group 1 ("dogs") in the last spot, thus changing the result to "cats and dogs".
- [regex lib cheat sheet](http://regexlib.com/CheatSheet.aspx)
#### Regex & Texas
- `curl http://archive.org/stream/diplomaticcorre33statgoog/diplomaticcorre33statgoog_djvu.txt > texas.txt`
- `nano texas.txt` Delete everything except for the index of the list of letters 
- Save the file
- `grep '\bto\b' texas.txt`
- Copy and paste some of your text into [RegeXr](http://www.regexr.com/).
- Write your regular expression (ie. what you're trying to find), and your substitution (ie. what you're replacing with) in the RegExr interface.
- sed -r -i.bak 's/(.+\bto\b.+)/~\1/g' texas.txt
- Type `ls` and you'll see that a new file, `texas.txt.bak` has been created.
- Type `nano texas.txt` and examine the file. You should now have `~` at the start of each entry of the index!
- `grep '~' texas.txt > index.txt`
- `sed -r -i.bak 's/(,)( [0-9]{4})(.+)/\2/g' index.txt`
- `sed -r -i.bak 's/~//g' index.txt`
- `grep -r ".+,.+,.+," index.txt`
- Add `Sender, Recipient, Date` as the first line of `index.txt`


#### Open Refine
- Move your `cleaned-correspondence` file to somewhere safe on your computer
- Click ‘Create project’
- Click ‘Choose files’ and select the Texan correspondence CSV file
- Name your project and click ‘Create project’
- Click on the arrow to the left of "Sender" in OpenRefine and select `Facet -> Text Facet`. Do the same with the arrow next to "Recipient".
- Within the "Sender" facet box on the left side, click on the button labeled "Cluster"
- Play with the values in the drop-down boxes and notice how the number of clusters found change depending on which method is used. Because the methods are slightly different, each will present different matches that may or may not be useful
- If you see two values which should be merged, e.g. "Ashbel Smith" and ". Ashbel Smith", check the box to the right in the 'Merge' column and click the 'Merge Selected & Re-Cluster' button below
- Repeat these steps with Recipients, reducing unique Recipients from 192 to about 160
- To finish the automatic cleaning of the data, click the arrow next to "Sender" and select `Edit Cells -> Common transforms -> Trim leading and trailing whitespace`
- Repeat steps for "Recipient"
- Click on ‘Export’ at the top right of the window to get your data back out as a .csv file
- In the arrow to the left of Sender in the main OpenRefine window, select Edit column -> Rename this column, and rename the column "source"
- In the arrow to the left of Recipient in the main OpenRefine window, select Edit column -> Rename this column, and rename the column "target"
- In the top right of the window, select 'Export -> Custom tabular exporter'
- Notice that "source", "target", and "Date" are checked in the content tab; uncheck "Date"
- Go to the download tab and change the download option from 'Tab-separated values (TSV)' to 'Comma-separated values (CSV)' and press download.
- Go ahead and drop this file into the [Palladio](http://hdlab.stanford.edu/palladio/) interface. Do you see any interesting patterns? Make a note!
- Upload your cleaned file with a new name back into your DH Box
#### Capstone exercise
- Google for sed patterns and see if you can combine what you find with what you've learned in this module in order to clean up the text
- `find . -type f -exec sed -i.bak "s/foo/bar/g" {} \;` This finds all files in a folder and creates a backup for each one in turn before searching for foo and replacing it with bar.
- `grep "[b-df-hj-np-tv-xz]\{5\}" filename` will find all instances of strings of five consonants or more, which can be useful to give you an idea of what kinds of sed patterns to write.
- Remember to copy your notes and any other information/observations/thoughts to your GitHub repo.
####  Named Entity Recognizer
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi aliquet mi nisl, malesuada mollis arcu pharetra sit amet. Mauris non nibh orci. Fusce quam nibh, venenatis eget erat ut, dapibus venenatis sapien. Suspendisse laoreet nibh in molestie finibus. Fusce lorem dui, volutpat ac lacus et, lobortis tristique sem. Phasellus vulputate augue vel aliquam eleifend. Vestibulum semper convallis sapien a ultrices. Praesent tincidunt cursus faucibus. Sed finibus lorem cursus sodales iaculis. Aliquam ut augue vel velit auctor euismod. Nulla et neque mi. Vestibulum non dolor in ante suscipit dapibus nec non dolor.
#### Counting and Mining Data with Unix
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi aliquet mi nisl, malesuada mollis arcu pharetra sit amet. Mauris non nibh orci. Fusce quam nibh, venenatis eget erat ut, dapibus venenatis sapien. Suspendisse laoreet nibh in molestie finibus. Fusce lorem dui, volutpat ac lacus et, lobortis tristique sem. Phasellus vulputate augue vel aliquam eleifend. Vestibulum semper convallis sapien a ultrices. Praesent tincidunt cursus faucibus. Sed finibus lorem cursus sodales iaculis. Aliquam ut augue vel velit auctor euismod. Nulla et neque mi. Vestibulum non dolor in ante suscipit dapibus nec non dolor.


Capstone Exercise
-----------------

You can use what you've been learning here to do some clean-up on the Canadian war diary files (or a subset of them, of course, as suits your interests — you have explored them, haven't you?). Google for **sed patterns** and see if you can combine what you find with what you've learned in this module in order to clean up the text. For instance, a common error in OCR is to confuse the letter `i` with the letter `l` and the numeral `1`. Shawville becomes Shawvllle. You could use grep to see if that error is present, and then sed to correct it. The file names are long, and there are several hundred; you might give this kind of thing a try too:

`$ find . -type f -exec sed -i.bak "s/foo/bar/g" {} \;`

This command finds all files in a folder and creates a backup for each one in turn before searching for **foo** and replacing it with **bar**.

The command `$ grep "[b-df-hj-np-tv-xz]\{5\}" filename` will find all instances of strings of five consonants or more, which can be useful to give you an idea of what kinds of sed patterns to write.

Maybe, if you inspect the PDF and the txt files together, you can figure out patterns that set off interesting things in say the classified ads or the editorials — and then write some grep and sed to create new files with just that information. Then you could use Open Refine to further clean things up. Maybe the messiness of the data is [exactly the point](https://smgprojects.github.io/experiment-bad-equity/) ([and my workup on bad OCR](https://smgprojects.github.io/experiment-determining-bad-ocr-via-automated-spellcheck/)) you want to explore. Nevertheless:

**Cleaning data is 80% of the work in digital history.**

**Remember to copy your notes and any other information/observations/thoughts to your GitHub repo.**

Going Further
-------------

*   See some of the suggestions at the end of the [Open Refine exercise](../../supporting materials/open-refine/).
    
*   The **Stanford Named Entity Recognizer** is a program that enables you to automatically tag words in your corpus according to whether or not they are place names, individuals, and so on. The output can then be subsequently extracted and visualized. Try the [NER exercise in our supporting materials](../../supporting materials/ner/).
    
*   [Counting and Mining Data with Unix](http://programminghistorian.org/lessons/research-data-with-unix)
    
