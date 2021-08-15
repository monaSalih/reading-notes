## What Google Learned From Its Quest to Build the Perfect Team

![htm](htm3.PNG)

1. Psychological safety: Everyone feels safe in taking risks around their team members, and that they won’t be embarrassed or punished for doing so.

![htm](https://static01.nyt.com/images/2016/02/28/magazine/28mag-teams1/28mag-teams1-superJumbo.jpg?quality=90&auto=webp)

2. Dependability: Everyone completes quality work on time.
3. Structure and clarity: Everyone knows what their specific expectations are. These expectations must be challenging yet attainable.

![htm](https://static01.nyt.com/images/2016/02/28/magazine/28mag-teams2/28mag-teams2-superJumbo.jpg?quality=90&auto=webp)

4. Meaning: Everyone has a sense of purpose in their work (i.e., financial security, supporting family, helping the team succeed, etc.).
5. Impact: Everyone sees that the result of their work actually contributes to the organization’s overall goals.

![htm](https://static01.nyt.com/images/2016/02/28/magazine/28mag-teams3/28mag-teams3-superJumbo.jpg?quality=90&auto=webp)


## How I explained REST to my brother

* Who is Roy Fielding?
✔ He helped write the first web servers, that sent documents across the internet… and then he did a ton of research explaining why the web works the way it does. His name is on the specification for the protocol that is used to get pages from servers to your browser.

* Why don’t the techniques that we use today work well when we need to be able to talk to all of the machines in the world?
✔ the computers useed same protocols to send messages back and forth to each other,Because it dosn't designed to be used like that. When Fielding and his colleagues started building the web, being able to talk to any machine anywhere in the world was a primary concern. But most of the techniques developers later used to get computers to talk to each other didn't have those requirements.needed to talk to a small group of

* What is the HTTP protocol that Fielding and his friends created?
✔ is all about applying verbs to nouns. For instance, when you go to a web page, the browser does an HTTP GET on the URL you typed in and back comes a web page.

* What does a GET do? 
✔ Each of the systems would retrieve information from each other using a simple HTTP GET

* What does a POST do?
✔ it used when one system needs to add something to another system 

* What does PUT do?
✔ it used when a system wants to replace something in another system, it uses an HTTP

* What does PATCH do?
✔ The only thing left to figure out is what the data models should look like 