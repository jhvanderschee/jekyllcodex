---
title: Lightbox
---

### Introduction

Lightbox is a solution that loads your <a href="/img/logo-2x.png">image links</a>, your <a href="https://www.youtube.com/watch?v=dQw4w9WgXcQ&showinfo=0&rel=0">Youtube links</a> and your <a href="https://vimeo.com/132888648">Vimeo links</a> automatically in a minimalistic and responsive pseudo window/overlay. No adjustment to your links is required, just follow the installation instructions below.

### How it works

Links that point to images, Youtube and Vimeo video's are automagically recognized and provided with an additional class by jQuery. Video's get an additional data-id in case of a video. A listener adds the lightboxes to the body on a click on the link. The lightboxes is removed when you click on the background/overlay. You can prevent links from turning into lightboxes, by adding the 'no-lightbox' class. To achieve this in Markdown, simply write:

```
{% raw %}[video link](https://youtu.be/iWowJBRMtpc?t=90s){:.no-lightbox}{% endraw %}
```

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