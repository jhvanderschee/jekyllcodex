---
title: "Mobile menu"
---

### Introduction

This page is coming soon... Do not want to wait? Send me an email on <a href="mailto:jhvanderschee@gmail.com" style="color: #777777;">jhvanderschee@gmail.com</a>.

### How it works

...

[expand]

```
{% raw %}{% include mobile-menu.html color="#777777" %}{% endraw %}
```

[/expand]

### Installation

Step 1. Download the file [mobile-menu.html](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/_includes/mobile-menu.html)
<br />Step 2. Save the file in the '_includes' directory of your project
<br />Step 3. Make sure the bottom of your layout document looks like this:

```
{% raw %}...
<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.3/jquery.min.js"></script>
{% include mobile-menu.html color="#777777" %}
</body>
</html>{% endraw %}
```