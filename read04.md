# What is CSS?
(Cascading Style Sheets) allows you to create great-looking web pages, but how does it work under the hood? This article explains what CSS is, with a simple syntax example, and also covers some key terms about the language.

# What is CSS for?
** CSS ** is a language for specifying how documents are presented to users — how they are styled, laid out, etc.

* ** A document:**  is usually a text file structured using a markup language — HTML is the most common markup language, but you may also come across other markup languages such as SVG or XML.

** Presenting :** a document to a user means converting it into a form usable by your audience. Browsers, like Firefox, Chrome, or Edge , are designed to present documents visually, for example, on a computer screen, projector or printer.

```
Note: A browser is sometimes called a user agent, which basically means a computer program that represents a person inside a computer system. Browsers are the main type of user agent we think of when talking about CSS, however, it is not the only one. There are other user agents available — such as those which convert HTML and CSS documents into PDFs to be printed.

```
## CSS syntax
CSS is a rule-based language — you define rules specifying groups of styles that should be applied to particular elements or groups of elements on your web page. 

The following code shows a very simple CSS rule :
```
h1 {
    color: red;
    font-size: 5em;
}
```

A CSS stylesheet will contain many such rules, written one after the other.
```

h1 {
    color: red;
    font-size: 5em;
}

p {
    color: black;
}
```

# CSS Modules

At this stage you don't need to worry too much about how CSS is structured, however it can make it easier to find information if, for example, you are aware that a certain property is likely to be found among other similar things and are therefore probably in the same specification. 

## CSS Specifications
All web standards technologies ( _ HTML  , CSS, JavaScript, etc. _) are defined in giant documents called specifications (or "specs"), and define precisely how those technologies are supposed to behave.

## Browser support information

Once CSS has been specified then it is only useful for us in developing web pages if one or more browsers have implemented it. This means that the code has been written to turn the instruction in our CSS file into something that can be output to the screen.

The browser support status is shown on every MDN property page in a section named "Browser compatibility" For example, the compatibility section for the CSS
```
 font-familyow.
```
# How To Add CSS

When a browser reads a style sheet, it will format in three Ways to Insert CSS:

1. ### External CSS

Each HTML page must include a reference to the external style sheet file inside the <link> element, inside the head section.

```
Example
External styles are defined within the <link> element, inside the <head> section of an HTML page:

<!DOCTYPE html>
<html>
<head>
<link rel="stylesheet" href="mystyle.css">
</head>
<body>

<h1>This is a heading</h1>
<p>This is a paragraph.</p>

</body>
</html>

```

2. ### Internal CSS
An internal style sheet may be used if one single HTML page has a unique style.
```
Example
Internal styles are defined within the <style> element, inside the <head> section of an HTML page:

<!DOCTYPE html>
<html>
<head>
<style>
body {
  background-color: linen;
}

h1 {
  color: maroon;
  margin-left: 40px;
}
</style>
</head>
<body>

<h1>This is a heading</h1>
<p>This is a paragraph.</p>

</body>
</html> 
```

3. ### Inline CSS
An inline style may be used to apply a unique style for a single element.

```
Example
Inline styles are defined within the "style" attribute of the relevant element:

<!DOCTYPE html>
<html>
<body>

<h1 style="color:blue;text-align:center;">This is a heading</h1>
<p style="color:red;">This is a paragraph.</p>

</body>
</html>
```

# CSS color Property

```
Example
Set the text-color for different elements:

body {
  color: red;
}

h1 {
  color: #00ff00;
}

p.ex {
  color: rgb(0,0,255);
}
```
