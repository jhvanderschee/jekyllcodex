---
title: GDPR compliant comments
---

Being able to add comments to your posts is good for visitor engagement. Therefore I have created a [GDPR compliant comment script for Jekyll](/without-plugin/comments/). We do not want to send our valuable visitor data to a random surveillance company. Even more so, when the only purpose of that company is to make money from this data and when this company has a bad security reputation. Yes, I am talking about you, Facebook and Disqus.

> Data is stored on Disqus servers, and the company has been criticized for its user tracking activities. The company suffered two major security breaches, one in 2013 and another in October 2017. A snapshot of a database containing 17.5 million user email addresses, login dates and sign-up dates was copied according to Disqus in the latest breach.

I have chosen GitHub for hosting comments, as you probably host your website on GitHub anyway. This ensures you do not send any additional information to a third party (as all requests already go to GitHub), which makes you GDPR compliant. If you host your website elsewhere, you should make sure that your visitor has approved third party scripts through the [cookie consent banner](/without-plugin/cookie-consent/){:.gray}. I have implemented a 'require_cookie_consent' variable to make this optional.