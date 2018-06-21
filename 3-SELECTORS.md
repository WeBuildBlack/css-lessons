## Selectors!
In past lessons, we've applied CSS rules to all HTML elements of a type. What if we wanted to style a specific element? That's when selectors come in. We're going to do a quick overview of some of the more useful selectors in the examples below.

## What is a selector?
Remember, the format for CSS rules goes as such:
```css
selector {
    property: value;
    property: value;
}
```
The selector is what defines the elements that will be affected by the rules.

## Type Selectors
The *type* selectors is the most basic form of selectors. It's also what we've been using these past lessons. They refer to a type of HTML tag. For example:
```css
h1 {
    font-family: Times New Roman;
}
p {
    font-family: Verdana;
}
```

## ID's and Classes
There are a lot of times when we would like to apply a rule on a one specific element. We use the *id* attribute for that. For example, we can create an HTML file like this:
```html
<button id="idName">
``` 
Now we can target this element in our CSS like this:
```css
#idName {
    property: value;
    property: value;
}
```
The *#* is to let the CSS know you are targeting an *id*. This *id* value can be made up of letters, digits, dashes, and underscores. Technically, you can have multiple elements on a page with the same *id* value, but that would kind of defeat the purpose. If you want to group multiple elements with your CSS, we use something called a *class*.

## Classes
Classes are just like IDs, but instead of applying to just one element, they apply to multiple. For example:
```html
<body>
    <h1 >Another Title</h1>
    <p class="className">Paragraph 1</p>
    <p class="className">Paragraph 2</p>
</body>
```
Then we can target those paragraph elements like this:
```css
.className {
    property: value;
    property: value;
}
```
The *.* before the class name is used to let CSS know you're targeting a *class*.

## Descendant Elements
We can target the children of elements with *descendant elements*. For example, if I wanted to embolden every list item in an unordered list, I could do so like this:
```css
ul li {
    font-weight: bold;
}
```

## Multiple selectors
If you've ever realized that you are using the some of the same rules for different classes, you can use multiple selectors to cut some code down. For example:
```css
.className, #idName, ul li {
    property: value;
    property: value;
}
```
The properties defined will be applied to all of the selectors.

## Hover
Have you ever hovered over something on a web page and it changed in some way? We can achieve that with the *:hover* selector. For example:
```css
selector:hover {
    property: value;
    property: value;
}
```

The selector can be a type, id or class and you can apply the hover effect to any element on the page. Try this:
```css
p:hover {
    padding-left: 30px;
    color: #3366cc;
}
```
Attach that CSS to this HTML:
```html
<body>
    <p>Hover over me and see what happens!</p>
</body>
```
Now try hovering over that paragraph in your browser.

## Overlapping Rules
It's possible that at some point you have so many rules that they overlap. There is an order of overriding that goes as such:
* class selectors override type selectors
* id selectors override class selectors

Here's an example:

```css
p {
    color: green;
}
.whatcolor {
    color:  #48d3c2;
}
#whatcolor {
    color: red;
}
```
Attach this CSS to this HTML:
```html
<body>
    <p class="whatcolor" id="whatcolor">What colour am I?</p>
</body>
```
We can see in our browser that the text is red because the ID overrides everything.

## Stick around for the next episode...
In the next episode we'll be taking a deeper dive into color. It's time to make things a lil more good lookin! See you next time.
