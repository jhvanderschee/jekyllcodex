---
title: Lightbox
---

### Introduction

Lightbox: image links that automatically load in a nice pseudo window.

### How it works

The following code looks at the permalink and translates it into a breadcrumb/path:

```
{% raw %}...{% endraw %}
```

### Example

<a href="/img/logo-2x.png"><img src="/img/logo-2x.png" /></a>

### Installation

Step 1. Download the file [lightbox.html](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/_includes/lightbox.html)
<br />Step 2. Save the file in the '_includes' directory of your project
<br />Step 3. Make sure the bottom of your layout document looks like this:

```
{% raw %}...
{% include lightbox.html %}
</body>
</html>{% endraw %}
```

Step 4. Download the file [jquery-3.2.1.min.js](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/js/jquery-3.2.1.min.js)
<br />Step 5. Save the file in the '/js/' directory of your project
<br />Step 6. Make sure jQuery is loaded by adding it to the head like this:

```
{% raw %}<!DOCTYPE html>
<html>
<head>
<script src="/js/jquery-3.2.1.min.js"></script>
...
</head>{% endraw %}
```