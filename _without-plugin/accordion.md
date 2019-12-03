---
title: Accordion
accordion: 
  - title: this is item 1
    content: Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce et lorem elit. Nam scelerisque leo ut consequat congue. Donec libero magna, sagittis eu tellus non, tristique varius tortor. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Nunc ultrices libero tellus, vel mattis ex faucibus in. Pellentesque aliquet finibus urna a rutrum. Ut vitae nibh iaculis justo ultricies tristique. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Pellentesque mattis, nibh vitae ultrices dignissim, leo justo sollicitudin lorem, sit amet tincidunt risus odio nec augue. Quisque placerat nibh eget velit scelerisque pellentesque. Etiam auctor vel leo eget pulvinar. Donec sodales nulla elit, non eleifend justo convallis vitae. Aliquam erat volutpat. Etiam ac rhoncus tortor. Ut sodales egestas nisl.
  - title: this is item 2
    content: >-
      Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce et lorem elit. Nam scelerisque leo ut consequat congue. Donec libero magna, sagittis eu tellus non, tristique varius tortor. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Nunc ultrices libero tellus, vel mattis ex faucibus in. Pellentesque aliquet finibus urna a rutrum. Ut vitae nibh iaculis justo ultricies tristique. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Pellentesque mattis, nibh vitae ultrices dignissim, leo justo sollicitudin lorem, sit amet tincidunt risus odio nec augue. Quisque placerat nibh eget velit scelerisque pellentesque. Etiam auctor vel leo eget pulvinar. Donec sodales nulla elit, non eleifend justo convallis vitae. Aliquam erat volutpat. Etiam ac rhoncus tortor. Ut [sodales](#) egestas nisl.
---

### Introduction

Sometimes you have a lot of information you want to disclose gradually. This is often the case with Frequently Asked Questions. An accordion is a perfect solution for this. Clicking on the title of the accordion expands the content area. This looks like this:

{% include accordion.html %}

### How it works

To create an accordion, add the following code to the front matter of your page:

```
{% raw %}---
accordion: 
  - title: this is item 1
    content: Lorem ipsum dolor sit amet, consectetur adipiscing elit. 
  - title: this is item 2
    content: Lorem ipsum dolor sit amet, consectetur adipiscing elit.
---{% endraw %}
```

The code uses no javascript and uses the CSS checkbox 'hack' to toggle the content. The accordion deliberately refrains from setting the height of the content blocks. Calculating this height with javascript is required to add animatio (slide down), but adds a lot of complexity. If you want to animate this accordion nevertheless, I would suggest to calculate the height during the 'onclick' and remove the height directly after the animation process. Calculating the height during the 'window.resize' seems more logical, but will slow down your website. Although I like animated accordions, I think that this CSS-only solution is more elegant. The code of the example above can be found here.

[expand]


```
{% raw %}{% include accordion.html %}{% endraw %}
```

[/expand]

### Installation

Step 1. Download the file [accordion.html](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/_includes/accordion.html)
<br />Step 2. Save the file in the '_includes' directory of your project
<br />Step 3. Make sure your front matter of your page looks like the example above
<br />Step 4. Add the following line to your layout on the place where you want the form to appear:

```
{% raw %}{% include accordion.html %}{% endraw %}
```