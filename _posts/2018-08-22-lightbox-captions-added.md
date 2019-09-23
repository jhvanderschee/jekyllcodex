---
title: Lightbox captions added
date: 2018-08-22 00:00:00 Z
---

I was on a holiday in France and got an email from a guy named Stu who was using Jekyll Codex. He wrote: 

> "I have been developing a Jekyll website (hosted on github pages) and have made huge progress thanks to your tutorials and 'without plugins' codex. Thank you for those!" 

I was very pleased to hear that. But what was even better, was that he told me he had managed to alter the code of the lightbox in a way that it displayed the filename as a caption. A very clever and minimalistic idea. I asked him if I could review his code and add the functionality to the 'without plugins' directory. He immediately agreed. I polished the solution a little, by using the filename to also add automatic `alt` and `title` attributes. I also made it possible to disable the captions by using a front matter variable on the page called `lightbox_captions`, which can be set to `false`. If you want to disable the captions on the 'image gallery' or the 'image gallery index', you can simply set their appearance to `display: none` through CSS (it is just a span). Finally I added a small black border around the white text of the caption, to make them legible under all circumstances, a solution that is also used in closed captions on television. I think Stu and I did a pretty good job. Take a look at the end result here:

- [Lightbox (and gallery) with captions](/without-plugin/image-gallery)
- [Lightbox without captions](/without-plugin/lightbox)

If you find any bugs, please let me know. Please feel free to suggest any other additions or improvements. Once again I would like to conclude by saying that I am grateful for your feedback and that it is a great feeling to built something that people like and use. Happy coding!