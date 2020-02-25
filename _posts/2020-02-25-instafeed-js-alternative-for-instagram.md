---
title: Instafeed.js alternative for Instagram
---

To show a users Instagram account pictures I used Instafeed.js. Instafeed.js was not only non-trivial to set up, but it also relied on the legacy API from Instagram that will be discontinued on March 2nd 2020 or [March 31 2020](https://developers.facebook.com/blog/post/2020/01/14/instagram-basic-display-api-long-lived-access-tokens-available/){:.gray}. Either way, time for a change. The developers behind Instafeed came to the conclusion that the new Instagram Basic Display API [requires server-side scripts](https://github.com/stevenschobert/instafeed.js/issues/635#issuecomment-576473432){:.gray}. A pure Javascript solution, like Instafeed.js, that directly gets content from Instagram, is no longer possible. 

### The solution

The solution I came up with is quite simple: fully split the server-side and client-side part by using XML(RSS) as an intermediate. For the server-side part I used Zapier (free). Zapier authenticates with Instagram and gets a long lived access token. Using this token it listens to the users feed with a five minute interval. When it discovers a new post/image, it adds this to a Zapier RSS feed that has nothing to do with Instagram. Now we just need a few lines of Javascript (8 to be exact) to visualize this RSS feed. A touch of CSS makes it easier on the eyes.

### The code

You can find the code below. Please read the [installation manual](https://jekyllcodex.org/without-plugin/instagram/). Note that using Jekyll is not a requirement.

```
<p id="instafeed"></p>

<script src="/js/jquery.min.js"></script>
<script type="text/javascript">
$.get('https://zapier.com/engine/rss/2502510/jhvanderschee', function (data) {
    $(data).find("item").each(function () { // or "item" or whatever suits your feed
        var el = $(this);
        var title = el.find("title").text();
        var link = el.find("link").text();
        var image = el.find("enclosure").attr('url');
        var description = el.find("description").text();
        $('#instafeed').append('<a href="'+encodeURI(link)+'" target="_blank" title="'+title.replace('Caption: ','')+'"><img src="'+encodeURI(image)+'" alt="'+title.replace('Caption: ','')+'" /></a>');
    });
});
</script>

<style>
    #instafeed {overflow: auto; margin-left: -1%;}
    #instafeed a {float: left; display: block; margin: 0 0 1% 1%; width: 19%;}
    #instafeed a img {width: 100%;}
</style>
```