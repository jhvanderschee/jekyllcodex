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

This script creates an image gallery index. This can be used for all kind of image links (not just to pages with galleries).

{% include image-gallery-index.html %}

### How it works

Just add some Front Matter to your page

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

And add the include to your layout:

```
{% raw %}{% if page.galleries %}{% include image-gallery-index.html %}{% endif %}{% endraw %}
```

Note that the images are being resized and served by [images.weserv.nl](https://images.weserv.nl).

### Installation

Step 1. Download the file [image-gallery-index.html](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/_includes/image-gallery-index.html)
<br />Step 2. Save the file in the ‘_includes’ directory of your project
<br />Step 3. Add the following line to your layout on the place where you want the image gallery index to appear:

```
{% raw %}{% include image-gallery.html folder="/uploads/album" %}{% endraw %}
```