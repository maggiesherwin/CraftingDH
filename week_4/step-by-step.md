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
#### Open Refine
- Move your `cleaned-correspondence` file to somewhere safe on your computer.
#### Capstone exercise
- Google for sed patterns and see if you can combine what you find with what you've learned in this module in order to clean up the text
- `find . -type f -exec sed -i.bak "s/foo/bar/g" {} \;` This finds all files in a folder and creates a backup for each one in turn before searching for foo and replacing it with bar.
- `grep "[b-df-hj-np-tv-xz]\{5\}" filename` will find all instances of strings of five consonants or more, which can be useful to give you an idea of what kinds of sed patterns to write.
- Remember to copy your notes and any other information/observations/thoughts to your GitHub repo.
####  Named Entity Recognizer
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi aliquet mi nisl, malesuada mollis arcu pharetra sit amet. Mauris non nibh orci. Fusce quam nibh, venenatis eget erat ut, dapibus venenatis sapien. Suspendisse laoreet nibh in molestie finibus. Fusce lorem dui, volutpat ac lacus et, lobortis tristique sem. Phasellus vulputate augue vel aliquam eleifend. Vestibulum semper convallis sapien a ultrices. Praesent tincidunt cursus faucibus. Sed finibus lorem cursus sodales iaculis. Aliquam ut augue vel velit auctor euismod. Nulla et neque mi. Vestibulum non dolor in ante suscipit dapibus nec non dolor.
#### Counting and Mining Data with Unix
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi aliquet mi nisl, malesuada mollis arcu pharetra sit amet. Mauris non nibh orci. Fusce quam nibh, venenatis eget erat ut, dapibus venenatis sapien. Suspendisse laoreet nibh in molestie finibus. Fusce lorem dui, volutpat ac lacus et, lobortis tristique sem. Phasellus vulputate augue vel aliquam eleifend. Vestibulum semper convallis sapien a ultrices. Praesent tincidunt cursus faucibus. Sed finibus lorem cursus sodales iaculis. Aliquam ut augue vel velit auctor euismod. Nulla et neque mi. Vestibulum non dolor in ante suscipit dapibus nec non dolor.


     Exercises - HIST3814o Crafting Digital History       // Current page data var mkdocs\_page\_name = "Exercises"; var mkdocs\_page\_input\_path = "module-3/Exercises.md"; var mkdocs\_page\_url = "/module-3/Exercises/";     hljs.initHighlightingOnLoad();

[HIST3814o Crafting Digital History](../..)

*   [Home](../..)
*   [Getting Started](../../introduction/crafting-digital-history/)
*   1\. Open Access Research
    *   [Why you should be open](../../module-1/Open-Access-Research/)
    *   [Exercises](../../module-1/Exercises/)
*   2\. Finding Data
    *   [How do we find data?](../../module-2/Finding Data/)
    *   [Exercises](../../module-2/Exercises/)
*   3\. Fixing Data
    *   [Data is messy](../Wrangling Data/)
    *   [Exercises](./)
        *   [Module 3 Exercises](#module-3-exercises)
        
        *   [Exercise 1: Regular Expressions](#exercise-1-regular-expressions)
        *   [Exercise 2: Open Refine](#exercise-2-open-refine)
        *   [Capstone Exercise](#capstone-exercise)
        *   [Going Further](#going-further)
        
*   4\. Analysis
    *   [Seeing Patterns](../../module-4/Seeing Patterns/)
    *   [Exercises](../../module-4/Exercises/)
*   5\. Visualization
    *   [Communicating your Findings](../../module-5/Humanities Visualization/)
    *   [Capstone Exercise](../../module-5/Exercises/)
*   [6\. Final Thoughts](../../conclusion/Conclusion/)
*   Appendices
    *   [Text Encoding Initiative](../../supporting materials/tei/)
    *   [Git in RStudio](../../supporting materials/git-rstudio/)
    *   [Introduction to Regular Expressions (regex)](../../supporting materials/regex/)
    *   [Regex & the Republic of Texas](../../supporting materials/regexex/)
    *   [Open Refine](../../supporting materials/open-refine/)
    *   [Stanford Named Entity Recognizer](../../supporting materials/ner/)
    *   [Going further with regex](../../supporting materials/regex-ner/)
    *   [Quick intro to R](../../supporting materials/quick-intro-r/)
    *   [Choose Your Own Adventure](../../supporting materials/cyoa.txt/)
    *   [Geoparsing with Python](../../supporting materials/geoparsing-w-python.txt/)
    *   [Glitch](../../supporting materials/glitch/)
    *   [Social Network Analysis with Gephi](../../supporting materials/gephi.txt/)
    *   [Graphing the Net](../../supporting materials/graphing-the-net.txt/)
    *   [Topic Modeling, DH Box](../../supporting materials/topicmodel-r-dhbox/)
    *   [Topic Modeling, Local](../../supporting materials/topicmodel-r-yourmachine/)
    *   [Network visualization with igraph](../../supporting materials/netviz/)
    *   [Inkscape](../../supporting materials/inkscape/)
    *   [GitHub Pages](../../supporting materials/gh-pages/)
    *   [Leaflet](../../supporting materials/leaflet.txt/)

 

[HIST3814o Crafting Digital History](../..)

*   [Docs](../..) »
*   3\. Fixing Data »
*   Exercises
*   [Edit on GitHub](https://github.com/shawngraham/dhworkbook/tree/gh-pages/edit/master/docs/module-3/Exercises.md)

* * *

Module 3 Exercises
==================

The exercises in this module cover:

*   Cleaning text with regular expressions
*   Cleaning files with Open Refine

* * *

Exercise 1: Regular Expressions
-------------------------------

When we have text that has been marked up, we can do interesting things with it. In the previous module, you saw that XSL can be used to add styles to your XML (which a browser can interpret and display). You can see how having those tags makes for easier searching for information as well, right? Sometimes things are not well marked up. Sometimes, it's all a real mess. In this exercise, we'll explore 'regular expressions', (AKA 'Regex') or ways of asking the computer to search for **patterns** rather than matching exact text.

This exercise follows a tutorial written for [The Macroscope](http://themacroscope.org). Another good reference is the [regular expressions website](http://www.regular-expressions.info/).

You should open [RegeXr](http://www.regexr.com/), an interactive tutorial that shows us what various regular expressions can do, in a browser window so you can test your regular expressions out **before** applying them to your data! We will use the power of regular expressions to search for particular patterns in a published volume of the correspondence of the Republic of Texas. We'll use regex to massage the information into a format that we can then use to generate a social network of letter writers over time. (You might also want to try the [Programming Historian tutorial Understanding Regular Expressions](http://programminghistorian.org/lessons/understanding-regular-expressions).)

What if you had **a lot** of documents that you needed to clean up? One way of doing it would be to write a Python program that applied your regex automatically, across all the files in a folder. **Optional advanced exercise**: [Cleaning OCR'd Text with Regular Expressions](http://programminghistorian.org/lessons/cleaning-ocrd-text-with-regular-expressions).

For this exercise, do the following:

1.  Start with [a gentle introduction to regex](../../supporting materials/regex/).
    
2.  Then begin the [regex exercise](../../supporting materials/regexex/).
    

**Remember to copy your history file and any other information, observations, or thoughts to your GitHub repo.**

* * *

Exercise 2: Open Refine
-----------------------

**Open Refine** is the final tool we'll explore in this module. This engine allows us to clean up our messy data. We will feed it the results from Exercise 2 in order to consolidate individuals (ie. 'Shawn' and 'S4awn' are probably the same person, so Open Refine will consolidate that information for us). This exercise also follows a tutorial originally written for [The Macroscope](http://themacroscope.org).

Open Refine does not run in DH Box, so use the File Manager in DH Box to move your `cleaned-correspondence` file to somewhere safe on your computer.

For this exercise, do the following:

1.  The [Open Refine exercise in our supporting materials](../../supporting materials/open-refine/).

For more advanced usage of Open Refine, as an optional exercise you can also try [The Programming Historian's Tutorial on Open Refine](http://programminghistorian.org/lessons/cleaning-data-with-openrefine).

**Remember to copy your notes and any other information/observations/thoughts to your GitHub repo.**

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
    

[Next](../../module-4/Seeing Patterns/ "Seeing Patterns") [Previous](../Wrangling Data/ "Data is messy")

* * *

Built with [MkDocs](http://www.mkdocs.org) using a [theme](https://github.com/snide/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org).

[GitHub](https://github.com/shawngraham/dhworkbook/tree/gh-pages/) [« Previous](../Wrangling Data/) [Next »](../../module-4/Seeing Patterns/)

var base\_url = '../..';




, an interactive tutorial that shows us what various regular expressions can do, in a browser window so you can test your regular expressions out **before** applying them to your data! We will use the power of regular expressions to search for particular patterns in a published volume of the correspondence of the Republic of Texas. We'll use regex to massage the information into a format that we can then use to generate a social network of letter writers over time. (You might also want to try the [Programming Historian tutorial Understanding Regular Expressions](http://programminghistorian.org/lessons/understanding-regular-expressions).)
