# JavaScript
JavaScript is a prototype-based, multi-paradigm, single-threaded, dynamic language, supporting object-oriented, imperative, and declarative (e.g. functional programming) styles.While it is most well-known as the scripting language for Web pages, many non-browser environments also use it, such as Node.js, Apache CouchDB and Adobe Acrobat.

# Tutorials
> how to program in JavaScript with guides and tutorials.

#### For complete beginners 
you can following modul to learn JS if you dont have previose knowladge:

* [JavaScript first steps](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks) 

* [JavaScript building blocks](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks)

* [Introducing JavaScript objects](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects)
[Asynchronous JavaScript](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Asynchronous)
* [Client-side web APIs](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Client-side_web_APIs)

you can use [JavaScript guide](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide)

## Intermediate
* Understanding client-side JavaScript frameworks

providing developers with proven tools for building scalable, interactive web applications.

* A re-introduction to JavaScript:

An overview for those who think they know about JavaScript.

* JavaScript data structures:
Overview of available data structures in JavaScript.

* Equality comparisons and sameness:

JavaScript provides three different value-comparison operations:
 * strict equality using ===
 * loose equality using == 
 * and the Object.is() method.

 # Input Output in plain JavaScript


>examples/js/pure_js_greating.html

```

<html>
<head>
  <title>Hello World</title>
</head>
<body>
 
First name: <input id="first_name">
Last name: <input id="last_name">
<button id="say">Say hi!</button>
 
<hr>
<div id="result"></div>
 
<script>
function say_hi() {
    var fname = document.getElementById('first_name').value;
    var lname = document.getElementById('last_name').value;
 
    var html = 'Hello <b>' + fname + '</b> ' + lname;
 
    document.getElementById('result').innerHTML = html;
}
 
document.getElementById('say').addEventListener('click', say_hi);
</script>
 
</body>
</html>
 ```
 

## If you click on the [Try link](https://code-maven.com/try/examples/js/pure_js_greating.html), you'll see two input boxes and a button



# Creating HTML is cumbersome

In the back-end systems written in Perl, Python or Ruby, people have encountered the same problem and the solution was the creation of various templating engines. Basically a template would be an HTML snippet with some place holders and then a function call that gets the HTML snippet (the template) as a parameter, and gets several key-value pairs. The function then returns a new HTML snippet in which the place holders were replaced by the value of the appropriate key.
