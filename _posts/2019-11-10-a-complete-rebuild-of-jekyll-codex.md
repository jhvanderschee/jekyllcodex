---
title: A complete rebuild of Jekyll Codex
date: 2019-11-10 00:00:00 Z
---

I wrote in July that Jekyll Codex displays in Google has risen from almost zero to an average of 200 a day. I am happy to announce that that amount has doubled in the last four months! The average amount of clicks has also risen from 20 to a little under 30 a day. This makes for an average of around 900 visits per month. Great news! I hope that this rebuild will improve my Google ranking even further.

### A big day for Jekyll Codex

Today I have launched a complete rebuild of the Jekyll Codex website, which I [announced](/blog/ditching-jquery-and-twitter-bootstrap/) a while ago. You may not see it, but I have rewritten all CSS and scripts, so they will no longer use jQuery nor Twitter Bootstrap. This means the website has gone on quite a diet, because jQuery and Twitter Bootstrap accounted for a hefty 250kb (compressed) per page load. Page loads have gone down from 400kb to less than 150kb. This influenced the Speed Index, which is now 1.0s instead of 1.8s. Quite some progress, which improves accessibility and SEO.

You may think that NOT using jQuery and Twitter Bootstrap will make your (or my) life harder. You may also think that 250kb on your first page load is 'not a big deal'. But plain Javascript has come a long way and writing plain Javascript is alsmost as easy as writing jQuery. Also, not having to fight 136kb of CSS from Twitter Bootstrap is absolutely worth having to re-style your inputs. But the most important reason is that this approach is essential when you want to build [websites that load instantly](https://www.usecue.com/blog/websites-that-load-instantly/). And, as [Google promotes fast loading websites](https://www.usecue.com/blog/google-will-shame-slow-websites/) in its search engine, we are talking about improved SEO too. So this change is not about short term results, but about better websites performance in the long run. It is [a strategy to get a 100% Google Lighthouse score](https://www.usecue.com/blog/how-to-get-a-100-google-lighthouse-score/).

### So what has changed? 

Responsiveness is now fully handled in plain CSS. My philosophy is that CSS and JS have evolved to a point where frameworks do more harm than good. Making a website responsive is very easy when you use flexbox and/or CSS columns. Therefore I changed the 'Mobile menu' script into a 'Toggle menu' script that is no longer dependent on Twitter Bootstrap and jQuery. I also rewritten all sizes and break-points (media queries) from 'px' to 'rem'. This makes the website truly scalable with a single setting: the font-size in 'px' on the HTML element.

The most popular item that has changed is the lightbox. I did not re-add the 'swipe' feature, as it was causing some bugs. I might add this feature later, but for now this functionality is gone. I did not re-add the captions, as I found myself removing them on every website I was using the lightbox and I was having enough on my plate already. I might add this functionality later. 

Another thing I rebuilt is the slider, or carousel. I replaced the Twitter Bootstrap variant with a pure CSS carousel. When I have time left I will re-add things like HTML texts in the slides and the option to choose for a fade transition. 

The biggest change of all is the webshop. It depended on a Ajax call to Formspree. Formspree, however, removed these Ajax calls from their free tier. Although the Ajax call was still working, I replaced it by a simple redirect. This allows you to choose any form handler you want and makes the webshop a lot easier to set up. Additionally I simplified the product template and data structure and cour cart is now stored in a JSON object in local storage instead of in a string in a cookie.

### Not yet completely finished

Although 99% of the work is ready, some things are still depending on jQuery. They will be replaced soon. These are the following items:

- Add to homescreen
- Better forms
- Comments

### You liked the old code better?

If you do not like all this new fancy stuff you can still visit the [jQuery and Twitter Bootstrap version](https://fresh-butterfly.cloudvent.net) of this website at a CloudCannon development domain. This is useful if your website is using jQuery anyway or if your website is based on the old code. I will not work on/update the old version anymore. If you want to move foward, the new way is the way to go ;-).
