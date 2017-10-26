---
title: Atom/RSS feed
---

### Introduction

The Atom Syndication Format is an XML language used for web feeds. A web feed (also called 'news feed' or 'RSS feed') is a data format used for providing users with frequently updated content. Content distributors syndicate a web feed, thereby allowing users to subscribe a channel to it. A typical scenario of web-feed use might involve the following: a content provider publishes a feed link on its site which end users can register with an aggregator program (also called a feed reader or a news reader) running on their own machines.

### How it works

The atom feed, in the 'feed.xml' file uses Liquid to build the XML. The file contains the following code.

[expand]

```
{% raw %}---
layout: null
---
<?xml version="1.0" encoding="UTF-8"?>
<rss version="2.0" xmlns:atom="http://www.w3.org/2005/Atom">
  <channel>
    <title>{{ site.title | xml_escape }}</title>
    <description>{{ site.description | xml_escape }}</description>
    <link>{{ site.url }}{{ site.baseurl }}/</link>
    <atom:link href="{{ "/feed.xml" | prepend: site.baseurl | prepend: site.url }}" rel="self" type="application/rss+xml"/>
    <pubDate>{{ site.time | date_to_rfc822 }}</pubDate>
    <lastBuildDate>{{ site.time | date_to_rfc822 }}</lastBuildDate>
    <generator>Jekyll v{{ jekyll.version }}</generator>
    {% for post in site.posts limit:10 %}
      <item>
        <title>{{ post.title | xml_escape }}</title>
        <description>{{ post.content | xml_escape }}</description>
        <pubDate>{{ post.date | date_to_rfc822 }}</pubDate>
        <link>{{ post.url | prepend: site.baseurl | prepend: site.url }}</link>
        <guid isPermaLink="true">{{ post.url | prepend: site.baseurl | prepend: site.url }}</guid>
        {% for tag in post.tags %}
        <category>{{ tag | xml_escape }}</category>
        {% endfor %}
        {% for cat in post.categories %}
        <category>{{ cat | xml_escape }}</category>
        {% endfor %}
      </item>
    {% endfor %}
  </channel>
</rss>{% endraw %}
```

The code above will create a XML feed with the 10 latest posts in it. To tell the browsers you have a web feed, add a simple line to the head of your HTML:

```
{% raw %}<link rel="alternate" type="application/rss+xml" href="{{ site.url }}/feed.xml">{% endraw %}
```

[/expand]

### Installation

Step 1. Download the file [feed.xml](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/feed.xml)
<br />Step 2. Save the file in the root of your Jekyll project
<br />Step 3. Add the following line to your head/the 'head.html' include:

```
{% raw %}<link rel="alternate" type="application/rss+xml" href="{{ site.url }}/feed.xml">{% endraw %}
```