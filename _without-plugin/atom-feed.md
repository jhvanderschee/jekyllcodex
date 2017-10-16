---
title: Atom feed
---

### Introduction

The name Atom applies to a pair of related Web standards. The Atom Syndication Format is an XML language used for web feeds. On the World Wide Web, a web feed (or news feed) is a data format used for providing users with frequently updated content. Content distributors syndicate a web feed, thereby allowing users to subscribe a channel to it. Making a collection of web feeds accessible in one spot is known as aggregation, which is performed by a news aggregator. A web feed is also sometimes referred to as a syndicated feed. A typical scenario of web-feed use might involve the following: a content provider publishes a feed link on its site which end users can register with an aggregator program (also called a feed reader or a news reader) running on their own machines.

### How it works

If you want an atom feed, add the file [feed.xml](https://github.com/jnvsor/jekyll-dynamic-menu/blob/master/feed.xml) to the root of your project. This will create a XML feed with the 10 latest posts in it. To tell the browsers you have a RSS feed, add this line to the head of your HTML:

```
{% raw %}<link rel="alternate" type="application/rss+xml" href="{{ site.url }}/feed.xml">{% endraw %}
```

### Installation

Step 1. Download the file [feed.xml](https://github.com/jnvsor/jekyll-dynamic-menu/blob/master/feed.xml)
<br />Step 2. Save the file in the root of your Jekyll project
<br />Step 3. Add the following line to your head/the 'jekyll-head.html' include:

```
{% raw %}<link rel="alternate" type="application/rss+xml" href="{{ site.url }}/feed.xml">{% endraw %}
```