### Note: This branch is under development, so please don't blame us for any errors, which are obviously unintentional from our part.

# OpnRank

A simple SEO metrics scanner that can be extended with added modules.

OpnRank consists of broadly 3 stages in its workflow:

   1. Content Parsing stage.
   2. Content Analysis stage.
   3. Content Visualization stage.


## 1. Content Parsing Stage.

In the content parsing stage, OpnRank parses the content from various sources into a readable format, and make it usable for analysis. Nothing much is involved here. But for the sake of clarity, here's what it does:

   1. (Optional) Send a request to the URL (if content is from a URL)
   2. Receives the data from the URL (if URL allows for scraping), or the local file (currently .pdf and .txt formats are supported.)
   3. Parses the data such that only the text from the content remains.
   4. Writes the text data into a .txt f

Although it is simple, modules can be very well added to it for different purposes (E.g., adding support for other file formats)


## 2. Content Analysis Stage.

This is the real deal. This is the stage for modules to come in. Analysis can range from simple keyword frequency count to sentiment analysis and other complex NLP functions.


#### What it means for users:

You shouldn't mess with this part casually. Add changes and tweaks only when you are sure of it.


#### What it means for contributors & developers:

This is where OpnRank needs you all to work on. All modules should be stored in the modules folder. You should have a main file that contains all the functions to call from the other scripts that you may make.

Example:

Let's say you are making a module abcd, that has 3 functions: f1(), f2(), f3()

You should create the main file named abcd.py in the modules/analysis folder, and another subfolder in the modules/analysis folder named abcd, that stores other scripts that you may use. Let's name these contents in the subfolder as fl1.py, fl2.py, fl3.py

Then, abcd.py should contain code like:

    from abcd import f1
    from abcd import f2
    from abcd import f3
    
    def f1():
      %your code
      
    def f2():
      %your code
    
    def f3():
      %your code

## 3. Content Visualization stage.
