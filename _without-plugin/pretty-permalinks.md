---
title: Pretty URL's
---

### Introduction

The page URL is an important factor in ranking your page in the search engine. Therefore it is important to have pretty URL's (also called 'permalinks'). 

### How it works

With Jekyll you can create pretty URL's using the ‘old-school’ approach. Create an ‘index.html’ in the root for the homepage and a folder called ‘about’ with another ‘index.html’ file inside for your ‘about’ page... and so on. The Jekyll way is to add the permalink to the top of your document. Note that both options will work equally good. However, these approaches still show the .html extension. To prevent this you have to change a default setting in the '_config.yml' file.

### Installation

Add the following code to your '_config.yml' file:

```
{% raw %}permalink: /blog/:title/{% endraw %}
```