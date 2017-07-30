---
title: Basics
layout: page
permalink: /basics/
---


## Layout

### Templates

If you need templates, you can create them in the directory ‘_layouts’. Your template is alsmost the same as your ‘index.md’ file, you created in the ‘Getting started’. The only difference is that you should name it ‘templatename.html’, remove the dotted lines at the start, and replace the word content with:

```
{% raw %}{{ content }}{% endraw %}
```

Furthermore you should change your ‘index.md’ file to this:

```
{% raw %}---
layout: templatename
---

content{% endraw %}
```

### Using Sass

Jekyll supports Sass out of the box. This means you can use ‘style.scss’ anywhere in your project and refer to it as ‘style.css’. You will have no excuse for using CSS anymore. Want to compress the outputted CSS? Just add the following two lines to your ‘_config.yml’ file.

```
{% raw %}sass:
  style: compressed{% endraw %}
```

## Blogging

### Setup

Go to your ‘Collections’ in CloudCannon and see if you already have support for posts. If not, create a ‘_posts’ directory in the root of your project and look again. Listing your blog items requires the following Liquid code:

```
{% raw %}<h3>Posts</h3>
<ul>
  {% for post in site.posts %}
  <li>
    <a href="{{ post.url }}">{{ post.title }}</a>
  </li>
  {% endfor %}
</ul>{% endraw %}
```

### Custom permalinks

To change the permalinks of your blog articles, simply add this single line to your ‘_config.yml’:

```
{% raw %}permalink: /blog/:year/:month/:day/:title/{% endraw %}
```

### Reading time

To display the reading time of an article, just use the following code:

```
{% raw %}{% capture words %}
{{ content | number_of_words | minus: 180 }}
{% endcapture %}
{% unless words contains '-' %}
{{ words | plus: 180 | divided_by: 180 | append: ' minutes to read' }}
{% endunless %}{% endraw %}
```

## SEO

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

## Menu’s

### Set active class

Setting the active class on a li that contains a link to the current page URL goes like this:

```
{% raw %}<li {% if page.url == '/getting-started/' %}class="active"{% endif %}> ... </li>{% endraw %}
```

Or if you want to check that the first part of the URL equals the menu item:

```
{% raw %}{% assign url_parts = page.url | split: '/' %}
<li {% if url_parts[1] == 'getting-started' %}class="active"{% endif %}> ... </li>{% endraw %}
```

Or you can use the more generic but shorter:

```
{% raw %}<li {% if page.url contains 'getting-started' %}class="active"{% endif %}> ... </li>{% endraw %}
```

### Dynamic menu

Creating a menu that automagically discovers and adds new pages is also possible with plain Liquid. More info and a demo can be found [here](https://github.com/jnvsor/jekyll-dynamic-menu). When you put the two files (‘menulevel’ and ‘menushow’) in your ‘_includes’ folder you can generate a dynamic menu with the following command:

```
{% raw %}{% include menulevel.html url='' %}{% endraw %}
```

## Images

### Gallery

Listing the jpg files in the current directory in Jekyll can be done like this:

```
{% raw %}{% for file in site.static_files %}
  {% assign pageurl = page.url | replace: 'index.html', '' %}
  {% if file.path contains pageurl %}
    {% if file.extname == '.jpg' or file.extname == '.jpeg' or file.extname == '.JPG' or file.extname == '.JPEG' %}
      <img src="{{ file.path }}" />
    {% endif %}
  {% endif %}
{% endfor %}{% endraw %}
```

### Auto-resize images

If you upload a huge image in CloudCannon, you would love it to be displayed small or cropped. This is super easy if you use https://images.weserv.nl/. Just create a image tag like this:

```
{% raw %}<img src="http://images.weserv.nl/?url=www.yourdomain.com{{ page.image }}&w=200&q=65" />{% endraw %}
```

More info about this service can be found at images.weserv.nl.

## Need more?

Look at the add-ons for more solutions.