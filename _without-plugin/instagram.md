---
title: Instagram
---

### Introduction

This script creates an instagram feed of a user. The script reads all images from your instagram account, downloads the largest size (612x612) and shows the last five.

{% include instagram.html clientId="ed7b5036b29a48d482376be6c3413d24" userId="260010543" accessToken="260010543.ed7b503.9571dca5a7cb4914b866004d67c96ef0" %}

### How it works

This script loads instafeed.js and requires three variables: [userId](https://www.otzberg.net/iguserid/), [clientId](https://www.instagram.com/developer/) and [accessToken](https://www.instagram.com/developer/authentication/). To obtain a clientId you need to register your website as an Instagram application. This will give you a clientId. Next you need to follow a three step process to obtain the accessToken.

### Installation

Step 1. Download the file [instagram.html](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/_includes/instagram.html)
<br />Step 2. Save the file in the '_includes' directory of your project
<br />Step 3. Add the following line to your layout on the place where you want the share buttons to appear:

```
{% raw %}{% include instagram.html clientId="ed7b5036b29a48d482376be6c3413d24" userId="260010543" accessToken="260010543.ed7b503.9571dca5a7cb4914b866004d67c96ef0" %}{% endraw %}
```