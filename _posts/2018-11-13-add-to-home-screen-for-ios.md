---
title: Add to home screen for iOS
---

I have been creating some native apps for clients. Because I am a big fan of website technology (simple and safe), I have been building apps that are basically website wrappers (web view) or browsers without a URL bar. This works fine for Android, but Apple refuses to allow apps with only a web view in the Apple store. They will not tell you what the minimum functionality is you have to add, although companies like Basecamp seem to get away with it. Therefore I have chosen for some clients to make the website installable on their iOS device. In laymans terms this is called: adding the website to the home screen. Web developers call this PWA's (Progressive Web Apps).

Adding an Android app to the home screen is as simple as pressing the right button in Chrome. For iOS this is a little bit more complicated. I have listed the complications:

- A home screen icon (PWA) must be created from Safari.
- A link from the home screen can only be detected by the browser (javascript) if it opens in PWA mode (full screen, without an address bar).
- The PWA does not share its cookies with this new Safari window, nor the other way around.
- Apple does not allow page loads in a PWA, but will open Safari in a new window if it detects a page load.

The desired functionality is a 'nagging' message that tells you to install the mobile app. If you have 'installed' the home screen icon and you open the PWA, the message should be hidden. To accomplish this we let javascript detect the PWA version of the website. If it is detected we add a parameter to the URL of every link to let Safari know we want hide the nagging message forever with a cookie.

Do you want to know what that looks like? Open this page on iOS and you will find out!