---
title: Instagram
---

### Introduction

You have to put the word 'instafeed.io' in your Instagram 'bio'. After you have done this, this script displays the first few images from the instagram homepage of a user:

{% include instagram.html username="jhvanderschee" %}

### How it works

For information on how this works, visit [instafeed.io](https://www.instafeed.io). When your images are showing up (which might take a few seconds and a refresh) they are no longer fetched from Instagram. Do you like it? [Buy me something!](/donate/)

### Installation

Step 1. Download the file [instagram.html](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/_includes/instagram.html)
<br />Step 2. Save the file in the '_includes' directory of your project
<br />Step 3. Add the following line to your layout on the place where you want your instagram pictures to appear:

```
{% raw %}{% include instagram.html username="jhvanderschee" %}{% endraw %}
```
