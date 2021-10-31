# Web scraping:

![](https://serpapi.com/blog/content/images/2021/08/Google_final.jpg)

Web scraping: is data scraping used for extracting data from websites. The web scraping software may directly access the World Wide Web using the Hypertext Transfer Protocol or a web browser.

## Reasons for Web Scraping:
Automated web scraping can be a solution to speed up the data collection process. You write your code once, and it will get the information you want many times and from many pages.

## Challenges of Web Scraping

* Variety: Every website is different. While you’ll encounter general structures that repeat themselves, each website is unique and will need personal treatment if you want to extract the relevant information.

* Durability: Websites constantly change. Say you’ve built a shiny new web scraper that automatically cherry-picks what you want from your resource of interest.

## Building a web scraper: Python prepwork
* Getting to the libraries:

there are several types of Python web scraping libraries from which you can choose:
- Requests
```
pip install requests
```
Requests library provides easy methods for sending HTTP GET and POST requests. For example, the function to send an HTTP Get request is aptly named get():
```
import requests
response = requests.get("https://oxylabs.io/”)
print(response.text)
```


- Beautiful Soup: Beautiful Soup is a Python library that works with a parser to extract data from HTML and can turn even invalid markup into a parse tree.
```
#Part 1 – Get the HTML using Requests

import requests
url='https://oxylabs.io/blog'
response = requests.get(url)
```
```
#Part 2 – Find the element

from bs4 import BeautifulSoup
soup = BeautifulSoup(response.text, 'html.parser')
print(soup.title)
```

- lxml:  this library is impacted by poorly designed HTML, making its parsing capabilities impeded. 

```
pip install lxml
```


- Selenium:
Selenium requires three components:

* Web Browser – Supported browsers are Chrome, Edge, Firefox and Safari
* Driver for the browser – See this page for links to the drivers
* The selenium package 

### Beware of Honey Pot Traps
This detection is obviously not easy and requires a significant amount of programming work to accomplish properly, as a result, this technique is not widely used on either side – the server side or the bot or scraper side.

### Check if Website is Changing Layouts
Some websites make it tricky for scrapers, serving slightly different layouts.
>For example, in a website pages 1-20 will display a layout, and the rest of the pages may display something else. 

### Avoid scraping data behind a login
Login is basically permission to get access to web pages. Some websites like Indeed do not allow permission.

Its generally preferred to avoid scraping websites that have a login as you will get blocked easily, but one thing you can do is imitate human browsers whenever authentication is required you get the target data you need.

### How can websites detect and block web scraping?

Websites can use different mechanisms to detect a scraper/spider from a normal user. Some of these methods are enumerated below:

1. Unusual traffic/high download rate especially from a single client/or IP address within a short time span.

2. Repetitive tasks performed on the website in the same browsing pattern – based on an assumption that a human user won’t perform the same repetitive tasks all the time.

3. Checking if you are real browser – A simple check is to try and execute javascript. 

4. Detection through honeypots – these honeypots are usually links which aren’t visible to a normal user but only to a spider. 

### How do you find out if a website has blocked or banned you?
If any of the following signs appear on the site that you are crawling, it is usually a sign of being blocked or banned.

- CAPTCHA pages
- Unusual content delivery delays
- Frequent response with HTTP 404, 301 or 50x errors
