# [Web] Build a Website
*This is how YouTube displays your cat videos.*

![build a website](.rsrc/banner.png)

# Objectives
- Understand what a web browser is
- Understand what HTML is
- Understand what code does what when you want to play a YouTube video

# Introduction
There are a number of things that most people take for granted in life--the way the internet works is a big one. Its simple, right? You navigate to a website and it appears. It's not actually this simple but it's not that complicated either. In this section we will talk about how the world wide web works and who is responsible for doing what when you navigate to a website. Is HTML a programming language? We'll discuss this devisive question and talk about what a web browser is actually doing. Understanding how websites work will help you stay safe online and will open up massive career oportunities as well.

1. [The Web Browser](#the-web-browser)
2. [Understanding HTML](#understanding-html)
3. [Serving the Website](#serving-the-website)
4. [Styling with CSS](#styling-with-css)
5. [Dynamic Actions with JavaScript](#dynamic-actions-with-javascript)

# Lesson
## The Web Browser
What is a web browser? Is it a portal to another demension? All a web browser is, is an application that knows how to interpret code and create a picture for you to see. It understands javascript to animate things and allow you to interact with the page. It also knows how to take a CSS file and use it to style the page with colors, shadows and curved borders among other things. A web browser is essentially a glorified viewing tool for web pages and provides you with a ton of additional features for analyzing whats happening like storage of data and network connections. In additional lessons we'll go deeper into the features available to you and how you can use those features to accomplish some really interesting and useful tasks.

## Understanding HTML
Markdown languages are simply a way to tell the web browser to display a certain portion of the text a certian way. Markdown languages also allow us to display graphical components like images and gifs, or even annotate code such as in the following. This page that you're viewing right now was written in a markdown language and everything that is displayed was either done so with HTML, a style sheet or javascript. Regardless the core is HTML which stands for the Hypertext Transfer Markup Language. There are other markup languages such as XML which stands for the Extensibile Markup Language.The following is an example of some HTML and a demonstration of how it would be displayed to a user in a web browser. The nate.png image is stored in the same directory as the markup file:
```
<h1>Nate Singer</h1>
<img src="nate.png" width=300/>
<p>This is a bio for Nate...</p>
```
<img src=".rsrc/html.png" width=500/>

Other markup languages use different formats but provide roughly the same framework. The premise is that we use a tag like "<h1>" to represent a header and then we can write our header details before an associated closing tag. The other point to note here is that in the img tag we see additional configuration options. These configurations range and are related to the specific tag, but typically we see these used to indiciate a data source or configure styling. Styling can also be configured as class, which will be discussed in the following CSS section.

## Serving the Website
Websites are typically served via a routing tool. This can be a variety of different technologies but generally is a single application. Python and NodeJS are commonly used to serve smaller websites while Nginx and Apache have historically been used to serve larger websites. There are other technologies like Microsoft IIS that have also been used in the past, but typically you are simply using this application to interpret HTTP requests from end users and return a webpage to the user using HTML.

Here you can see the example of using python to serve the page from the previous section to a user.
```
Serving HTTP on 0.0.0.0 port 80 (http://0.0.0.0:80/) ...
127.0.0.1 - - [30/May/2022 17:18:55] "GET /site.html HTTP/1.1" 200 -
```

We see a GET request come in for /site.html and then we respond with a HTML code 200 indicating a successful request as well as the site.html page. For more information on what a GET request is and what the response codes are, check out the respective lessons on those topics. As you learn more about web technologies these two specific components will be more and more important.

## Styling with CSS
In the HTML section we see an image being defined using an ```img``` tag. What if we want to give this curved borders. We can use a style component of the page to specify this directly, but we can also create classes in css files to do more detailed things and organize all of our code better. To round edges out in the first example, directly styling an element we would do something like ```<img src=".rsrc/html.png" style="border-radius: 10px;"/>```. If we wanted to use a dedicated css file, we would create a class in a seperate file, include the file and then include the class in our definition. For now we will ignore this case and eventually in the CSS lesson we will get into more detail on this point. The above example will give us the following:

<img src=".rsrc/rounded.png" width=500/>

## Dynamic Actions with JavaScript
Lastly, for now at least, we'll round out a discussion of common web file formats with a discussion of JavaScript. Importantly, Java and JavaScript are two distinct languages. There are a bunch of different JavaScript frameworks such as angularJS, vueJS and nodeJS to name a few, but all were built to solve specific problems. Most commonly, javascript is used to do dynamic things in a web page such as create a countdown timer. If you look at the Hack a Bit website you will see some javascript files in use to do these things. For now just know that most dynamic actions are handled by JavaScript. We will cover some of the awesome things you can do with JS as well as some security pitfalls in the JavaScript lesson later on.

# The Real World, How WebSites Work
Let's now take a look at why these concepts matter. We will walk through an examples of a website in the real world.

## 2009 - YouTube Video Player
YouTube is one of the most popular, highly-trafficked websites in the world. Let's walk through what happens when you want to view a video.
1. You download the page as HTML from www.youtube.com
2. The HTML tells your web browser to go get the CSS and JS files from the webserver by making requests in the background
3. The browser styles the page based on the CSS
4. The browser starts to download the video dynamically using JavaScript; this is why you see the white line loading progress.

# Check YoSelf
## Q1 - What type of resource is most commonly used for styling a webpage?
a. ```Python Compiled Code (PYC)```<br>
b. ```JavaScript (JS)```<br>
c. ```Hypertext Transfer Markup Language (HTML)```<br>
d. ```Cascading Style Sheets (CSS)``` <---<br>

## Q2 - What routing application is commonly used for small temporary websites?
a. ```Python3 http.server``` <---<br>
b. ```NginX```<br>
c. ```Apache```<br>
d. ```Gunicorn```<br>

## Q3 - What type of language is HTML?
a. ```Interpreted```<br>
b. ```Markdown``` <---<br>
c. ```Compiled```<br>
d. ```Assembly```<br>

# Keep Going, Next Steps
Check out the following curated resources if you'd like to keep learning about this topic to dominate hard challenges.
1. Nginx backstory - https://www.nginx.com/resources/glossary/nginx/
2. Learn CSS with Battles - https://cssbattle.dev/
3. JavaScript Challenges - https://www.jschallenger.com/ 
4. Frontend Coding Challenges - https://codier.io/ 
5. Apache Webserver - https://httpd.apache.org/ABOUT_APACHE.html
