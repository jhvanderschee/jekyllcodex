---
title: New window fix
---

### Introduction

One of the irritating things about Markdown is that you [cannot](https://stackoverflow.com/questions/4425198/can-i-create-links-with-target-blank-in-markdown) specify 'target="_blank"' in your links. This script fixes that, by automatically adding these targets to external links and PDF links.

### How it works

The following code should be added to the footer:

```
{% include new-window-fix.html %}
```

### Installation

Step 1. Download the file [new-window-fix.html](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/_includes/new-window-fix.html)
<br />Step 2. Save the file in the '_includes' directory of your project
<br />Step 3. Make sure the bottom of your layout document looks like this:

```
{% raw %}...
{% include new-window-fix.html %}
</body>
</html>{% endraw %}
```