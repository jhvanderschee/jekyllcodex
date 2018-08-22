---
title: Lightbox captions added
---

I was on a holiday in France and got an email from a guy who was using Jekyll Codex. He wrote: 

> "I have been developing a Jekyll website (hosted on github pages) and have made huge progress thanks to your tutorials and 'without plugins' codex. Thank you for those!" 

You are welcome! That is exactly what this website is for. He added that he had managed to alter the code of the lightbox in a way that it displayed the filename as a caption. A very clever idea. I reviewed his code and his solution and added the filename as caption functionality to the [image gallery code](/without-plugin/image-gallery) in the 'without plugins' directory. I added the option to disable captions, using a front matter variable on the page called `lightbox_captions`, which can be set to false. You can see this [here](/without-plugin/lightbox).