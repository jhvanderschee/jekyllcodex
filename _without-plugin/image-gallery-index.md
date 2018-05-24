---
title: Image gallery index
galleries:
  - title: Link to homepage
    image: /uploads/album/1.jpg
    url: /
  - title: Link to image gallery
    image: /uploads/album/2.jpg
    url: /without-plugin/image-gallery
---

### Introduction

This script creates an image gallery index. This can be used for all kind of image links (not just to pages with galleries). An example is shown below.

{% include image-gallery-index.html %}

### How it works

The image gallery index works like the [image gallery](/without-plugin/image-gallery).

[expand]

```
{% include image-gallery-index.html %}
```

Note that the images are being resized and served by [images.weserv.nl](https://images.weserv.nl).

[/expand]

### Installation

Step 1. Download the file [image-gallery-index.html](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/_includes/image-gallery-index.html)
<br />Step 2. Save the file in the ‘_includes’ directory of your project
<br />Step 3. Add the following line to your layout on the place where you want the image gallery index to appear:
```
{% raw %}{% if page.galleries %}{% include image-gallery-index.html %}{% endif %}{% endraw %}
```
Step 4. Add the following front matter to the page where you want the image gallery index to appear:
```
---
galleries:
  - title: Link to homepage
    image: /uploads/album/1.jpg
    url: /
  - title: Link to image gallery
    image: /uploads/album/2.jpg
    url: /without-plugin/image-gallery
---
```