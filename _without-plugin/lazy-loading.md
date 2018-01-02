---
title: Lazy loading
---

### Introduction

Sometimes pages contain an awful lot of images. In that case you want these images to only load when the user scrolls down. This principle is called lazy loading and it is the opposite of pre-loading.

### How it works

Use it like this:

```
<img src="/img/blank.png" alt="" data-echo="/img/actualimage.jpg">
```

... or for background images like this:

```
<div style="background: url(/img/blank.png) center center no-repeat; background-size: cover;" data-echo-background="/img/actualimage.jpg"></div>
```

Note that you can create a (popular and) fancy effect by replacing the 'blank.png' image by a very small version of the actual image. This will cause a blur that is being resolved on scroll.

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