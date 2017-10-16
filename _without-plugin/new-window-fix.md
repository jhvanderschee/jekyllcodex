---
title: New window fix
---

### Introduction

One of the irritating things about Markdown is that you cannot specify 'target="_blank"' in your links. This script fixes that, by automatically adding these targets to external links and PDF links.

### How it works

The following code should be added to the footer:

```
{% raw %}<script>
//open external links in a new window
function externalLinks() {
  for(var c = document.getElementsByTagName("a"), a = 0;a < c.length;a++) {
    var b = c[a];
    b.getAttribute("href") && b.hostname !== location.hostname && (b.target = "_blank")
  }
}
function PDF2new_window ()
{
  if (!document.getElementsByTagName) return false;
  var links = document.getElementsByTagName("a");
  for (var eleLink=0; eleLink < links.length; eleLink ++) {
    if ((links[eleLink].href.indexOf('.pdf') !== -1)||(links[eleLink].href.indexOf('.doc') !== -1)||(links[eleLink].href.indexOf('.docx') !== -1)) {
      links[eleLink].onclick =
        function() {
          window.open(this.href);
          return false;
        }
    }
  }
} 
PDF2new_window()
externalLinks();
</script>{% endraw %}
```

### Installation

Step 1. Download the file [new-window-fix.html](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/_includes/reading-time.html)
<br />Step 2. Save the file in the '_includes' directory of your project
<br />Step 3. Make sure the bottom of your layout document looks like this:

```
{% raw %}...
{% include new-window-fix.html %}
</body>
</html>{% endraw %}
```