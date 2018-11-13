---
title: Add your website to the home screen of iOS
---

I have been creating qutie a few native apps for clients. Because I am a big fan of website technology (simple and safe), I have been building native apps that consist of only a web view. They are basically website wrappers or browsers without a URL bar. This works fine for Android, but Apple refuses to allow these kind of apps in the Apple store. They will not tell you what the minimum functionality is you have to add, although big American companies, like Basecamp, seem to get away with only an extra menu. Somehow I get the feeling that might not be the case in my situation. Because I see no future in developing for a closed platform with arbitrary rules, I have chosen to make these websites installable as mobile web apps on iOS devices. In laymans terms this is called: adding the website to the home screen. Web developers call this PWA's (Progressive Web Apps).

Adding a website to the home screen in Android is as simple as pressing the right button in Chrome. For iOS this is a little bit more complicated. I have listed the complications:

- A home screen icon (PWA) can be created from Safari only (and not from Chrome for iOS).
- Clicking a link on the home screen can only be detected by the website (by javascript) if it opens in PWA mode (full screen, without an address bar).
- Apple does not allow page loads in PWA's, but will open the link in Safari (in a new window) instead.
- The PWA does not share its cookies with this new Safari window, nor does Safari share cookies with the PWA.

The desired functionality is very simple. We want to show a 'nagging' message that tells you to install the mobile app. If you have 'installed' the app and you click on its icon, this nagging message should be hidden. To accomplish this we let javascript detect Safari on iOS. That will show the instructions on how to add the website to the home screen. When the user clicks on this home screen icon, we let javascript detect the PWA version of the website. This is done by testing the 'window.navigator' for the 'standalone' variable, which is true in case of a PWA. We then let javascript add a parameter to the URL of every link on the page of the PWA. Once a link is clicked, the browser opens and the extra parameter makes sure a cookie is set (in Safari) that hides the nagging message forever.

Do you want to know what that looks like? Open this page on iOS and you will find out! If you like this implementation, you can use [this code](/without-plugin/add-to-home-screen-ios/) too, as I have added it to the without-plugins library of this website.