---
title: About availability and redundancy
date: 2018-12-10 00:00:00 Z
---

The hardest problem to solve with static site generators, is availability and redundancy. In a monolithic system you would just replicate the server and you will have a complete fail-over. This is not so simple for Static Site Generators. However, you can quite easily deploy a website to multiple platforms. I have used this website as an example.

### What if the hosting is down?

When this website goes down, I just need to point the DNS of the domain name to another service and it is back online. This process can be automated with [DNS failover](https://dnsmadeeasy.com/services/dnsfailover/){:.gray}. This is a DNS system that automatically updates your records based on the availability of the endpoints in the record. Magic, right?

- This website is available at Netlify hosting at [https://boatman-bird-64062.netlify.com/](https://boatman-bird-64062.netlify.com/){:.gray}.
- This website is available at CloudCannon hosting at [https://gifted-pooch.cloudvent.net/](https://gifted-pooch.cloudvent.net/){:.gray}.
- This website is available at Github hosting at [http://jhvanderschee.github.io/jekyllcodex/](http://jhvanderschee.github.io/jekyllcodex/){:.gray}.

### What if the CMS does not work properly?

I have set up different CMS services that work at the same time. Note that each CMS has his own levels of access. CloudCannon provides full/code access AND limited/editor access. Forestry.io and Netlify CMS only provide limited/editor access and Github only provides full/code access.

- This website can be edited directly on [Github](https://github.com/jhvanderschee/jekyllcodex){:.gray}.
- This website can be edited in [Forestry.io](https://forestry.io){:.gray}.
- This website can be edited in [CloudCannon](https://cloudcannon.com){:.gray}.
- This website can be edited in [Netlify CMS](https://www.netlifycms.org){:.gray}.

### Then why is it hard?

In reality there is a lot more going on in a static site. It is not just the hosting and the CMS. This site, for example, uses dynamic image resizing. I use [images.weserv.nl](https://images.weserv.nl){:.gray} for that for which I currently have no failover. CloudCannon can solve the image resizing partially for us, making [images.weserv.nl](https://images.weserv.nl){:.gray} potentially obsolete, but it is not yet very efficient and I have not seen any other CMS do this so far. Then there is 'forms'. As you can see in the [form builder](/without-plugin/form-builder) I have implemented several form engines... and for a reason. You want to be able to easily switch your form engine. Forms can use the platform-specific solution, like [forms on Netlify](https://www.netlify.com/docs/form-handling/){:.gray} or [forms on CloudCannon](https://docs.cloudcannon.com/hosting/forms/introduction/){:.gray}. These are reliable solutions, but they only work on their own hosting platform. You can also choose platform-independent form handlers like [Formspree](https://formspree.io/){:.gray} or [FormBucket](https://www.formbucket.com/){:.gray}. If you use them, your forms will work on any hosting platform, but they have a bigger chance of being down. Finally, each website has some very specific solutions, like a [webshop](/without-plugin/webshop) or [comments](/without-plugin/comments), using [Github](https://github.com/){:.gray} or [Staticman](https://staticman.net/){:.gray}. These specific solutions are very hard to replace.

### How to best solve the redundancy problem

For important forms I have set up an extra AJAX form submission, to have the form entry duplicated. When the AJAX form submission returns an error code it nevertheless submits the 'normal' form. Setting up a failover DNS is a good measure too, as well as configuring multiple CMS systems. In reality every service fails every now and then and the more services you use, the more failure you will encounter. The most important thing is to be aware of it, so you can limit the impact. This can be done by monitoring uptime. I use [Uptime Robot](https://uptimerobot.com){:.gray} for this. If a service goes down, [Uptime Robot](https://uptimerobot.com){:.gray} will send me an email. If that happens I assess what to do next. A short term solution is to switch from provider and a long term solution is to improve the redundancy.
