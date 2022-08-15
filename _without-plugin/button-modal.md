---
title: Button modal
---

### Introduction

I got a [request](https://github.com/jhvanderschee/jekyllcodex/issues/18), asking for a modal window when you click on a link. Quite a strange request... but nothing I cannot build.

### How it works

This code looks for any link that contains the class 'buttonmodal'. This link toggles a modal window that lives the footer of your page. Clicking outside the modal closes the modal throught some javascript.

### Installation

Step 1. Download the file [buttonmodal.html](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/_includes/buttonmodal.html)
<br />Step 2. Save the file in the ‘_includes’ directory of your project
<br />Step 3. Make sure the bottom of your layout document looks like this:

```
{% raw %}...
{% include buttonmodal.html %}
</body>
</html>{% endraw %}
```
Step 4. Download the file [buttonmodal.yaml](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/_data/buttonmodal.yaml)
<br />Step 5. Save the file in the ‘_data’ directory of your project
<br />Step 6. Add a link with a class 'buttonmodal' to your content using `{:.buttonmodal}`.