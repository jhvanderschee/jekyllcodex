---
title: Search (Google)
---

### Introduction

Modern websites have a search bar, searching within the site for specific content. These search boxes often search the database in real-time. That is not possible within a static website. Therefore another solution must be found.

### How it works

[expand]

```
{% raw %}<form method="get" action="http://www.google.com/search" target="_blank"><input type="hidden" name="sitesearch" value="yourdomain.com" /><input type="text" name="q" maxlength="255" value="" placeholder="Search via Google" /></form>{% endraw %}
```

[/expand]

### Installation

Step 1. Download the file [search-google.html](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/_included/search-google.html) and adjust it
<br />Step 2. Save the file in the '_includes' directory of your project
<br />Step 3. Add the following statement to your layout where you want the menu to appear:

```
{% raw %}{% include search-google.html %}{% endraw %}
```