---
title: Ditching jQuery and Twitter Bootstrap
---

I have been using Jekyll Codex extensively the last few years and so have you. Jekyll Codex displays in Google has risen from almost zero to an average of 200 a day. The average amount of clicks has also risen from just a few to an average of 20 a day. 

Jekyll Codex has been my personal code base for reusable scripts, but the last months a shift has taken place in my personal workflow. I have gotten rid of all frameworks I was using. This means: no more (overriding) Twitter Bootstrap and no more jQuery. I am now writing my own CSS, using Flexbox and I have been chosing vanilla (plain) javascript over jQuery in all my new projects. This allows me to build [websites that are 20kb or smaller](https://www.usecue.com/). Twitter Bootstrap and Flexbox made my website unnecessary  large and slow. 

My ultimate goal is to 'fix' Jekyll Codex too: the code as well as the website itsself. I want the upgrade my Google Lighthouse score to a solid 100.

I have started by porting the code for the lightbox from jQuery to plain javascript. This was tougher than I thought. Porting code from jQuery to plain javascript is extremely educational and makes you appreciate the things jQuery can do (but not enough to keep it ;-)). The website youmightnotneedjquery.com, MDN web docs and Stack Overflow have been helpful resources.

Below you can find my first version of the plain javascript lightbox. You can see it in action [here](https://www.usecue.com/blog/the-need-for-speed-on-the-web/). 

```
    function is_youtubelink(url) {
      var p = /^(?:https?:\/\/)?(?:www\.)?(?:youtu\.be\/|youtube\.com\/(?:embed\/|v\/|watch\?v=|watch\?.+&v=))((\w|-){11})(?:\S+)?$/;
      return (url.match(p)) ? RegExp.$1 : false;
    }
    function is_imagelink(url) {
        var p = /([a-z\-_0-9\/\:\.]*\.(jpg|jpeg|png|gif))/i;
        return (url.match(p)) ? true : false;
    }
    function is_vimeolink(url,el) {
        var id = false;
        var xmlhttp = new XMLHttpRequest();
        xmlhttp.onreadystatechange = function() {
            if (xmlhttp.readyState == XMLHttpRequest.DONE) {   // XMLHttpRequest.DONE == 4
                if (xmlhttp.status == 200) {
                    var response = JSON.parse(xmlhttp.responseText);
                    id = response.video_id;
                    console.log(id);
                    el.classList.add('lightbox-vimeo');
                    el.setAttribute('data-id',id);

                    el.addEventListener("click", function(event) {
                        event.preventDefault();
                        document.getElementById('lightbox').innerHTML = '<a id="close"></a><a id="next">&rsaquo;</a><a id="prev">&lsaquo;</a><div class="videoWrapperContainer"><div class="videoWrapper"><iframe src="https://player.vimeo.com/video/'+el.getAttribute('data-id')+'/?autoplay=1&byline=0&title=0&portrait=0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe></div></div>';
                        document.getElementById('lightbox').style.display = 'block';

                        setGallery(this);
                    });
                }
                else if (xmlhttp.status == 400) {
                    alert('There was an error 400');
                }
                else {
                    alert('something else other than 200 was returned');
                }
            }
        };
        xmlhttp.open("GET", 'https://vimeo.com/api/oembed.json?url='+url, true);
        xmlhttp.send();
    }
    function setGallery(el) {
        var elements = document.body.querySelectorAll(".gallery");
        elements.forEach(element => {
            element.classList.remove('gallery');
        });
        var link_elements = el.parentNode.querySelectorAll("a[class*='lightbox-']");
        link_elements.forEach(link_element => {
            link_element.classList.remove('current');
        });
        link_elements.forEach(link_element => {
            if(el.getAttribute('href') == link_element.getAttribute('href')) {
                link_element.classList.add('current');
            }
        });
        if(link_elements.length>1) {
            document.getElementById('lightbox').classList.add('gallery');
            link_elements.forEach(link_element => {
                link_element.classList.add('gallery');
            });
        }
        var currentkey;
        var gallery_elements = document.querySelectorAll('a.gallery');
        Object.keys(gallery_elements).forEach(function (k) {
            if(gallery_elements[k].classList.contains('current')) currentkey = k;
        });
        if(currentkey==(gallery_elements.length-1)) var nextkey = 0;
        else var nextkey = parseInt(currentkey+1);
        if(currentkey==0) var prevkey = (gallery_elements.length-1);
        else var prevkey = parseInt(currentkey-1);

        document.getElementById('next').addEventListener("click", function() {
            gallery_elements[nextkey].click();
        });
        document.getElementById('prev').addEventListener("click", function() {
             gallery_elements[prevkey].click();
        });
    }

    document.addEventListener("DOMContentLoaded", function() {
        //add classes to links to be able to initiate lightboxes
        var elements = document.querySelectorAll('a');
        elements.forEach(element => {
            var url = element.getAttribute('href');
            if(url) {
                if(url.indexOf('vimeo') !== -1 && !element.classList.contains('no-lightbox')) {
                    is_vimeolink(url,element);
                }
                if(is_youtubelink(url) && !element.classList.contains('no-lightbox')) {
                    element.classList.add('lightbox-youtube');
                    element.setAttribute('data-id',is_youtubelink(url));
                }
                if(is_imagelink(url) && !element.classList.contains('no-lightbox')) {
                    element.classList.add('lightbox-image');
                    var href = element.getAttribute('href');
                    var filename = href.split('/').pop();
                    var split = filename.split(".");
                    var name = split[0];
                    element.setAttribute('title',name);
                }
            }
        });

        //remove the clicked lightbox
        document.getElementById('lightbox').addEventListener("click", function(event) {
            if(event.target.id != 'next' && event.target.id != 'prev'){
                this.innerHTML = '';
                document.getElementById('lightbox').style.display = 'none';
            }
        });
      
        //add the youtube lightbox on click
        var elements = document.querySelectorAll('a.lightbox-youtube');
        elements.forEach(element => {
            element.addEventListener("click", function(event) {
                event.preventDefault();
                document.getElementById('lightbox').innerHTML = '<a id="close"></a><a id="next">&rsaquo;</a><a id="prev">&lsaquo;</a><div class="videoWrapperContainer"><div class="videoWrapper"><iframe src="https://www.youtube.com/embed/'+this.getAttribute('data-id')+'?autoplay=1&showinfo=0&rel=0"></iframe></div>';
                document.getElementById('lightbox').style.display = 'block';

                setGallery(this);
            });
        });

        //add the image lightbox on click
        var elements = document.querySelectorAll('a.lightbox-image');
        elements.forEach(element => {
            element.addEventListener("click", function(event) {
                event.preventDefault();
                document.getElementById('lightbox').innerHTML = '<a id="close"></a><a id="next">&rsaquo;</a><a id="prev">&lsaquo;</a><div class="img" style="background: url(\''+this.getAttribute('href')+'\') center center / contain no-repeat;" title="'+this.getAttribute('title')+'" ><img src="'+this.getAttribute('href')+'" alt="'+this.getAttribute('title')+'" /></div><span>'+this.getAttribute('title')+'</span>';
                document.getElementById('lightbox').style.display = 'block';

                setGallery(this);
            });
        });

    });
```