## wireframe: 
### Wireframing is a practice used by UX designers which allows them to define and plan the information hierarchy of their design and plan the layout and interaction of your interface, also a great way of getting to know how a user interacts with your interface, through the positioning of buttons and menus on the diagrams.

 ## Examples of wireframes
  ** some examples of wireframes: **

  1. Wireframes drawn with paper and a pencil, or at a whiteboard, have the advantage of looking and being very easy to change
  2. With the help of paper-prototypes, you can test with end users at every stage of ideation and design.
  3. Switching later to software (after initially hand-drawing your wireframe) allows you to keep track of more detailed decisions.

 

  ![wire]( https://d33wubrfki0l68.cloudfront.net/dbb80f2f6a5dafa25f702ad00bc429057fb59cec/52716/en/blog/uploads/versions/samuel-student-wireframe---x----972-715x---.png)

  
  ## What to consider when deciding on your wireframing process
  following are a number of ways different designers can structure the process from design to implementation:
  * Wireframe > Interactive Prototype > Visual > Design
* Sketch > Code
* Sketch > Wireframe > Hi-Def Wireframe > Visual > Code
* Sketch > Wireframe > Visual > Code

## The best tools for wireframing

There are heaps of free tools out there for creating wireframes and prototypes, The examples below all have free trials, so check them out!:
* UXPin: UXPin has a wide range of functionalities, but one of the best ones is how it facilitates building responsive clickable prototypes directly in your browser.

* InVision: InVision allows you to get feedback straight from your team and users through clickable mock-ups of your site design. It’s completely free too!

* Wireframe.cc: Wireframe.cc provides you with the technology to create wireframes really quickly within your browser, the online version of pen and paper.

How to make your wireframe in six steps
1. 1. Do your research
2. 2. Prepare your research for quick reference
3. 3. Make sure you have your user flow mapped out
4. Draft, don’t draw. Sketch, don’t illustrate
5. Add some detail and get testing
6. Start turning your wireframes into prototypes

# HTML
## So what is HTML?
is a markup language that defines the structure of your content. Consists of a series of elements, which you use to enclose, or wrap, different parts of the content to make it appear a certain way, or act a certain way.
for example follwing line how we can convert to HTML:

```
My cat is very grumpy
convert it to html line:
<p>My cat is very grumpy</p>
```
# Anatomy of an HTML element
Let's explore this paragraph element a bit further.
![html]( https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/HTML_basics/grumpy-cat-small.png)

## The main parts of our element are as follows:

1. The opening tag: This consists of the name of the element (in this case, p), wrapped in opening and closing angle brackets.

2. The closing tag: This is the same as the opening tag, except that it includes a forward slash before the element name. 
3. The content: This is the content of the element, which in this case, is just text.
4. The element: The opening tag, the closing tag, and the content together comprise the element.


Elements can also have attributes that look like the following:
![html2]( https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/HTML_basics/grumpy-cat-attribute-small.png)

attribute should always have the following:

* A space between it and the element name (or the previous attribute, if the element already has one or more attributes).
* The attribute name followed by an equal sign.
* The attribute value wrapped by opening and closing quotation marks.

# Nesting elements
You can put elements inside other elements too — this is called nesting. like following:

	``` 
  <p>My cat is <strong>very</strong> grumpy.</p>
  
  # Empty elements

  Some elements have no content and are called empty elements. Take the <img> element that we already have in our HTML page:
  ```
   <img src="images/firefox-icon.png" alt="My test image">
   ```

    
# Anatomy of an HTML document

That wraps up the basics of individual HTML elements, but they aren't handy on their own

```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>My test page</title>
  </head>
  <body>
    <img src="images/firefox-icon.png" alt="My test image">
  </body>
</html>

```
* <!DOCTYPE html>: mean to act as links to a set of rules that the HTML page had to follow to be considered good HTML, which could mean automatic error checking and other useful things.


* <html></html>: This element wraps all the content on the entire page and is sometimes known as the root element.

* <head></head>: This element acts as a container for all the stuff you want to include on the HTML page that isn't the content you are showing to your page's viewers. 

* <meta charset="utf-8">: This element sets the character set your document should use to UTF-8 which includes most characters from the vast majority of written languages. 

* <title></title>: This sets the title of your page, which is the title that appears in the browser tab the page is loaded in. 

* <body></body>: This contains all the content that you want to show to web users when they visit your page, whether that's text, images, videos, games, playable audio tracks, or whatever else.

## Images
Let's turn our attention to the <img> element again:
```
<img src="images/firefox-icon.png" alt="My test image">
```

## Marking up text
This section will cover some of the essential HTML elements you'll use for marking up the text.

### Headings
Heading elements allow you to specify that certain parts of your content are headings . HTML contains 6 heading levels, <h1>–<h6>, although you'll commonly only use 3 to 4 at most:
```
<h1>My main title</h1>
<h2>My top level heading</h2>
<h3>My subheading</h3>
<h4>My sub-subheading</h4>
```
### Paragraphs
As explained above, <p> elements are for containing paragraphs of text:
```
<p>This is a single paragraph</p>
Add your sample text (you should have it from What will your website look like?) into one or a few paragraphs, placed directly below your <img> element.
```

### Lists
The most common list types are ordered and unordered lists:

* Unordered lists are for lists where the order of the items doesn't matter, such as a shopping list. These are wrapped in a <ul> element.

* Ordered lists are for lists where the order of the items does matter, such as a recipe. These are wrapped in an <ol> element.
Each item inside the lists is put inside an <li> (list item) element.

For example:
```
<p>At Mozilla, we’re a global community of technologists, thinkers, and builders working together ... </p>
We could modify the markup to this

<p>At Mozilla, we’re a global community of</p>

<ul>
  <li>technologists</li>
  <li>thinkers</li>
  <li>builders</li>
</ul>

<p>working together ... </p>

```
### Links
Links are very important — they are what makes the web a web! To add a link, we need to use a simple element — <a> — "a" being the short form for "anchor". 
```
<a href="https://www.mozilla.org/en-US/about/manifesto/">Mozilla Manifesto</a>
```

# Semantics
In programming, Semantics refers to the meaning of a piece of code — for example "what effect does running that line of JavaScript have?", or "what purpose or role does that HTML element have" (rather than "what does it look like?".)

## Semantics in JavaScript
In JavaScript, consider a function that takes a string parameter, and returns an <li> element with that string as its textContent. 

## Semantics in CSS
In CSS, consider styling a list with li elements representing different types of fruits.

## Semantics in HTML

In HTML, for example, the <h1> element is a semantic element, which gives the text it wraps around the role (or meaning) of "a top level heading on your page."

```
<h1>This is a top level heading</h1>
```
On the other hand, you could make any element look like a top level heading. Consider the following:

``` 
<span style="font-size: 32px; margin: 21px 0;">Is this a top level heading?</span>
```
## Semantic elements
These are some of the roughly 100 semantic elements available:
```
* <article>
* <aside>
* <details>
* <figcaption>
* <figure>
* <footer>
* <header>
* <main>
* <mark>
* <nav>
* <section>
* <summary>
* <time>

```
