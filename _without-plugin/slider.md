---
title: Slider/Carousel
carousels:
  - images:
    - image: "/uploads/slider/ganapathy-kumar-93498_scaled.jpg"
    - image: "/uploads/slider/samuel-zeller-356272_scaled.jpg"
    - image: "/uploads/slider/samuel-zeller-356338_scaled.jpg"
    - image: "/uploads/slider/ricardo-gomez-angel-180819_scaled.jpg"
  - images:
    - image: "/uploads/slider/ricardo-gomez-angel-180819_scaled.jpg"
    - image: "/uploads/slider/ganapathy-kumar-93498_scaled.jpg"
    - image: "/uploads/slider/samuel-zeller-356272_scaled.jpg"
    - image: "/uploads/slider/samuel-zeller-356338_scaled.jpg"
---

### Introduction

A lot of websites have a slider (or carousel). Most of them in the header. The big question is: [Should I use a carousel?](http://shouldiuseacarousel.com/) If you decide you should... this page shows you how to use a decent one. The carousel is based on this [pure CSS carousel](https://codeburst.io/how-to-pure-css-carousel-ce1a8cb231c8) with plenty of [options](https://codepen.io/jh3y/pen/WwVKLN). Content is stored in YML in the data directory. Design decisions are stored in the include variables.

### How it works

The code allows you to set the height of the slider as an integer (number), and the unit in as '%' or 'px'. You can define how long each slide should stay on the screen (in seconds). An interesting feature, is the option to make the slider responsive. If you set the height to '50' and the unit to '%', the dimensions will always be 2:1, but the height will vary. If you set the height to '300' and the unit to 'px' the height will always be the same, but the dimensions will vary. Note that the CSS in this script replaces the default icons for big HTML arrows and uses background images to ensure that the slider maintains the same height. Click the 'read more' link for a demo.

[expand]

{% include carousel.html height="50" unit="%" duration="7" number="1" %}

{% include carousel.html height="50" unit="%" duration="7" number="2" %}

[/expand]

### Installation

Step 1. Download the file [carousel.html](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/_includes/carousel.html)
<br />Step 2. Save the file in the '_includes' directory of your project
<br />Step 3. Add this to your layout:

```
{% raw %}
  {% include carousel.html height="50" unit="%" duration="7" number="1" %}
{% endraw %}
```
Step 4. Create a YML array called 'carousels' in your front matter with this content:

```
carousels:
  - images: 
    - image: /uploads/slider/image1.jpg
    - image: /uploads/slider/image2.jpg
    - image: /uploads/slider/image3.jpg
    - image: /uploads/slider/image4.jpg
  - images: 
    - image: /uploads/slider/image5.jpg
    - image: /uploads/slider/image6.jpg
    - image: /uploads/slider/image7.jpg
    - image: /uploads/slider/image8.jpg
```
