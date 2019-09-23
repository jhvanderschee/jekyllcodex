---
title: Jekyll against the rest of the world
date: 2015-11-09 00:00:00 Z
---

Heavy with confidence, I would deposit my lumbering frame in the middle of the room. My choice to go all static had been a good one. It was quite a serene scenery—nothing could touch me.

There were website owners running around wildly, chasing WordPress security vulnerabilities, while at the same time trying to plug holes, which the dubious free plug-ins they downloaded had ripped into their very essence.
<br />I saw a man standing at the window and bashing his head against it in a slow rhythmic pace. This wasn’t a medical condition. He was simply repeating the rate at which his PHP-based and database-driven publishing solution would accept new requests.
<br />From the corner of my eye I could make out a woman who was frantically flailing her arms about. She was trying to get into the room. Unfortunately, no one would let her in—her website had been infected with malware and whenever someone tried to visit it, there was a warning, urging users to run away as fast as they could.
<br />Static publishing, oh blissful serenity. Why do I like you so much?

### Dynamic is evil

It’s not, really. But bear with me for a moment.
<br />Imagine you’re publishing a new post on your site. How often does that content change? Is it really necessary to recreate the final HTML output you deliver to your users every single time someone accesses your site? Query the database, run it through the templating engine, run it through plugins, render HTML, deliver. That’s a lot of work.
<br />Most likely, you won’t notice this immediately. But if your site suddenly becomes popular, chances are, it won’t scale very well. It could go down. Of course there’s options for you if you wish to stay dynamic and have that flexibility. You could use caching plugins or even full-fledged web accelerators like Varnish. To me, this is just throwing huge piles of code and applications at the problem.

[...]

*This is the first part of an article from Tobias Horvath, posted at [tobyx.com](https://tobyx.com/2015/jekyll-vs-world).*