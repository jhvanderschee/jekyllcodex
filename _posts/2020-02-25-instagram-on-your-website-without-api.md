---
title: Instagram on your website without API
date: 2020-02-25 00:00:00 Z
---

I wanted to find an [alternative to instafeed.js](/blog/instafeed-js-alternative-for-instagram/), which used to work without API calls. I found a relatively easy way to circumvent running your own server to keep your API tokens fresh. The solution was to let Zapier do the heavy lifting. However, there were some downsides to this approach. When a few months ago the URL's of the static images started to change every few hours, this solution no longer worked (as I was storing only links to these images and not the images themselves).

### Solution

Fortunately I found an alternative solution. It is EXTREMELY simple to use. Just add the following line to your code and you will find your instagram images in a nice 5 by 2 grid. You can view an [example here](/without-plugin/instagram).

```
{% raw %}{% include instagram.html username="jhvanderschee" %}{% endraw %}
```

Enjoy! Keep it simple!