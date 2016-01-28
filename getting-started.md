---
title: Getting started
layout: page
permalink: /getting-started/
---

## Step 1. Create a basic website

A website typically consists of a few elements. The header with a menu, a sidebar, the content and the footer. Back in the days we used frames to put these components together. Nowadays we use includes. These includes require a programming language to work, like PHP. Using PHP however introduces a lot of vulnerabilities. Not the best idea for a front-end dev without a clue, like you.

You used to create an 'index.php' file and do something like this:

<pre>&lt;html&gt;
&lt;head&gt;&lt;/head&gt;
&lt;body&gt;
&lt;?php include('header.php'); ?&gt;
content
&lt;?php include('sidebar.php'); ?&gt;
&lt;?php include('footer.php'); ?&gt;
&lt;/body&gt;
&lt;/html&gt;</pre>

Now you create an 'index.html' file and you replace your PHP tags with Liquid tags, like so:

<pre>&lt;html&gt;
&lt;head&gt;&lt;/head&gt;
&lt;body&gt;
&lcub;% include header.html %&rcub;
content
&lcub;% include sidebar.html %&rcub;
&lcub;% include footer.html %&rcub;
&lt;/body&gt;
&lt;/html&gt;</pre>

And one extra thing: you need to place the files you want to include in a folder in the root named: '_includes'. Otherwise it does not work.

## Step 2. Preview your website

Opening the 'index.html' file in your browser does not work, so you need to upload it to a Jekyll environment. You can install Jekyll through command-line on your own machine. If this is your cup of tea, please go to [jekyllrb.com](http://jekyllrb.com/). Otherwise, follow these simple instructions:

- Create a free account at [cloudcannon.com](http://cloudcannon.com)
- Create a website and name it
- Create an empty '_config.yml' file in the root
- Upload your 'index.html' file and the '_includes' directory
- Visit your website on the URL CloudCannon created for you

## Step 3. Add a CMS to your website

Adding a CMS is very simple in CloudCannon. Just open your 'index.html' file and replace:

<pre>content</pre>

with:

<pre>&lt;div class="editable"&gt;content&lt;/div&gt;</pre>

Resulting in:

<pre>&lt;html&gt;
&lt;head&gt;&lt;/head&gt;
&lt;body&gt;
&lcub;% include 'header.html' %&rcub;
&lt;div class="editable"&gt;content&lt;/div&gt;
&lcub;% include 'sidebar.html' %&rcub;
&lcub;% include 'footer.html' %&rcub;
&lt;/body&gt;
&lt;/html&gt;</pre>

Your website now has a WYSIWYG editor in CloudCannon for easy content manipulation. 

## Step 4. Host your website

Oh, how I hate shared hosting accounts... untill Jekyll. Shared hosting accounts are cheap but unreliable. However, Jekyll provides us with a back-up (actually the source code), which makes me feel a whole lot safer. CloudCannon exports the static version of your site to an FTP account on every update, enabling you to use the hosting environment of your choice. Just connect your FTP account through the CloudCannon options.
