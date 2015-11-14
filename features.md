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

To support blogging you need a '_posts' directory in the root of your project. 

## Extra features


### Pretty URL's

When you want your URL's to be pretty, simply use the 'old-school' approach. Create an 'index.html' in the root for the homepage and a folder called 'about' with another 'index.html' file inside for your 'about' page... and so on. You will take advantage of this on a later moment when you need to build a menu, based on the page hierarchy.

### Menu/Page hierarchy

...

### Contact forms

...

### Search

...

### Responsive images

https://www.netlify.com/blog/2015/08/20/simple-responsive-images-with-jekyll

### Minify everything

...