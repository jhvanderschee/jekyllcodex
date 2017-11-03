---
title: Image gallery
---

### Introduction

This script creates an image gallery. The script reads all images from a specific (user-defined) folder in Jekyll, automagically crops them to 300px squares, using an image resize proxy service and shows them in rows of five.

{% include image-gallery.html folder="/uploads/album" %}

### How it works

The script searches for any file with a path that contains the string given in 'folder' and checks whether it is a 'jpg' file. If so, it creates an image tag for the image. The source is a 300 pixel wide square cropped version of the image. Then the script wraps the image in a link, containing the full path to the image. This will trigger the lightbox if present.

[expand]

```
{% raw %}<style>
  .image-gallery {overflow: auto; margin-left: -1%;}
  .image-gallery a {float: left; display: block; margin: 0 0 1% 1%; width: 19%;}
  .image-gallery a img {width: 100%;}
</style>

<div class="image-gallery">
{% for file in site.static_files %}
  {% if file.path contains include.folder %}
    {% if file.extname == '.jpg' or 
      file.extname == '.jpeg' or 
      file.extname == '.JPG' or 
      file.extname == '.JPEG' %}
      <a href="{{ file.path }}">
        <img src="//images.weserv.nl/?url=jekyllcodex.org/{{ file.path }}&w=300&h=300&output=jpg&q=50&t=square" />
      </a>
    {% endif %}
  {% endif %}
{% endfor %}
</div>{% endraw %}
```

Note that the images are being resized and served by [images.weserv.nl](https://images.weserv.nl).

[/expand]

### Installation

Step 1. Download the file [image-gallery.html](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/_includes/image-gallery.html)
<br />Step 2. Save the file in the ‘_includes’ directory of your project
<br />Step 3. Add the following line to your layout on the place where you want the image gallery to appear:

```
{% raw %}{% include image-gallery.html folder="/uploads/album" %}{% endraw %}
```