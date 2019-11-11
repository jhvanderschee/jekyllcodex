---
title: Cookie consent
---

### Introduction

To be compliant with the GDPR, you have to have user consent for all non-functional and third pary cookies and scripts. This script allows you to delay the loading of certain Javascript includes, until the user clicks on 'Approve' in a cookie banner.

### How it works

The code inserts a cookie banner at the bottom of the screen. When you click 'Approve' it creates a cookie that is valid for 31 days. Each page load the code checks for the existence of this cookie. If it exists (and the value is 'true'), the blocked scripts are loaded. The blocked scripts can be found in the includes in the code below. You can easily replace these includes with your own.

```
{% raw %}if(readCookie('cookie-notice-dismissed')=='true') {
    {% include ga.js %}
    {% include chatbutton.js %}
}{% endraw %}
```

### Installation

Step 1. Download the file [cookie-consent.html](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/_includes/cookie-consent.html)
<br />Step 2. Save the file in the '_includes' directory of your project
<br />Step 3. Make sure the bottom of your layout document looks like this:

```
{% raw %}...
{% include cookie-consent.html %}
</body>
</html>{% endraw %}
```