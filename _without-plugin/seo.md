---
title: SEO
---

### How it works

This code takes care of the following things in the head:

- title
- meta description
- shortcut icons
- canonical link
- open graph tags
- atom feed (optional)

The following code adds all these items to your head:

```
{% raw %}<head>
  <meta charset="utf-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1">

  <title>{% if page.title %}{{ page.title }}{% else %}{{ site.title }}{% endif %}</title>
  <meta name="description" content="{{ page.content | strip_html | strip_newlines | truncate: 160 }}">
  
  <link rel="shortcut icon" type="image/png" href="/img/icon-196x196.png">
  <link rel="shortcut icon" sizes="196x196" href="/img/icon-196x196.png">
  <link rel="apple-touch-icon" href="/img/icon-196x196.png">

  <link rel="stylesheet" href="{{ "/css/style.css" | prepend: site.baseurl }}">
  <link rel="canonical" href="{{ page.url | replace:'index.html','' | prepend: site.baseurl | prepend: site.url }}">
  <link rel="alternate" type="application/rss+xml" title="{{ site.title }}" href="{{ "/feed.xml" | prepend: site.baseurl | prepend: site.url }}">
  
  {% include ga.html %}
</head>{% endraw %}
```

Note: Ofcourse you can also set manual page descriptions, using 'page.description' and a matching YML variable in your page. 

### Installation

Step 1. Download the file [jekyll-head.html](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/_includes/reading-time.html)
<br />Step 2. Save the file in the '_includes' directory of your project
<br />Step 3. Make sure the structure of your layout document looks like this:

```
{% raw %}<!DOCTYPE html>
<html>
{% include jekyll-head.html %}
<body>
...
</body>
</html>{% endraw %}
```

