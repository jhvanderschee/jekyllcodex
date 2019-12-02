---
title: Randomize
---

### Introduction

Sometimes you want to create a randomized list of items. In a static site this is quite hard, because random in Liquid means random at build time. This script, however, randomizes at each visit/page load using Javascript.

### How it works

This scripts shuffles all items in the page that have the class randomize. Make sure you hide the items you do not want to show with CSS. To prevent the potentially massive amount of DOM elements to take up too much memory and bandwith, you can write all image sources as 'data-src'. This script will rewrite only the visible ones to 'src'. The same can be done for background images, by using 'data-style' on your elements.

[expand]

Here is some example HTML:

```
<ul class="randomize">
  <li>Item 0</li>
  <li>Item 1</li>
  <li>Item 2 <img data-src="https://jekyllcodex.org/uploads/grumpycat2.jpg" /></li>
</ul>
```

And some example CSS:

```
.randomize > * {display: none;}
.randomize > *:nth-child(1), .randomize > *:nth-child(2) {display: block;}
```

You can use this script as many times on a page as you like.

[/expand]

### Installation

Step 1. Download the file [randomize.html](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/_includes/randomize.html)
<br />Step 2. Save the file in the '_includes' directory of your project
<br />Step 3. Add the 'randomize' class to the parent of the elements you want to randomize
<br />Step 4. Make sure the bottom of your layout document looks like this:

```
{% raw %}...
{% include randomize.html %}
</body>
</html>{% endraw %}
```