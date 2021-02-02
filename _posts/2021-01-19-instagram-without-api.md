---
title: Instagram without API
date: 2021-01-19 00:00:00 Z
---

In October of last year [I already wrote](/blog/instagram-on-your-website-without-api) about loading instagram on your website without an API. I edited the post several times since. Let me explain what happened. 

Since [instafeed.js](https://github.com/stevenschobert/instafeed.js) stopped working (in March/June 2020) I have explored several approaches for showing Instagram images on client websites without using the very complicated Facebook API. First I explored [Zapier](https://zapier.com/). I added the Instagram image URL's to a standard RSS feed, but Instagram started changing the URL's of their images over time, which made this solution only suitable for people who post every day. Therefore I explored the concept of a scraper that could fetch the images, using a headless browser. It turned out that Instagram was pretty good at blocking our IP addresses, so this did not work either. I had no choice but to do it the 'right' way...

Together with my very talented twin brother I created an actual Facebook/Instagram app, called 'profile page images', or [PPI Loader](https://profilepageimages.usecue.com). It authenticates with the Instagram API (so you don't have to) and gets a long lived access token for every user. Every 24 hours a cron job downloads your latest images (when you log in you can fire this job every hour). When your access token is getting old we automatically refresh it for you. Obviously you need to grant the application access to your Instagram account, which has to be done during the registration process. The cron job saves and hosts your images in a public directory on our server. Using these images is [a piece of cake](https://profilepageimages.usecue.com/getting-started).

Currently we are in a beta phase. The app itself has been approved by Facebook/Instagram (yeah!), but we are awaiting Facebooks Business Validation. Facebook has a way of making simple things pretty hard. Because of this app, you will never have to worry about coding a solution to put Instagram images on your clients website. Becoming a beta tester is as easy as entering your email address and Instagram username in [the registration form](https://profilepageimages.usecue.com/register). We can only allow for a limited amount of beta testers, so hurry if you like it! As soon as we are out of the beta phase, I will update this post (or write a new one).

UPDATE: Our Business Validation has been approved too! Therefore the app is no longer in development mode. This means the registration process is now instant and we no longer have the '50 users' limit.

Today I added automatic image scaling to the service. The scaled images have 50% jpg compression, are scaled to a 500px maximum for either width or height and weigh around 20kb each. A grid of ten Instagram images  weighs only 200kb, which is approximately the size of one large image. The images are served in a separate folder within your account, called 'small'. Pretty sweet, huh?
