---
title: Features
layout: page
permalink: /features/
---

## Layout

### Different templates

If you need different templates, for posts and pages for example, you can create them in the directory '_layouts'. Your template is alsmost the same as your 'index.html' file, you created in the 'Getting started'. The only difference is that you should name it something like 'post.html', 'page.html' or 'default.html' and replace the content with: 

<pre>&lcub;&lcub; content &rcub;&rcub;</pre>

Furthermore you have to add three extra lines at the top of your 'index.html' file.

<pre>---<br />layout: page<br />---</pre>

### Using Sass

Jekyll supports Sass out of the box. This means you can use 'style.scss' anywhere in your project and refer to it as 'style.css'. You will have no excuse for using CSS anymore. Want to compress the outputted CSS? Just add the following two lines to your '_config.yml' file.

<pre>sass:<br />&nbsp;&nbsp;style: compressed</pre>

## Blogging

### Setup

Go to your 'Collections' in CloudCannon and see if you already have support for posts. If not, create a '_posts' directory in the root of your project and look again. Blogs have a default URL like this: YYYY/MM/DD/title-of-the-blog.html. Listing your blog items requires the following Liquid code:

<pre>&lt;h3&gt;Posts&lt;/h3&gt;
&lt;ul&gt;
  &lcub;% for post in site.posts %&rcub;
  &lt;li&gt;
    &lt;a href="&lcub;&lcub; post.url &rcub;&rcub;">&lcub;&lcub; post.title &rcub;&rcub;&lt;/a&gt;
  &lt;/li&gt;
  &lcub;% endfor %&rcub;
&lt;/ul&gt;</pre>

## Extra features


### Pretty URL's

When you want your URL's to be pretty, simply use the 'old-school' approach. Create an 'index.html' in the root for the homepage and a folder called 'about' with another 'index.html' file inside for your 'about' page... and so on. You will take advantage of this on a later moment when you need to build a menu, based on the page hierarchy.

### Menu/Page hierarchy

List children is relatively simple, like this:

<pre>&lcub;% assign url_parts = page.url | split: '/' %&rcub;
&lcub;% assign url_parts_size = url_parts | size %&rcub;
&lcub;% assign rm = url_parts | last %&rcub;
&lcub;% assign base_url = page.url | replace: rm %&rcub;

&lt;ul&gt;
    &lcub;% for node in site.pages %&rcub;
      &lcub;% if node.url contains base_url %&rcub;
        &lcub;% assign node_url_parts = node.url | split: '/' %&rcub;
        &lcub;% assign node_url_parts_size = node_url_parts | size %&rcub;
        &lcub;% assign filename = node_url_parts | last %&rcub;
        &lcub;% if url_parts_size == node_url_parts_size and filename != 'index.html' %&rcub;
          &lt;li&gt;&lt;a href='&lcub;&lcub;node.url&rcub;&rcub;'>&lcub;&lcub;node.title&rcub;&rcub;&lt;/a&gt;&lt;/li&gt;
        &lcub;% endif %&rcub;
      &lcub;% endif %&rcub;
    &lcub;% endfor %&rcub;
&lt;/ul&gt;</pre>

### Need more?

Look at the add-ons for other solutions. 