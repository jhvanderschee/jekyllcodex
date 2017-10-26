---
title: Lightbox
---

### Introduction

Lightbox is a solution that loads <a href="/img/logo-2x.png">image</a>, <a href="https://www.youtube.com/watch?v=dQw4w9WgXcQ&showinfo=0&rel=0">Youtube</a> and <a href="https://vimeo.com/132888648">Vimeo links</a> automatically in a minimalistic and responsive pseudo window/overlay. No adjustment to your links are required, just follow the installation instructions below.

### How it works

Links that point to images, Youtube and Vimeo video's are provided with an additional class by the script, as well as a data-id in case of a video. Then a listener is added that dynamically adds the lightboxes to the body on a click. These lightboxes are removed when clicking their background/overlay.

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