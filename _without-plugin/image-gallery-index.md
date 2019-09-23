---
title: Image gallery index
galleries:
- title: Link to homepage
  image: "/uploads/album/Beautiful Mountains.jpg"
  url: "/"
- title: Link to image gallery
  image: "/uploads/album/Museum of Pop Culture.jpg"
  url: "/without-plugin/image-gallery"
---

### Introduction

This script creates an image gallery index. This can be used for all kind of image links (not just to pages with galleries). An example is shown below.

{% include image-gallery-index.html %}

### How it works

The image gallery index works like the [image gallery](/without-plugin/image-gallery){:.gray}.

[expand]

```
{% raw %}<style>
    .image-gallery-index {overflow: auto; margin-left: -1%!important;}
    .image-gallery-index a {float: left; display: block; margin: 0 0 1% 1%; width: 19%;}
    .image-gallery-index a img {width: 100%; display: block;}
    .image-gallery-index a .caption {display: block; text-align: center; padding-top: 2px;}
</style>

<p class="image-gallery-index">{% for item in page.galleries %}<a href="{{ item.url }}" title="{{ item.title }}"><img src="//images.weserv.nl/?url={{ site.url | replace: 'http://','' | replace: 'https://','' }}{{ item.image }}&w=300&h=300&output=jpg&q=50&t=square" /><span class="caption">{{ item.title }}</span></a>{% endfor %}</p>{% endraw %}
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