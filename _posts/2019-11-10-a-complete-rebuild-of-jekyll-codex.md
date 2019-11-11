---
title: A complete rebuild of Jekyll Codex
date: 2019-11-10 00:00:00 Z
---

A big day for Jekyll Codex... because today I have launched a complete rebuild of the Jekyll Codex website. You may not see it, but I have rewritten all CSS and scripts so they will no longer use jQuery nor Twitter Bootstrap. This means the website has gone on a big diet, because jQuery and Twitter Bootstrap accounted for a hefty 250kb (compressed) per page load. This means that page loads have gone down from 400kb to less than 150kb, which will be good for speed and SEO.

You may think that not using jQuery and Twitter Bootstrap will make my (or your) life harder. You may also think that 250kb on your first page load is 'not a big deal'. But plain Javascript has come a long way and writing plain Javascript is alsmost as easy as writing jQuery, so there is no excuse anymore. And not having to fight 136kb of CSS from Twitter Bootstrap is absolutely worth having to re-style your inputs. But most important... this approach is absolutely essential when you want to build [websites that load instantly](https://www.usecue.com/blog/websites-that-load-instantly/).

I [announced this change](/blog/ditching-jquery-and-twitter-bootstrap/) a while ago, but now I finally found the time to execute it. It took me about a week, but that is more of an investment than lost time... as I myself am the biggest user of (the scripts on) this website.

So what has changed? The most popular item that has changed significantly is the lightbox. I have removed the 'swipe' feature, as it was causing some bugs. I might re-add this feature later, but for now this functionality is gone. I also removed the captions, as I found myself removing them on every website I was using the lightbox.

Another big thing that has changed is the webshop. It depended on a Ajax call to Formspree. Formspree, however, removed Ajax calls from their free tier. This Ajax call was also hard to set up, because you needed to bypass the authentication/captcha step. Although the Ajax call was still working in the free teir, I replaced it by a simple redirect. This allows you to choose any formhandler you want and makes the webshop a lot easier to set up.