---
title: Metrics
---

### Introduction

Google Analytics is a freemium web analytics service offered by Google that tracks and reports website traffic. Google launched the service in November 2005. Google Analytics is the most widely used web analytics service on the Internet.

### How it works

A javascript is added to your footer to instruct Google to track the page load. Additionally SSL is forced during this tracking and the IP address is anonymized, making this the most decent use of Google Analytics possible. However, using server side metrics is faster, more responsible and maybe even more reliable.

[expand]

```
{% raw %}<script type="text/javascript">
  var _gaq = _gaq || [];
  _gaq.push(['_setAccount', 'UA-xxxxxxxx-1']);
  _gaq.push(['_gat._forceSSL']);
  _gaq.push(['_gat._anonymizeIp']);
  _gaq.push(['_trackPageview']);

  (function() {
    var ga = document.createElement('script'); ga.type = 'text/javascript'; ga.async = true;
    ga.src = ('https:' == document.location.protocol ? 'https://ssl' : 'http://www') + '.google-analytics.com/ga.js';
    var s = document.getElementsByTagName('script')[0]; s.parentNode.insertBefore(ga, s);
  })();
</script>{% endraw %}
```

[/expand]

### Installation

Step 1. Download the file [analytics.html](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/_includes/analytics.html)
<br />Step 2. Save the file in the '_includes' directory of your project
<br />Step 3. Change the property code (UA-xxxxxxxx-1) to your code
<br />Step 4. Make sure the bottom of your layout document looks like this:

```
{% raw %}...
{% include analytics.html %}
</body>
</html>{% endraw %}
```