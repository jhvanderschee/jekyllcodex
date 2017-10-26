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
<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.3/jquery.min.js"></script>
{% include lightbox.html %}
</body>
</html>{% endraw %}
```