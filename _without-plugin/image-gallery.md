---
title: Image gallery
---

### Introduction

Below you will find a image gallery. This image gallery reads all images from a specific (user-defined) folder in Jekyll and automagically crops them to 300px squares, using the [images.weserv.nl](https://images.weserv.nl) image resize proxy service. Then it uses the lightbox functionality.

{% include image-gallery.html folder="/uploads/seattle" %}

<p style="position: relative; margin-top: -7px; font-style: italic;">'Seattle' by Sergei Akulich (from <a href="https://unsplash.com" style="color: #777777; text-decoration: underline;">Unsplash.com</a>)</p>

### How it works

The script searches for any file with a path that contains the string given in 'folder' and checks whether it is a 'jpg' file. If so, it creates an image tag for the image. The source is a 300 pixel wide square cropped version of the image. Then the script wraps the image in a link, containing the full path to the image. This will trigger the lightbox later on.

[expand]

```
{% raw %}<style>
    .image-gallery {overflow: auto; margin-left: -10px;}
    .image-gallery a {float: left; display: block; margin: 0 0 10px 10px; width: calc(20% - 10px);}
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

[/expand]

### Installation

Step 1. Download the file [image-gallery.html](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/_includes/image-gallery.html)
<br />Step 2. Save the file in the ‘_includes’ directory of your project
<br />Step 3. Add the following line to your layout on the place where you want the image gallery to appear:

```
{% raw %}{% include image-gallery.html folder="/uploads" %}{% endraw %}
```