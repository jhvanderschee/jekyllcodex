---
title: Sitemap
---

### Introduction

A sitemap makes it easier for search engines to discover new content on a website. Sitemaps can be submitted to the search-engine (for Google, use Google Webmaster Tools).

### How it works

The 'sitemap.xml' file should reside in the root of your website and contain roughly the following code. When you add collections, you should not forget to add them to this sitemap.

[expand]

```
{% raw %}---
layout: null
---
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.sitemaps.org/schemas/sitemap/0.9 http://www.sitemaps.org/schemas/sitemap/0.9/sitemap.xsd" xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  {% for page in site.pages %}
  {% if page.url contains '.xml' %}{% else %}
      <url>
        <loc>{{ site.url }}{{ page.url }}</loc>
        <changefreq>monthly</changefreq>
        <priority>1.0</priority>
       </url>
  {% endif %}
  {% endfor %}
  {% for page in site.posts %}
      <url>
        <loc>{{ site.url }}{{ page.url | replace: 'index.html', '' }}</loc>
        <changefreq>monthly</changefreq>
        <priority>1.0</priority>
       </url>
  {% endfor %}
</urlset>{% endraw %}
```

[/expand]

### Installation

Step 1. Download the file [sitemap.xml](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/sitemap.xml)
<br />Step 2. Save the file in the root of your Jekyll project
<br />Step 3. Make sure the structure of your documents head looks like this:

```
{% raw %}<head>
...
<link rel="sitemap" type="application/xml" title="Sitemap" href="/sitemap.xml" />
</head>{% endraw %}
```