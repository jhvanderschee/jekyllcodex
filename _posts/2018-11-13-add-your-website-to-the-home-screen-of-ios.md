---
title: Add your website to the home screen of iOS
date: 2018-11-13 00:00:00 Z
---

I have been creating quite a few native apps for clients. Because I am a big fan of website technology (simple and safe), I have been building native apps that consist of only a web view. They are basically website wrappers or browsers without a URL bar. This works fine for Android, but Apple refuses to allow these kind of apps in the Apple store. They will not tell you what the minimum functionality is you have to add, although big American companies, like Basecamp, seem to get away with only an extra menu. Somehow I get the feeling that might not be the case in my situation. Because I see no future in developing for a closed platform with arbitrary rules, I have chosen to make these websites installable as mobile web apps on iOS devices. In laymans terms this is called: adding the website to the home screen. Web developers call this PWA's (Progressive Web Apps).

If we want to add a website to the home screen, we are confronted with quite a few complications:

- A home screen icon (PWA) can only be created in the native browser of the platform (so not in Chrome for iOS).
- Clicking a link on the home screen can only be detected by the website (through javascript) if it opens in PWA mode (full screen, without an address bar).
- Apple/iOS does not allow a page load (link with a href) in a PWA. It will open the link in Safari (in a new window).
- A PWA does not share its cookies with the browser, nor does the browser share its cookies with the PWA.

The desired functionality, however, is very simple. We want to [show a (daily) reminder](/uploads/addtohomescreen1.jpeg) that tells you that you can install the mobile app. If you have 'installed' the app, its icon should be [added to the home screen](/uploads/addtohomescreen2.jpg). When you click on this home screen icon, the reminder should (obviously) be hidden forever. 

To accomplish this we let javascript detect Safari on iOS. The reminder shows the instructions on how to add the website to the home screen. If you dismiss these instructions a cookie will be set that expires in a day. When the user actually installs the app and clicks on the home screen icon, we let javascript detect this PWA version of the website. We do this by testing the 'window.navigator' for the 'standalone' variable, which is true in case of a PWA. We then let javascript add a parameter to the URL of every link on the page of the PWA. Once a link is clicked, the browser opens and the extra parameter makes sure a cookie is set (in the browser) that hides the reminder forever.

Do you want to know what that looks like? Check the image links in this article or open this page on iOS. If you like this implementation, you can use [this code](/without-plugin/add-to-home-screen-ios/) too, as I have added it to the without-plugins library of this website.