---
title: Basics
layout: page
permalink: /basics/
---

## Layout

### Different templates

If you need different templates, for posts and pages for example, you can create them in the directory ‘_layouts’. Your template is alsmost the same as your ‘index.html’ file, you created in the ‘Getting started’. The only difference is that you should name it something like ‘page.html’ and replace the content with:

~~~
{{ content }}
~~~

Furthermore you have to add three extra lines at the top of your ‘index.html’ file.

~~~
---
layout: page
---
~~~

### Using Sass

Jekyll supports Sass out of the box. This means you can use ‘style.scss’ anywhere in your project and refer to it as ‘style.css’. You will have no excuse for using CSS anymore. Want to compress the outputted CSS? Just add the following two lines to your ‘_config.yml’ file.

~~~
sass:
  style: compressed
~~~

## Blogging

### Setup

Go to your ‘Collections’ in CloudCannon and see if you already have support for posts. If not, create a ‘_posts’ directory in the root of your project and look again. Listing your blog items requires the following Liquid code:

~~~
<h3>Posts</h3>
<ul>
  {% for post in site.posts %}
  <li>
    <a href="{{ post.url }}">{{ post.title }}</a>
  </li>
  {% endfor %}
</ul>
~~~

### Custom permalinks

To change the permalinks of your blog articles, simply add this single line to your ‘_config.yml’:

~~~
permalink: /blog/:year/:month/:day/:title/
~~~

## SEO

### Pretty URL’s

When you want your URL’s to be pretty, simply use the ‘old-school’ approach. Create an ‘index.html’ in the root for the homepage and a folder called ‘about’ with another ‘index.html’ file inside for your ‘about’ page… and so on. The Jekyll way is to add the permalink to the top of your document, like this:

~~~
---
permalink: /your/complex/permalink/
---
~~~

### Description tag

If you want to manually add a page description, simply add the following line to the head of your HTML:

~~~
{% if page.description %}<meta name="description" content="{{ page.description }}" />{% endif %}
~~~

Add the following lines to the top of your document if you require a manual description. Updating them is a piece of cake in CloudCannon.

~~~
---
description: my-description
---
~~~

### Canonical link

Making sure Google indexes the right page (and not the url with ‘index.html’), simply add the following line to the head of your HTML:

~~~
<link rel="canonical" href="{{ page.url | replace: &amp;amp;quot;index.html&amp;amp;quot;,&amp;amp;quot;&amp;amp;quot; | prepend: &amp;amp;quot;http://yourdomainname.com&amp;amp;quot; }}">
~~~

### Sitemap XML

Creating a sitemap for a page that is hosted on GitHub pages is [easy](https://help.github.com/articles/sitemaps-for-github-pages/). If you do not want to use a plugin, just place [this](https://github.com/CloudCannon/Jekyll-Tips/blob/master/sitemap.xml) code in a file called ‘sitemap.xml’ in the root of your website. Do not forget to submit your sitemap to Google (or any other search engine).

### Atom feed

Add the file [feed.xml](https://github.com/jnvsor/jekyll-dynamic-menu/blob/master/feed.xml) to the root of your project. This will create a XML feed with the 10 latest posts in it. To tell the browsers you have a RSS feed, add this line to the head of your HTML:

~~~
<link rel="alternate" type="application/rss+xml" title="Your sites title" href="http://yourdomainname.com/feed.xml">
~~~

## Menu’s

### Set active class

Setting the active class on a li that contains a link to the current page URL goes like this:

~~~
<li {% if &amp;amp;amp;amp;#39;/getting-started/&amp;amp;amp;amp;#39; == page.url %}class="active"{% endif %}> ... </li>
~~~

Or if you want to check that the first part of the URL equals the menu item:

~~~
{% assign url_parts = page.url | split:&amp;amp;amp;amp;#39;/&amp;amp;amp;amp;#39; %}
<li {% if &amp;amp;amp;amp;#39;getting-started&amp;amp;amp;amp;#39; == url_parts[1] %}class="active"{% endif %}> ... </li>
~~~

### Dynamic menu

Creating a menu that automagically discovers and adds new pages is also possible with plain Liquid. More info and a demo can be found [here](https://github.com/jnvsor/jekyll-dynamic-menu). When you put the two files (‘menulevel’ and ‘menushow’) in your ‘_includes’ folder you can generate a dynamic menu with the following command:

~~~
{% include menulevel url=&#39;/subdir/&#39; %}
~~~

## Need more?

Look at the add-ons for more solutions.