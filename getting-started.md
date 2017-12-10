---
title: Getting started
---


## Step 1. Create a basic website

A website typically consists of a few elements. The header with a menu, a sidebar, the content and the footer. Back in the days we used frames to put these components together. Nowadays we use includes. These includes require a programming language to work, like PHP. Using PHP however introduces a lot of vulnerabilities. What if we could prevent that by design? Well... you can with Jekyll.

You used to create an 'index.php' file and do something like this:

```
<html>
<head></head>
<body>
<?php include('header.php'); ?>
content
<?php include('sidebar.php'); ?>
<?php include('footer.php'); ?>
</body>
</html>
```

Now you create an 'index.md' file and you replace your PHP tags with Liquid tags, like so:

```
{% raw %}---
---
<html>
<head></head>
<body>
{% include header.html %}
content
{% include sidebar.html %}
{% include footer.html %}
</body>
</html>{% endraw %}
```

You need to place html files you want to include in a root folder named: '_includes'. [Get the code &rarr;](https://github.com/jhvanderschee/jekyllinclude)

## Step 2. Preview your website

Opening the 'index.md' file in your browser does not work, so you need to have an enivronment that runs Jekyll. You can install Jekyll through command-line on your own machine. If this is your cup of tea, please go to [jekyllrb.com](http://jekyllrb.com/). Otherwise, follow these simple instructions:

* Create a free account at [cloudcannon.com](http://cloudcannon.com)
* Create a website and name it
* Create an empty '_config.yml' file in the root
* Upload your 'default.html' file and the '_layouts' directory
* Upload the needed includes to the '_includes' directory
* Upload your 'index.md' file to the root directory
* Visit your website on the URL CloudCannon created for you

## Step 3. Host your website

Oh, how I hate shared hosting accounts... untill Jekyll. Shared hosting accounts are cheap but unreliable. However, a Git based static site provides us with a back-up (actually the source code), which makes me feel a whole lot safer. CloudCannon exports the static version of your site to an FTP account on every update, enabling you to use an hosting environment of your choice. Just connect your FTP account through the CloudCannon options. So if your cheap hosting account goes down, the source code will still live on in Git and in your CloudCannon environment, enabling you to push the site to another cheap hosting account. Isn't that reassuring?