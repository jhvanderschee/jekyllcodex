---
title: Add to home screen
---

### Introduction

This page is coming soon... Do not want to wait? Send me an email on <a href="mailto:jhvanderschee@gmail.com" style="color: #777777;">jhvanderschee@gmail.com</a>.

### Installation

Step 1. Download the file [add-to-homescreen.html](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/_includes/add-to-homescreen.html)
<br />Step 2. Save the file in the '_includes' directory of your project
<br />Step 3. Make sure the bottom of your layout document looks like this:

```
{% raw %}...
<script src="/js/jquery.min.js"></script>
{% include add-to-homescreen.html %}
</body>
</html>{% endraw %}
```