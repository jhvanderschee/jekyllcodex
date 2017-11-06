---
title: Reading time
---

### Introduction

The reading time indicator is a simple script which helps to create a reading indicator displaying the estimated reading time for the content. The script calculates the reading time based on a configurable reading speed (180 words per minutes by default).

### How it works

To display the reading time of an article, the code below is used.

[expand]

```
{% raw %}{% capture words %}
{{ content | number_of_words | minus: 180 }}
{% endcapture %}
{% unless words contains '-' %}
{{ words | plus: 180 | divided_by: 180 | append: ' minutes to read' }}
{% endunless %}{% endraw %}
```

[/expand]

### Installation

Step 1. Download the file [reading-time.html](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/_includes/reading-time.html)
<br />Step 2. Save the file in the '_includes' directory of your project
<br />Step 3. Add the following line to your layout on the place where you want the reading time indicator to appear:

```
{% raw %}{% include reading-time.html %}{% endraw %}
```