---
title: "Slider"
slider:
  text_color: white
  shadow_color: black 
  image_width: 1000
  image_height: 500
  slides: 
    - image: /uploads/slider/ganapathy-kumar-93498.jpg
      slide_html:
    - image: /uploads/slider/samuel-zeller-356272.jpg
      slide_html: "<h3>La Passione 1/2</h3>Shirley, do you own a Ferrari?"
    - image: /uploads/slider/samuel-zeller-356338.jpg
      slide_html: "<h3>La Passione 2/2</h3>Yes, my life is your dream."
    - image: /uploads/slider/ricardo-gomez-angel-180819.jpg
      slide_html:
---

### Introduction

Embedding a slider in your layout is a much requested feature. Twitter Bootstrap is often used for creating layouts and allows yout to add a slider relatively effortless. The code below simplifies things even more and makes the slider configurable and editable. 

### How it works

This slider replaces the default icons for big HTML arrows and uses background images to make sure the slider maintains the same height. The code allows you to set the height of the slider as an integer (number), and the unit in as '%' or 'px'. You can define if you want the transition to be a 'slide' or a 'fade'. And finally how long each slide should stay on the screen (in seconds).

{% include slider.html height="50" unit="%" transition="slide" duration="7" %}

### Installation

Step 1. Download the file [slider.html](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/_includes/slider.html)
<br />Step 2. Save the file in the '_includes' directory of your project
<br />Step 3. Make sure you load the Bootstrap CSS in your head and jQuery and Bootstrap JS in your [footer.html](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/_includes/footer.html).
<br />Step 4. Add the following statement to your layout where you want the slider to appear:

```
{% raw %}{% if page.slider %}
  {% include slider.html height="50" unit="%" transition="slide" duration="7" %}
{% endif %}{% endraw %}
```
Step 5. Add the following YML to the head of your Markdown file:

```
slider:
  text_color: white
  shadow_color: black 
  image_width: 1000
  image_height: 500
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