---
title: DOM and locators
date: 2025-02-28 00:00:00 +0800
categories: [Learning]
tags: [locators, DOM ]     # TAG names should always be lowercase
---

## 1. DOM (Document Object Model)

DOM is like a tree structure that represents everything on a web page. It allows programming languages (like JavaScript) to interact with and change a webpage dynamically. I will primarily review interactions with DOM using Java since that’s my focus for the time being. 

Here is an example of a simple HTML code block to help illustrate the picture:

```html
<!DOCTYPE html>
<html>
<head>
   <title>My Page</title>
</head>
<body>
   <h1>Hello, World!</h1>
   <p>This is a paragraph.</p>
</body>
</html>
```

In the above example, you can consider the `<html>` tag as the grandparent, `<head>` & `<body>` as parents and `<title>`, `<h1>`, `<p>` as their children.
A similar representation within the DOM tree can be seen below:

```pgsql
HTML
├── HEAD
│   └── TITLE → "My Page"
└── BODY
    ├── H1 → "Hello, World!"
    └── P → "This is a paragraph."
  ```

All HTML elements present in the DOM structure are DOM elements.

```html
<p>This is a paragraph.</p>
```
Here, `<p>` is an element of the DOM.
Nodes in DOM

There are also nodes of the DOM, which helps us to further differentiate between the different elements. Here is an example of 3 different nodes:

Nodes in DOM

There are also nodes of the DOM, which helps us to further differentiate between the different elements. Here is an example of 3 different nodes:

```html
<p id="demo">Hello</p>
```

`<p>` is our Element node. It is an element node because it is an HTML element within the DOM structure.

`Hello` is our Text node. This is the string placed within our paragraph `<p>`.

`id="demo"` is an Attribute node since id is an attribute of the `<p>` tag.

The hierarchy of the 3 nodes will look like this:

```pgsql
ELEMENT NODE: <p>
   ├── ATTRIBUTE NODE: id="demo"
   └── TEXT NODE: "Hello"
```
All 3 of the above nodes are part of the DOM structure, but not all are considered Elements, but only the Element node.

Now that we have a rough idea of what the DOM structure is, we can discuss locators.

## 2. Locators

I will review locators in the context of the DOM structure. What this basically means is that I will review techniques for locating nodes within the DOM.
A locator is basically a way to tell your software to use or interact with a given element within a web page. Going back to our previous example, we will review possible ways to locate elements and in the context of automation using Selenium’s WebDriver for Java:

```html
<!DOCTYPE html>
<html>
<head>
    <title>My Page</title>
</head>
<body>
    <h1>Hello, World!</h1>
    <p>This is a paragraph.</p>
</body>
</html>
```

As there are not as many elements, in the above example, we can go about locating them in several different ways:

```
    By.tagName
    By.xpath
    By.cssSelector
```

The most obvious and straightforward way to locate a tag is using its name. So, if we are to locate the header tag, then we will simply type in `“h1”` in our browser inspect window. This would also be specified as `By.tagName("h1")` when typing our statement in Selenium:

![Image](assets/img/byTagName.png)

Another way is to use XPath expressions:

```java
By.xpath("//h1")
```

![Image](assets/img/byXpath.png)

The same results can also be achieved using a CSS selector, but I will not go into further details as our HTML example is limited to elements of the DOM that do not have attributes or other components to work with.
Both CSS and XPath locators are the preferred techniques for finding elements of the DOM as they offer a lot of flexibility when querying. I will focus on using XPath as I find it more intuitive when searching for data.

The following table shows some common usages of XPath when locating different elements:

| **XPath Syntax**            | **Example**                    | **Description**                                                                 |
|-----------------------------|--------------------------------|---------------------------------------------------------------------------------|
| Absolute XPath              | `/html/body/h1`                | Selects the element from the root of the document, starting with `/`.           |
| Relative XPath              | `//h1`                          | Selects the element from anywhere in the document, not necessarily starting from the root. |
| Select by Tag Name          | `//h1`                          | Selects all `<h1>` tags in the document.                                         |
| Select by ID                | `//*[@id='elementId']`         | Selects an element by its `id` attribute.                                        |
| Select by Class             | `//*[@class='elementClass']`   | Selects elements by their `class` attribute.                                     |
| Select by Attribute         | `//*[@name='username']`        | Selects elements with a specific attribute, such as `name`, `type`, etc.         |
| Contains Text               | `//*[contains(text(),'Hello')]` | Selects elements whose text contains the specified string ("Hello" in this case).|
| Starts with Text            | `//*[starts-with(text(),'Hello')]` | Selects elements whose text starts with the specified string ("Hello").        |
| Contains Attribute Value    | `//*[contains(@class,'button')]` | Selects elements where the class attribute contains a specific substring (e.g., "button"). |
| Select Parent Element       | `//h1/..`                       | Selects the parent of the `<h1>` element.                                        |
| Select Child Element        | `//div/p`                       | Selects `<p>` elements that are children of `<div>` elements.                    |
| Select Specific Child       | `//div[2]/p`                    | Selects the second `<p>` child of a `<div>` element.                            |
| Select First Element        | `(//h1)[1]`                     | Selects the first `<h1>` element.                                                |
| Select Last Element         | `(//h1)[last()]`                | Selects the last `<h1>` element.                                                 |
| Logical OR                  | `//input[@type='text' or @type='password']` | Selects `<input>` elements with `type="text"` or `type="password"`.        |
| Logical AND                 | `//input[@type='text' and @name='username']` | Selects `<input>` elements that have both `type="text"` and `name="username"`.|
| Select by Index             | `//h1[1]`                       | Selects the first `<h1>` element in the document.                               |
| Select by Index (Last)      | `//h1[last()]`                  | Selects the last `<h1>` element in the document.                                |
