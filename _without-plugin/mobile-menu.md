---
title: "Mobile menu"
---

### Introduction

If you want to add a menu to a navbar, you only have to add the menu as an unordered list with links. This script will take care of the rest. It will show a hamburger with the word 'MENU' next to it. When you press the menu, the list items will appear below each other and the button will change into an 'X' with the word 'CLOSE' next to it.

### How it works

Create a menu in the navigation bar by creating an unordered list with links. Wrap this list in a `div` with `id="mobile-menu"`. Add the script to the footer to take care of the rest.

### Installation

Step 1. Download the file [mobile-menu.html](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/_includes/mobile-menu.html)
<br />Step 2. Save the file in the '_includes' directory of your project
<br />Step 3. Make sure the bottom of your layout document looks like this:

```
{% raw %}...
<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.3/jquery.min.js"></script>
{% include mobile-menu.html color="#777777" %}
</body>
</html>{% endraw %}
```