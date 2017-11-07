---
title: Open embed
---

### Introduction

One of the nicer features of WordPres is that you can just paste a Youtube URL in the content (on a new line) and WordPress transforms this into an embed code. This script does the same for Jekyll, using some Vanilla JS. In the same way it detects URL's that point to mp3 files and replaces them with a default HTML5 player. I recommend you to use these links on a new line too. Here is an example (source: <a href="http://freemusicarchive.org/music/Paper_Navy/All_Grown_Up/08_Swan_Song" target="_blank" style="color: #777777;">FMA</a>):

/uploads/Paper_Navy_-_08_-_Swan_Song.mp3

### How it works

The following script is being added to your footer. The mp3 embedder can detect a link in this format: 'linktoyour.mp3?autoplay=1&loop=1&controls=0'. This will lead to an autoplaying, looping mp3 that is invisible (has no controls). Default the player will not autoplay, not loop and show controls, as shown in the example above.

[expand]

```
{% raw %}<style>
.videoWrapper {
	position: relative;
	padding-bottom: 56.333%; /* custom */
	height: 0;
}
.videoWrapper iframe {
	position: absolute;
	top: 0;
	left: 0;
	width: 100%;
	height: 100%;
}    
</style>

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
        var pattern = /^((http|https):\/\/)/;
        if(pattern.test(p[i].innerHTML)) {
            var myId = getId(p[i].innerHTML);
            p[i].innerHTML = '<div class="videoWrapper"><iframe width="720" height="420" src="https://www.youtube.com/embed/' + myId + '?rel=0&amp;showinfo=0" frameborder="0" allowfullscreen></iframe></div>';
        }
    }
}
yt_url2embed();

function mp3_embed() {
    var p = document.getElementsByTagName('p');
    for(var i = 0; i < p.length; i++) {
        if(p[i].innerHTML.indexOf('.mp3') !== -1) {
            var str = p[i].innerHTML.split('?');
            if(str.length == 1) str[1] = '';
            var str1 = str[1];
            str1 = str1.replace('&','').replace('&','');
            str1 = str1.replace('autoplay=1','').replace('autoplay=0','');
            str1 = str1.replace('loop=1','').replace('loop=0','');
            str1 = str1.replace('controls=0','').replace('controls=1','');
            
            if (str[0].lastIndexOf('.mp3', str[0].length - 4) === str[0].length - 4 && str1.length == 0) {
                if(str[1].indexOf('autoplay=1') !== -1) var autoplay=1; else var autoplay=0;
                if(str[1].indexOf('loop=1') !== -1) var loop=1; else var loop=0;
                if(str[1].indexOf('controls=0') !== -1) var controls=0; else var controls=1;
                var newInnerHTML = '<audio';
                if(autoplay==1) newInnerHTML += ' autoplay';
                if(loop==1) newInnerHTML += ' loop';
                if(controls==1) newInnerHTML += ' controls';
                newInnerHTML += '><source src="'+str[0]+'" type="audio/mpeg">Your browser does not support the audio element.</audio>';
                p[i].innerHTML = newInnerHTML;
            }
        }
    }
}
mp3_embed();
</script>{% endraw %}
```

[/expand]

### Installation

Step 1. Download the file [open-embed.html](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/_includes/open-embed.html)
<br />Step 2. Save the file in the '_includes' directory of your project
<br />Step 3. Make sure the bottom of your layout document looks like this:

```
{% raw %}...
{% include open-embed.html %}
</body>
</html>{% endraw %}
```