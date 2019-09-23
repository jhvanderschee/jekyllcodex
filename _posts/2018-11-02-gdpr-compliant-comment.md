---
title: GDPR compliant comments
date: 2018-11-02 00:00:00 Z
comment_issue_id: 4
---

Being able to add comments to your posts is good for visitor engagement. Therefore I created a [GDPR compliant comment script for Jekyll](/without-plugin/comments/). You should not send your valuable visitor data to a random surveillance company. Especially not, when the only purpose of that company is to make money from this data and when this company has a bad security reputation. Yes, I am talking about Facebook and Disqus. A quote about Disqus I found on the internet:

> Data is stored on Disqus servers, and the company has been criticized for its user tracking activities. The company suffered two major security breaches, one in 2013 and another in October 2017. A snapshot of a database containing 17.5 million user email addresses, login dates and sign-up dates was copied according to Disqus in the latest breach.

I have chosen GitHub for hosting comments, as you probably host your website on GitHub anyway, GitHub has a decent reputation and it is possible to get a Data Processing Agreement (DPA) from GitHub. If you host your website on GitHub (Pages) you do not send any additional information to a third party (as all requests already go to GitHub), which makes you not any less GDPR compliant. If you host your website elsewhere, you should make sure that your visitor has approved third party scripts through the [cookie consent banner](/without-plugin/cookie-consent/){:.gray}. I have implemented a 'require_cookie_consent' variable to make the third party script approval optional.
