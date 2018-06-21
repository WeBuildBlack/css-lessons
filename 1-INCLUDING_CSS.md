# Including CSS
There are multiple different ways to link your CSS to your HTML page. There are ups and downs to all ways, and you should link carefully about each one as it can have an effect of your productivity level.

## The Options
* *Linked* - an external file connected using a *link* tag in the *head* of your HTML file
* *Imported* - a CSS file imported into another CSS file.
* *Embedded* - CSS styles written in using a *style* tag in the HTML file
* *In-line* - CSS styles for a specific element applied using the *style* attribute on a tag


## Linked CSS
This way is the one of the most popular as it's good for file organization. Linked CSS is when you put your CSS rules in a seperate document, usally with a *.css* file extension. Then you link that file to the HTML file using a *link* tag like so:
```html
<link href="someFile.css" rel="stylesheet" type="text/css" media="all">
```
All *link* tags should typically be placed in the *head*. Also, be aware that you can link to as many CSS files as you like. You just have to use a different *link* tag for each one.  
The *href* attribute, similar to the *a* tag in HTML, is for the URL to the actual CSS file. You can use absolute or relative paths.  
The *media* attribute is to define for what media types this stylesheet applies to. Here are some media types:
* *all* - all devices
* *screen* - computer screens
* *print* - for when the page is printed
* *speech* - for when the page is spoken using something like a screenreader

So let's say we have this CSS file:
```css
h1 {
    text-decoration: underline;
    color: blue;
}
p {
    padding-left: 20px;
    font-size: 18px;
}
```
Now if we wanted to link it to an HTML file, we would do it like so:  
```html
<!doctype html>
<html>
    <head>
        <title>This is an HTML Page</title>
        <meta name="description" content="Our HTML page">
        <meta name="keywords" content="html tutorial css">
        <link href="style.css" rel="stylesheet">
    </head>
    <body>
        <h1>Big Title Here</h1>
        <p>Just another smaller description about something going on.</p>
    </body>
</html>
```
You will notice the link tag above, and the face that it is pointing to *style.css*. Now because the path is just a file name it means the CSS file must be on the saem folder level as the HTML file.  
The cool thing about linked CSS files is that you can put your rules in a seperate file and link it to as many HTML files as you like. Another upside is speed. Once the linked style sheet has been downloaded, the first time the browser will keep a copy. Then when you go to other pages it doesn't have to keep re-downloading the CSS rules.

## Imported CSS
Importing CSS is when you bring other CSS files together into one. For example, let's say we have this CSS file called *outer.css*:
```css
h1 {
    text-decoration: underline;
}
p {
    padding-left: 20px;
    font-size: 18px;
}
```
If I wanted to merge these rules into another CSS file, *inner.css*, I could do that like so:
```css
@import url("outer.css");

h1 {
color: blue;
}
```
Now when I connect *inner.css* to an HTML file it will have the rules both files applied.
```html
<!doctype html>
<html>
    <head>
        <title>Sports Department</title>
        <link href="sports_style.css" rel="stylesheet">
    </head>
...
```

## Embedded CSS
Embedded CSS is when you use a *style* tag to include rules in the *head* of a HTML document. For example:
```html
<!doctype html>
<html>
    <head>
        <title>Embedded CSS example</title>
        <meta name="description" content="A page with embedded css">
        <meta name="keywords" content="html css embedded">
        <style>
            h1 {
            text-decoration: underline;
            color: blue;
            }
            p {
            padding-left: 20px;
            font-size: 18px;
            }
        </style>
    </head>
    <body>
        ...
    </body>
</html>
```

The rules we see in the *style* tag in the head will apply for all the specific HTML elements in this file. It's just that simple.

## In-line CSS
In-line is when we apply the CSS rules directly on the tag suing the *style* attribute. For example:
```html
<body>
    <h1 style="text-decoration:underline;color:blue;" >Unicycling</h1>
    <p style="padding-left:20px;font-size:18px;" >It takes twice the man to ride
    with half the wheels.</p>
</body>
```

## Overriding Rules
You can actually use multiple of these methods together. So what happens when you have rules that clash. In that case there is an order in which things will be overridden.
* Linked CSS will override the imports
* Embedded CSS will override linked CSS
* In-line CSS will override Embedded CSS

Essentially, the closer to the actual element the CSS is, the higher on the priority it goes.

## Stick around for the next episode...
In the next lesson, we'll be going over some of the basic CSS rules for text, colors, and spacing.
