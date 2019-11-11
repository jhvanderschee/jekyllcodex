---
title: Lightbox
---

### Introduction

Lightbox is a solution that loads your [image](/uploads/grumpycat2.jpg){:.gray} [links](/uploads/grumpycat.jpg){: .gray}, your [Youtube links](https://www.youtube.com/watch?v=dQw4w9WgXcQ&showinfo=0&rel=0){: .gray} and your [Vimeo links](https://vimeo.com/132888648){: .gray} automatically in a minimalistic and responsive pseudo window/overlay. No adjustment to your links is required, just follow the installation instructions below.

### How it works

Links that point to images, Youtube and Vimeo video's are automagically recognized and provided with an additional class by jQuery. Video's get an additional data-id in case of a video. A listener adds the lightboxes to the body on a click on the link. The lightboxes is removed when you click on the background/overlay. You can prevent links from turning into lightboxes, by adding the 'no-lightbox' class. To achieve this in Markdown, simply use the code below.

[expand]

```
{% raw %}[video link](https://youtu.be/iWowJBRMtpc?t=90s){:.no-lightbox}{% endraw %}
```

Note that I wrote this lightbox myself and tested it on a minimal amount of devices. It should work on mobile (tested on Android), IE9+ and all modern desktop browsers (tested on Firefox).

[/expand]

### Installation

Step 1. Download the file [lightbox.html](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/_includes/lightbox.html)
<br />Step 2. Save the file in the '_includes' directory of your project
<br />Step 3. Make sure the head of your layout document looks like this:

```
{% raw %}...
{% include lightbox.html %}
</head>
</html>{% endraw %}
```
