---
title: Instagram on your website without API
date: 2020-02-25 00:00:00 Z
---

I have created a [new version of the instagram include](/without-plugin/instagram) to show instagram images on your Jekyll website.

### Problem

My previous version was an [instafeed.js alternative](/blog/instafeed-js-alternative-for-instagram/), which used to work without API calls. The new version of instafeed required running your own server to keep your API tokens fresh. I found a  relatively easy way to circumvent this, by letting Zapier do the heavy lifting. However, there were some downsides to this approach. When, a few months ago, Instagram started to change the URL's of the static images every few hours, this solution no longer worked.

### Solution

Fortunately I found an alternative solution that is even easier. Just add the following line to your code and you will find your instagram images in a nice 5 by 2 grid. You can view an [example here](/without-plugin/instagram). I am not going into too many detail on how and why this works... but enjoy it!

```
{% raw %}{% include instagram.html username="jhvanderschee" %}{% endraw %}
```

Keep it simple!