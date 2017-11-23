---
title: "Randomize"
---

### Introduction

Sometimes when you want to create a randomized list of items. Especially when you want to show only the first few items (using CSS). 

### How it works

This scripts shuffles all items with the class randomize. Note that this script can be used only once on a page.

[expand]

```
{% include randomize.html %}
```

[/expand]

### Installation

Step 1. Download the file [randomize.html](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/_includes/randomize.html)
<br />Step 2. Save the file in the '_includes' directory of your project
<br />Step 3. Make sure the bottom of your layout document looks like this:

```
{% raw %}...
<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.3/jquery.min.js"></script>
{% include randomize.html %}
</body>
</html>{% endraw %}
```