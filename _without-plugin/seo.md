---
title: SEO
---

### Pretty URL’s

When you want your URL’s to be pretty, simply use the ‘old-school’ approach. Create an ‘index.html’ in the root for the homepage and a folder called ‘about’ with another ‘index.html’ file inside for your ‘about’ page… and so on. The Jekyll way is to add the permalink to the top of your document, like this:

```
{% raw %}---
permalink: /your/complex/permalink/
---{% endraw %}
```

### Description tag

If you want to manually add a page description, simply add the following line to the head of your HTML:

```
{% raw %}{% if page.description %}<meta name="description" content="{{ page.description }}" />{% endif %}{% endraw %}
```

Add the following lines to the top of your document if you require a manual description. Updating them is a piece of cake in CloudCannon.

```
{% raw %}---
description: my-description
---{% endraw %}
```

### Canonical link

Making sure Google indexes the right page (and not the url with ‘index.html’), simply add the following line to the head of your HTML:

```
{% raw %}<link rel="canonical" href="{{ page.url | replace:'index.html','' | prepend: 'http://yourdomainname.com' }}">{% endraw %}
```

### Sitemap XML

Creating a sitemap for a page that is hosted on GitHub pages is [easy](https://help.github.com/articles/sitemaps-for-github-pages/). If you do not want to use a plugin, just place [this](https://github.com/CloudCannon/Jekyll-Tips/blob/master/sitemap.xml) code in a file called ‘sitemap.xml’ in the root of your website. Do not forget to submit your sitemap to Google (or any other search engine).

### Atom feed

Add the file [feed.xml](https://github.com/jnvsor/jekyll-dynamic-menu/blob/master/feed.xml) to the root of your project. This will create a XML feed with the 10 latest posts in it. To tell the browsers you have a RSS feed, add this line to the head of your HTML:

```
{% raw %}<link rel="alternate" type="application/rss+xml" title="Your sites title" href="http://yourdomainname.com/feed.xml">{% endraw %}
```