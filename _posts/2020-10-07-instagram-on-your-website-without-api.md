---
title: Instagram on your website without API
date: 2020-10-07 00:00:00 Z
---

I have created a [new version of the instagram include](/without-plugin/instagram) to show instagram images on your Jekyll website.

### Problem

My previous version was an [instafeed.js alternative](/blog/instafeed-js-alternative-for-instagram/). Instafeed.js used to work without API calls. The new version of instafeed.js, however, required running your own server to keep your API tokens fresh. I thought that was a bit cumbersome and found a relatively easy way to circumvent this, by letting Zapier do the heavy lifting. However, there were some downsides to this approach. When, a few months ago, Instagram started to change the URL's of the static images every few hours, this solution no longer worked (as I was storing only the URL's).

### Solution

Fortunately I found an alternative solution that is even easier. Just add the following line to your code and you will find your instagram images in a nice 5 by 2 grid. You can view an [example](/without-plugin/instagram). More information about this solution can be found on the [PPI Loader website](https://profilepageimages.usecue.com/).

```
{% raw %}{% include instagram.html username="jhvanderschee" %}{% endraw %}
```

Keep it simple!
