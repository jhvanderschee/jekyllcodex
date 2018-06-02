---
title: "Cookie notice"
---

### Introduction

...

### How it works

...

### Installation

Step 1. Download the file [cookie-notice.html](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/_includes/cookie-notice.html)
<br />Step 2. Save the file in the '_includes' directory of your project
<br />Step 3. Make sure the bottom of your layout document looks like this:

```
{% raw %}...
<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.3/jquery.min.js"></script>
{% include cookie-notice.html %}
</body>
</html>{% endraw %}
```