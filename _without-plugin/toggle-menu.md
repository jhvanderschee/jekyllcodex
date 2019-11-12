---
title: Toggle menu
---

### Introduction

This script puts a menu bottom Every website needs a menu button. You know... the much debated hamburger that toggles the menu on mobile. It is best practise to add the word 'Menu' to the hamburger and to add a little animation that transforms the hamburger into the close button. An example of this script can be seen on mobile in the header of this website.

### How it works

This script toggles the class 'menuopen' on the body, which will make it easy to make your menu responsive. I deliberately left out any other header styling or assumptions about your layout. Flexbox is your friend when you are creating a menu bar. Suggested additional styling includes:

```
#togglemenu {display: none; cursor: pointer;}
@media (max-width: 1000px) {
    #togglemenu {display: block;}
    #menu ul {display: none;}
    .menuopen #menu ul {display: block;}
}
```
The code can be found here.

[expand]

```
{% include toggle-menu.html %}
```

[/expand]

### Installation

Step 1. Download the file [text-expand.html](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/_includes/toggle-menu.html)
<br />Step 2. Save the file in the '_includes' directory of your project
<br />Step 3. Add the following code to the place where you want the menu button to appear

```
{% raw %}{% include text-expand.html %}{% endraw %}
```