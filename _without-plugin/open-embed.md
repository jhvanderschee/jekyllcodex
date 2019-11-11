---
title: Open embed
---

### Introduction

One of the nicer features of WordPres is that you can just paste a Youtube or Vimeo URL in the content (on a new line) and WordPress transforms this into an embed code. This script does the same for Jekyll. In the same way it also detects URL's that point to mp3 files and replaces them with a default HTML5 player. Here is an example (source: [FMA](http://freemusicarchive.org/music/Paper_Navy/All_Grown_Up/08_Swan_Song){: .gray}):

/uploads/Paper_Navy_-_08_-_Swan_Song.mp3

### How it works

The mp3 embedder can detect a link in this format: 'linktoyour.mp3?autoplay=1&loop=1&controls=0'. This will lead to an autoplaying, looping mp3 that is invisible (has no controls). Default the player will not autoplay, not loop and show controls, as shown in the example above. Autoplay and loop will also work (in the same way) on Youtube and Vimeo embeds.

[expand]

```
{% raw %}<style>
.videoWrapper {
	position: relative;
	padding-bottom: 56.333%;
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
function get_youtube_id(url) {
    var p = /^(?:https?:\/\/)?(?:www\.)?(?:youtu\.be\/|youtube\.com\/(?:embed\/|v\/|watch\?v=|watch\?.+&v=))((\w|-){11})(?:\S+)?$/;
    return (url.match(p)) ? RegExp.$1 : false;
}
function vimeo_embed(url,el) {
    var id = false;
    $.ajax({
      url: 'https://vimeo.com/api/oembed.json?url='+url,
      async: true,
      success: function(response) {
        if(response.video_id) {
          id = response.video_id;
          if(url.indexOf('autoplay=1') !== -1) var autoplay=1; else var autoplay=0;
          if(url.indexOf('loop=1') !== -1) var loop=1; else var loop=0;
          var theInnerHTML = '<div class="videoWrapper"><iframe src="https://player.vimeo.com/video/'+id+'/?byline=0&title=0&portrait=0';
          if(autoplay==1) theInnerHTML += '&autoplay=1';
          if(loop==1) theInnerHTML += '&loop=1';
          theInnerHTML += '" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe></div>'; 
          el.innerHTML = theInnerHTML;
        }
      }
    });
}
function video_embed() {
    var p = document.getElementsByTagName('p');
    for(var i = 0; i < p.length; i++) {
        //check if this is an external url (that starts with https:// or http://
        if (p[i].innerHTML.indexOf("http://") == 0 ||
            p[i].innerHTML.indexOf("https://") == 0) {
            var youtube_id = get_youtube_id(p[i].innerHTML);
            if(youtube_id) {
                if(p[i].innerHTML.indexOf('autoplay=1') !== -1) var autoplay=1; else var autoplay=0;
                if(p[i].innerHTML.indexOf('loop=1') !== -1) var loop=1; else var loop=0;
                var theInnerHTML = '<div class="videoWrapper"><iframe width="720" height="420" src="https://www.youtube.com/embed/' + youtube_id + '?rel=0&showinfo=0';
                if(autoplay==1) theInnerHTML += '&autoplay=1';
                if(loop==1) theInnerHTML += '&loop=1&playlist='+youtube_id+'&version=3';
                theInnerHTML += '" frameborder="0" allowfullscreen></iframe></div>';
                p[i].innerHTML = theInnerHTML;
            }
            if(p[i].innerHTML.indexOf('vimeo.com') !== -1) {
                //ask vimeo for the id and place the embed
                vimeo_embed(p[i].innerHTML,p[i]);
            }
        }
    }
}
video_embed();

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

Step 1. Download the file [open-embed.html](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/_includes/open-embed.html)<br>Step 2. Save the file in the '_includes' directory of your project<br>Step 3. Make sure the bottom of your layout document looks like this:

```
{% raw %}...
{% include open-embed.html %}
</body>
</html>{% endraw %}
```