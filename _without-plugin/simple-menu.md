---
title: Simple menu
---

### Introduction

This static single-level menu highlights the right page. The code is independent of the permalink style used by Jekyll.

### How it works

The navigation of your website should be an unordered list. To get the list items to lighten up when they are active, the script adds an active class to them. This class should be styled with CSS. To detect which link is active, the script uses 'contains', as you can see in the code below. 

[expand]

```
{% raw %}<ul>
  <li {% if page.url contains '/getting-started' %}class="active"{% endif %}><a href="/getting-started/">Getting started</a></li>
  <li {% if page.url contains '/without-plugin' %}class="active"{% endif %}><a href="/without-plugins/">Without plugins</a></li>
  <li {% if page.url contains '/about' %}class="active"{% endif %}><a href="/about/">About</a></li>
  <li {% if page.url contains '/blog' %}class="active"{% endif %}><a href="/blog/">Blog</a></li>
</ul>{% endraw %}
```

This code is compatible with all permalink styles in Jekyll. The 'contains' statement succesfully highlights the first menu item at the following URL's: 

- getting-started/
- getting-started.html
- getting-started/index.html
- getting-started/subpage/
- getting-started/subpage.html

[/expand]

### Installation

Step 1. Download the file [simple-menu.html](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/_includes/simple-menu.html) and adjust it
<br />Step 2. Save the file in the '_includes' directory of your project
<br />Step 3. Add the following statement to your layout where you want the menu to appear:

```
{% raw %}{% include simple-menu.html %}{% endraw %}
```

PS. Do not forget to style the 'active' class in your CSS.
            