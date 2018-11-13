---
title: Add your website to the home screen of iOS
---

I have been creating some native apps for clients. Because I am a big fan of website technology (simple and safe), I have been building apps that consist of only a web view. They are basically website wrappers or browsers without a URL bar. This works fine for Android, but Apple refuses to allow these kind of apps in the Apple store. They will not tell you what the minimum functionality is you have to add, although companies like Basecamp seem to get away something similar. Therefore I have chosen for some clients to make the website installable on their iOS device. In laymans terms this is called: adding the website to the home screen. Web developers call this PWA's (Progressive Web Apps).

Adding an Android app to the home screen is as simple as pressing the right button in Chrome. For iOS this is a little bit more complicated. I have listed the complications:

- A home screen icon (PWA) can be created from Safari only (not from Chrome for iOS).
- Clicking a link on the home screen can only be detected by the website (by javascript) if it opens in PWA mode (full screen, without an address bar).
- Apple does not allow page loads in a PWA, but will open Safari in a new window if it detects a page load.
- The PWA does not share its cookies with this new Safari window, nor does Safari share cookies with the PWA.

The desired functionality is very simple. We want to show a 'nagging' message that tells you to install the mobile app. If you have 'installed' the home screen icon and you click it, the message should be hidden. To accomplish this we let javascript detect the PWA version of the website. If it is detected we add a parameter to the URL of every link to let Safari know we want hide the nagging message forever with a cookie. Once a link with the extra paramater is clicked, Safari is opened and the extra parameter makes sure the cookie is being set.

Do you want to know what that looks like? Open this page on iOS and you will find out!