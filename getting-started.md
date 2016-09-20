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

Now you create an 'index.md' file and you replace your PHP tags with Liquid tags, like so:

<pre>---
---
&lt;html&gt;
&lt;head&gt;&lt;/head&gt;
&lt;body&gt;
&lcub;% include header.html %&rcub;
content
&lcub;% include sidebar.html %&rcub;
&lcub;% include footer.html %&rcub;
&lt;/body&gt;
&lt;/html&gt;</pre>

You need to place the html files you want to include in a folder in the root named: '_includes'. [Get the code.](https://github.com/jhvanderschee/jekyllinclude)

## Step 2. Preview your website

Opening the 'index.md' file in your browser does not work, so you need to upload it to a Jekyll environment. You can install Jekyll through command-line on your own machine. If this is your cup of tea, please go to [jekyllrb.com](http://jekyllrb.com/). Otherwise, follow these simple instructions:

- Create a free account at [cloudcannon.com](http://cloudcannon.com)
- Create a website and name it
- Create an empty '_config.yml' file in the root
- Upload your 'default.html' file and the '_layouts' directory
- Upload the needed includes to the '_includes' directory
- Upload your 'index.md' file to the root directory
- Visit your website on the URL CloudCannon created for you

## Step 3. Host your website

Oh, how I hate shared hosting accounts... untill Jekyll. Shared hosting accounts are cheap but unreliable. However, Jekyll provides us with a back-up (actually the source code), which makes me feel a whole lot safer. CloudCannon exports the static version of your site to an FTP account on every update, enabling you to use the hosting environment of your choice. Just connect your FTP account through the CloudCannon options.
