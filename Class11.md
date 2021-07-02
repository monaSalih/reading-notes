# Images

### Controlling sizes of images in Css

You can control the size of an image using the width and height properties in CSS, just like you can for any other box

![ff1](ff1.md)

## Aligning images Using Css

Rather than using the <img> element's align attribute, webpage authors are increasingly using the float property to align images. There are two ways that this is commonly achieved:
 1. The float property is added to the class that was created to represent the size of the image (such as the small class in our example). 
 2. New classes are created with names such as align-left or align-right to align the images to the left or right of the page. These class names are used in addition to classes that indicate the size of the image.

 ![ff1](ff2.md)

 ## Centering images Using Css
Once it has been made into a block-level element, there are two common ways in which you can horizontally center an image:
 1. On the containing element, you can use the text-align property with a value of center.
  2. On the image itself, you can use the use the margin property and set the values of the left and right margins to auto.

## background-image

The background-image property allows you to place an image behind any HTML element. This could be the entire page or just part of the page. By default, a background image will repeat to fill the entire box.The path to the image follows the letters url, and it is put inside parentheses and quotes
 ![ff1](ff3.md)

 ## background-repeat // background-attachment
 The background-repeat property can have four values: 
 * repeat 
 The background image is repeated both horizontally and vertically (the default way it is shown if the backgroundrepeat property isn't used).
 * repeat-x 
 The image is repeated horizontally only (as shown in the first example on the left). 
 * repeat-y 
 The image is repeated vertically only.
 * no-repeat
  The image is only shown once. 

  ## background-position
  This property usually has a pair of values. The first represents the horizontal position and the second represents the vertical.

![ff1](ff4.md)

## shorthand//background

The properties must be specified in the following order, but you
can miss any value if you do not want to specify it:
1. background-color
2. background-image
3. background-repeat
4. background-attachment
5. background-position
![ff1](ff5.md)


## Images rollovers & Sprites

Using CSS, it is possible to create a link or button that changes to a second style when a user moves their mouse over it (known as a rollover) and a third style when they click on it

![ff1](ff6.md)


## Contrast of background images

If you want to overlay text on a background image, the image must be low contrast in order for the text to be legible.

![ff1](ff7.md)

### Nots

* You can specify the dimensions of images using CSS.This is very helpful when you use the same sized images on several pages of your site.
* Images can be aligned both horizontally and vertically using CSS.
* You can use a background image behind the box created by any element on a page.
* Background images can appear just once or be repeated across the background of the box.
* You can create image rollover effects by moving the
background position of an image.
* To reduce the number of images your browser has to
load, you can create image sprites


## Practical Information

### Search Engine Optimization (SEO)

Search engine optimization (or SEO) is the practice of trying to help your site appear nearer the top of search engine results when people look for the topics that your website covers.


## On-Page SEO


![ff1](ff8.md)

1. Page Title
The page title appears at the top of the browser window or on the tab of a browser. It is specified in the title> element which lives inside the <head> element.

2. URL / Web Address
The name of the file is part of the URL. Where possible, use keywords in the file name.

3. Headings
If the keywords are in a heading hn> element then a search engine will know that this page is all about that subject and give it greater weight than other text

4. Text
Where possible, it helps to repeat the keywords in the main body of the text at least 2-3 times. Do not, however, over-use these terms, because the text must be easy for a human to read.

5. Link Text
Use keywords in the text that create links between pages(rather than using generic expressions such as "click here").
6. Image Alt Text
Search engines rely on you providing accurate descriptions of images in the alt text. This will also help your images show up in the results of image-based searches.

7. Page Descriptions
The description also lives inside the <head> element and is specified using a <meta> tag. It should be a sentence that describes the content of the page. (These are not shown in the browser window but they may be displayed in the results pages of search engines.)

## How to Identify Keywords and Phrases

Determining which keywords to use on your site can be one of the hardest tasks when you start to think about SEO. Here are six steps that will help you identify the right keywords and phrases for your site.

1. Brainstorm
List down the words that someone might type into Google to find your site. Be sure to include the various topics,
products or services your site is about.

2. Organize
Group the keywords into separate lists for the different sections or categories of your website.

3. Research
There are several tools that let you enter your keywords and then they will suggest additional keywords you might like to consider, such as:
adwords.google.co.uk/select/KeywordToolExternal (When using this tool, select the "exact match" option rather than "broad match.")

4. Compare
It is very unlikely that your site will appear at the top of the search results for every keyword. This is especially true for topics where there is a lot of competition. The more sites out there that have already been optimized for a given keyword, the harder it will be for you to rise up the search results when people search on that term.

5. Refine
Now you need to pick which keywords you will focus on. These should always be the ones that are most relevant to each section of your site.

6. Map
Now that you have a refined list of keywords, you know which have the most competition, and which ones are most relevant, it is time to start picking which keywords you will use for each page.

## Analytics: Learning about your Visitors

* Signing Up
The Google Analytics service relies on you signing up for an account at:
(www.google.com/analytics) The site will give you a piece of tracking code which you need to put on every page of your site.

* How it Works
Every time someone loads a page of your site, the tracking code sends data to the Google servers where it is stored. Google then provides a webbased interface that allows you to see how visitors use your site. 

* The Tracking Code
A tracking code is provided by Google Analytics for each website you are tracking. It should appear just before the closing </head> tag. The code does not alter the appearance of your web pages. 

### How Many People Are Coming to Your Site?

* Visits
This is the number of times people have come to your site. If someone is inactive on your site for 30 minutes and then looks at another page on your site, it will be counted as a new visit.

* Unique Visits
This is the total number of people who have visited your site over the specified period. The number of unique visits will be lower than the number of visits if people have been returning to your site more than once in the defined period.

* Page Views
The total number of pages all visitors have viewed on your site. 

* Pages per Visit
The average number of pages each visitor has looked at on
your site per visit.

* Average Time on Site
The average amount of time each user has spent on the site
per visit. 

* Date Selector
Using the date selector in the top right hand corner of the site, you can change the period of time the reports display. When you log in, this is usually set to the last month, but you can change it to report on a specific time period.

* Export
The export link just above the title that says "visitors overview" allows you to export the statistics on this page for other applications such as Excel.

## What Are Your Visitors Looking At?

* Pages
This tells you which pages your visitors are looking at the most and also which pages they are spending the most time on.

* Landing Pages
These are the pages that people arrive on when first visiting your site. This can be particularly helpful because you may find people are not always coming into your site via the homepage.

* Top Exit Pages
This shows which pages people most commonly leave from. If a lot of people are leaving from the same page then you might consider changing that page or improving it

* Bounce Rate
This shows the number of people who left on the same page that they arrived on. A high bounce rate suggests that the content is not what they were looking for or that the page did not sufficiently encourage them to look around the rest of the site. What counts as a bounce:
● Clicked a link to another site
● Clicked on an advertisement
● Entered a new URL
● Used the "back" button
● Closed the browser

## FTP & Third Party Tools

To transfer your code and images from your computer to your hosting company, you use something known as File Transfer Protocol.

As the name suggests, File Transfer Protocol (or FTP) allows you to transfer files across the Internet from your computer to the web server hosting your site.

* Here is a list of some popular FTP applications:
● FileZilla
filezilla-project.org (Windows, Mac, Linux)
● FireFTP
fireftp.mozdev.org (Windows, Mac, Linux)

●  CuteFTP
cuteftp.com (Windows, Mac)

● SmartFTP
smartftp.com (WIndows)

● Transmit
panic.com/transmit (Mac)


After finish reading [click here](Quiz11.md) to test information.