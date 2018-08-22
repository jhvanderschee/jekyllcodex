---
title: Lightbox captions added
---

I was on a holiday in France and got an email from a guy who was using Jekyll Codex. He wrote: 

> "I have been developing a Jekyll website (hosted on github pages) and have made huge progress thanks to your tutorials and 'without plugins' codex. Thank you for those!" 

You are welcome! What a great feeling to have built something that people like and use. I love it. 

He also mentioned that he had managed to alter the code of the lightbox in a way that it displayed the filename as a caption. A very clever and minimalistic idea. I reviewed his code, updated it a bit and added this functionality to the image gallery code in the 'without plugins' directory. I have polished the whole idea a little, by adding automatic `alt` and `title` attributes to the images, based on the filename. You can also disable the captions, by using a front matter variable on the page called `lightbox_captions`, which can be set to `false`. If you want to disable the captions on the image gallery or the image gallery index, you can set their appearance to `display: none` through CSS. Finally I added a black border around the white text of the caption, to prevent legibility problems. I stole this solutions from closed captions on television. Take a look at the end-result here:

- [Lightbox (and gallery) with captions](/without-plugin/image-gallery)
- [Lightbox without captions](/without-plugin/lightbox)

This great solution is now available for everybody to use. If you find any bugs, please let me know. Please feel free to suggest any other additions or improvements.