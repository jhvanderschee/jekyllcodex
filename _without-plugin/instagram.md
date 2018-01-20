---
title: "Instagram"
---

### Introduction

This script creates an image gallery. The script reads all images from a specific (user-defined) folder in Jekyll, automagically crops them to 300px squares, using an image resize proxy service and shows them in rows of five.

{% include instagram.html %}

### How it works

This script loads instafeed.js and requires three variables: accessToken, userId and clientId.

### Installation

Step 1. Download the file [share-buttons.html](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/_includes/instagram.html)
<br />Step 2. Save the file in the '_includes' directory of your project
<br />Step 3. Add the following line to your layout on the place where you want the share buttons to appear:

```
{% raw %}{% include instagram.html %}{% endraw %}
```