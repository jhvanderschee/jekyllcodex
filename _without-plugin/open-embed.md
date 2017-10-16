---
title: Open embed
---

### Introduction

One of the nicer features of WordPres is that you can just paste a Youtube URL in the content (on a new line) and WordPress transforms this into an embed code.

### How it works

```
{% raw %}
<script>
function getId(url) {
    var regExp = /^.*(youtu.be\/|v\/|u\/\w\/|embed\/|watch\?v=|\&v=)([^#\&\?]*).*/;
    var match = url.match(regExp);
    if (match && match[2].length == 11) {
        return match[2];
    } else {
        return 'error';
    }
}
function yt_url2embed() {
    var p = document.getElementsByTagName('p');
    for(var i = 0; i < p.length; i++) {
        var pattern = /^((http|https|ftp):\/\/)/;
        if(pattern.test(p[i].innerHTML)) {
            var myId = getId(p[i].innerHTML);
            p[i].innerHTML = '<div class="videoWrapper"><iframe width="720" height="420" src="https://www.youtube.com/embed/' + myId + '?rel=0&amp;showinfo=0" frameborder="0" allowfullscreen></iframe></div>';
        }
    }
}
yt_url2embed();
PDF2new_window()
externalLinks();
</script>{% endraw %}
```