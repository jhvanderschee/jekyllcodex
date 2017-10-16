---
title: SEO
---

### How it works

Ofcourse you want your URL’s/permalinks to be pretty. To ensure this, simply use the ‘old-school’ approach. Create an ‘index.html’ in the root for the homepage and a folder called ‘about’ with another ‘index.html’ file inside for your ‘about’ page... and so on. The Jekyll way is to add the permalink to the top of your document, like this:

```
{% raw %}---
permalink: /your/complex/permalink/
---{% endraw %}
```
Note that both options will work equally good. 

Additionally you want your page to have a decent page description. Therefore you need to add the following line to the head of your HTML:

```
{% raw %}{% if page.description %}<meta name="description" content="{{ page.content | strip_html | truncate:160 }}" />{% endif %}{% endraw %}
```

The description is automatically generated from the page content. Ofcourse you can also set manual page descriptions, using 'page.description' and a matching YML variable in your page.

To make sure Google indexes the right page, simply add the following line to the head of your HTML:

```
{% raw %}<link rel="canonical" href="{{ page.url | replace:'index.html','' | prepend: 'http://yourdomainname.com' }}">{% endraw %}
```

Social tags...

Finally SEO plugins often create a sitemap. [This](https://github.com/CloudCannon/Jekyll-Tips/blob/master/sitemap.xml) code in a file called ‘sitemap.xml’ in the root of your website will do that for you. Do not forget to submit your sitemap to Google (or any other search engine).

Finally you want an atom feed. Add the file [feed.xml](https://github.com/jnvsor/jekyll-dynamic-menu/blob/master/feed.xml) to the root of your project. This will create a XML feed with the 10 latest posts in it. To tell the browsers you have a RSS feed, add this line to the head of your HTML:

```
{% raw %}<link rel="alternate" type="application/rss+xml" title="Your sites title" href="http://yourdomainname.com/feed.xml">{% endraw %}
```

### Installation

