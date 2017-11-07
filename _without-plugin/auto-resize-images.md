---
title: Auto-resize images
---

### Introduction

If you upload a huge image in CloudCannon (or any other Jekyll CMS), you would love it to be displayed small or cropped. This is super easy if you use an image resize proxy, like [images.weserv.nl](https://images.weserv.nl/). 

### How it works

Just create an image tag in your layout file that looks like this:

```
{% raw %}<img src="http://images.weserv.nl/?url=www.yourdomain.com{{ page.image }}&w=200&h=200&output=jpg&q=65" />{% endraw %}
```

More info about this service can be found at [images.weserv.nl](https://images.weserv.nl/).