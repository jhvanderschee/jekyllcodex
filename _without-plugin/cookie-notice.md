---
title: "Cookie notice"
---

### Introduction

To be compliant with the GDPR, you have to have user consent for all non-functional and third pary cookies and scripts. This must be explicit, so scrolling a website is no longer compliant. To help you this script allows you to delay the loading of Javascript, until the user approves these cookies and scripts.

### How it works

Just put the scripts you want to block in a Javascript include.

```
{% raw %}if(readCookie('cookie-notice-dismissed')=='true') {
    {% include ga.js %}
    {% include chatbutton.js %}
}{% raw %}
```

### Installation

Step 1. Download the file [cookie-notice.html](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/_includes/cookie-notice.html)
<br />Step 2. Save the file in the '_includes' directory of your project
<br />Step 3. Make sure the bottom of your layout document looks like this:

```
{% raw %}...
<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.3/jquery.min.js"></script>
{% include cookie-notice.html %}
</body>
</html>{% endraw %}
```