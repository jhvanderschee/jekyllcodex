---
title: Follow buttons
---

### Introduction

You can see them in action on the right side of the screen.

### How it works

This content is coming soon...

### Installation

Step 1. Download the file [follow-buttons.html](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/_includes/follow-buttons.html)
<br />Step 2. Save the file in the '_includes' directory of your project
<br />Step 3. Make sure the bottom of your layout document looks like this:

```
{% raw %}...
{% include follow-buttons.html %}
</body>
</html>{% endraw %}
```
Step 4. Add the following variables to your '_config.yml' file (with value's):
```
facebook_url: 
twitter_url: 
linkedin_url: 
googleplus_url:
pinterest_url:
instagram_url:
```