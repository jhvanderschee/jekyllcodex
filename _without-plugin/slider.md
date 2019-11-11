---
title: Slider
slider:
  text_color: white
  shadow_color: black
  image_width: 1000
  image_height: 500
  slides:
  - image: "/uploads/slider/ganapathy-kumar-93498.jpg"
    slide_html: 
  - image: "/uploads/slider/samuel-zeller-356272.jpg"
    slide_html: "<h3>La Passione 1/2</h3>Shirley, do you own a Ferrari?"
  - image: "/uploads/slider/samuel-zeller-356338.jpg"
    slide_html: "<h3>La Passione 2/2</h3>Yes, my life is your dream."
  - image: "/uploads/slider/ricardo-gomez-angel-180819.jpg"
    slide_html: 
---

### Introduction

A lot of websites have a slider or carousel. Most of them in the header. The carousel is based on this [pure CSS carousel](https://codeburst.io/how-to-pure-css-carousel-ce1a8cb231c8) with plenty of [options](https://codepen.io/jh3y/pen/WwVKLN). Content is stored in YML in the data directory. Design decisions are stored in the include variables.

### How it works

The code allows you to set the height of the slider as an integer (number), and the unit in as '%' or 'px'. You can define if you want the transition to be a 'slide' or a 'fade'. And finally how long each slide should stay on the screen (in seconds). An interesting feature, is the option to make the slider responsive. If you set the height to '50' and the unit to '%', the dimensions will always be 2:1, but the height will vary. If you set the height to '300' and the unit to 'px' the height will always be the same, but the dimensions will vary. Note that the CSS in this script replaces the default icons for big HTML arrows and uses background images to ensure that the slider maintains the same height. Click the 'read more' link for a demo.

[expand]

{% include carousel.html height="50" unit="%" transition="slide" duration="7" image_width="1000" image_height="500" %}

[/expand]

### Installation

Step 1. Download the file [slider.html](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/_includes/slider.html)
<br />Step 2. Save the file in the '_includes' directory of your project
<br />Step 3. Make sure you load Twitter Bootstrap 3.3.7 and add this to your layout:

```
{% raw %}{% if page.slider %}
  {% include slider.html height="50" unit="%" transition="slide" duration="7" %}
{% endif %}{% endraw %}
```
Step 4. Add this YML to the head of your Markdown file:

```
slider:
  text_color: white
  shadow_color: black
  slides: 
    - image: /uploads/slider/ganapathy-kumar-93498.jpg
      slide_html:
    - image: /uploads/slider/samuel-zeller-356272.jpg
      slide_html: "<h3>La Passione 1/2</h3>Shirley, do you own a Ferrari?"
    - image: /uploads/slider/samuel-zeller-356338.jpg
      slide_html: "<h3>La Passione 2/2</h3>Yes, my life is your dream."
    - image: /uploads/slider/ricardo-gomez-angel-180819.jpg
      slide_html:
```