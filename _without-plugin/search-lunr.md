---
title: Search with Lunr.js
inactive: true
---

### Introduction

Modern websites have a search bar, searching within the site for specific content. These search boxes often search the database in real-time. That is not possible within a static website. Therefore another solution must be found.

### How it works

This search relies on a local index. It uses the Lunr.js script to search.


{% include search-lunr.html %}



### Installation

Step 1. Download the file [search-lunr.html](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/_includes/search-lunr.html)
<br />Step 2. Save the file in the '_includes' directory of your project
<br />Step 3. Add the following statement to your layout where you want the search box to appear:

```
{% raw %}{% include search-lunr.html %}{% endraw %}
```