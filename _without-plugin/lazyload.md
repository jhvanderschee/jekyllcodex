---
title: Lazy load
---

### Introduction

Coming soon...

### How it works

Use it like this:

```
<img src="img/blank.gif" alt="" data-echo="img/album-1.jpg">
```

... or for background images like this:

```
<div style="background: url(img/blank.gif) center center no-repeat; background-size: cover;" data-echo-background="img/album-1.jpg"></div>
```

### Installation

Step 1. Download the file [lazyload.html](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/_includes/lazyload.html)
<br />Step 2. Save the file in the '_includes' directory of your project
<br />Step 3. Make sure the bottom of your layout document looks like this:

```
{% raw %}...
{% include lazyload.html %}
</body>
</html>{% endraw %}
```