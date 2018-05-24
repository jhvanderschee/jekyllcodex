---
title: Image gallery index
galleries:
  - title: Gallery 1
    image: /uploads/album/1.jpg
    url: /
  - title: Gallery 2
    image: /uploads/album/2.jpg
    url: /without-plugins
---

### Introduction

This script creates an image gallery index. 

{% include image-gallery-index.html %}

### How it works

...

[expand]

```
---
galleries:
  - title: Gallery 1
    image: /
---
```

Note that the images are being resized and served by [images.weserv.nl](https://images.weserv.nl).

[/expand]

### Installation

Step 1. Download the file [image-gallery-index.html](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/_includes/image-gallery-index.html)
<br />Step 2. Save the file in the ‘_includes’ directory of your project
<br />Step 3. Add the following line to your layout on the place where you want the image gallery index to appear:

```
{% raw %}{% include image-gallery.html folder="/uploads/album" %}{% endraw %}
```