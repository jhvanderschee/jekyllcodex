---
title: A complete rebuild of Jekyll Codex
date: 2019-11-10 00:00:00 Z
---

A big day for Jekyll Codex... because today I have launched a complete rebuild of the Jekyll Codex website. You may not see it, but I have rewritten all CSS and scripts so they will no longer use jQuery nor Twitter Bootstrap. This means the website has gone on a big diet, because jQuery and Twitter Bootstrap accounted for a hefty 250kb (compressed) per page load. This means that page loads have gone down from 400kb to less than 150kb. This influenced the Speed Index, which is now 1.0s instead of 1.8s. Quite some progress, which improves accessibility and SEO.

I realize that you may think that not using jQuery and Twitter Bootstrap will make your (or my) life harder. I also realize that you may think that 250kb on your first page load is 'not a big deal'. But plain Javascript has come a long way and writing plain Javascript is alsmost as easy as writing jQuery. Also, not having to fight 136kb of CSS from Twitter Bootstrap is absolutely worth having to re-style your inputs. But most important, this approach is absolutely essential when you want to build [websites that load instantly](https://www.usecue.com/blog/websites-that-load-instantly/). And, as Google promotes fast loading websites in its search ranking, we are talking about improved SEO too. So this change is not about short term results, but about better websites performance in the long run.

I [announced this change](/blog/ditching-jquery-and-twitter-bootstrap/) a while ago, but now I finally found the time to execute it. It took me about a week, but that is more of an investment than lost time... as I myself am the biggest user of (the scripts on) this website.

So what has changed? The most popular item that has changed significantly is the lightbox. I did not re-add the 'swipe' feature, as it was causing some bugs. I might add this feature later, but for now this functionality is gone. I did not re-add the captions, as I found myself removing them on every website I was using the lightbox.

Another big thing that has changed is the webshop. It depended on a Ajax call to Formspree. Formspree, however, removed these Ajax calls from their free tier. Although the Ajax call was still working in the free teir, I replaced it by a simple redirect. This allows you to choose any form handler you want and makes the webshop a lot easier to set up.

If you do not like all this new fancy stuff you can still visit the [old website](https://fresh-butterfly.cloudvent.net) at a CloudCannon development domain. 