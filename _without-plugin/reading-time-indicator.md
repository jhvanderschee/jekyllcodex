---
title: Reading time indicator
---

### Introduction



### How it works

To display the reading time of an article, just use the following code:

```
{% raw %}{% capture words %}
{{ content | number_of_words | minus: 180 }}
{% endcapture %}
{% unless words contains '-' %}
{{ words | plus: 180 | divided_by: 180 | append: ' minutes to read' }}
{% endunless %}{% endraw %}
```

### Installation

Step 1. Download the file <a href="https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/_includes/breadcrumbs.html">reading-time.html</a>
<br />Step 2. Save the file in the '_includes' directory of your project
<br />Step 3. Add the following line to your layout on the place where you want the reading time indicator to appear:

```
{% raw %}{% include reading-time.html %}{% endraw %}
```