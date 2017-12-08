---
title: "Slider"
inactive: true
---

### Introduction

This page is coming soon... Do not want to wait? Send me an email on <a href="mailto:jhvanderschee@gmail.com" style="color: #777777;">jhvanderschee@gmail.com</a>.


<div id="myCarousel" class="carousel slide" data-ride="carousel">
  <!-- Indicators -->
  <ol class="carousel-indicators">
    <li data-target="#myCarousel" data-slide-to="0" class="active"></li>
    <li data-target="#myCarousel" data-slide-to="1"></li>
    <li data-target="#myCarousel" data-slide-to="2"></li>
  </ol>

  <!-- Wrapper for slides -->
  <div class="carousel-inner">
    <div class="item active">
      <img src="//images.weserv.nl/?url=jekyllcodex.org/uploads/slider/1.jpg&w=1000&h=500&output=jpg&q=50&t=square" alt="1">
    </div>
    <div class="item">
      <img src="//images.weserv.nl/?url=jekyllcodex.org/uploads/slider/2.jpg&w=1000&h=500&output=jpg&q=50&t=square" alt="2">
    </div>
    <div class="item">
      <img src="//images.weserv.nl/?url=jekyllcodex.org/uploads/slider/3.jpg&w=1000&h=500&output=jpg&q=50&t=square" alt="3">
    </div>
  </div>

  <!-- Left and right controls -->
  <a class="left carousel-control" href="#myCarousel" data-slide="prev">
    <span class="glyphicon glyphicon-chevron-left">‹</span>
    <span class="sr-only">Previous</span>
  </a>
  <a class="right carousel-control" href="#myCarousel" data-slide="next">
    <span class="glyphicon glyphicon-chevron-right">›</span>
    <span class="sr-only">Next</span>
  </a>
</div>
<style>
span.glyphicon {
    font-family: "Open Sans","Helvetica Neue",Helvetica,Arial,sans-serif!important;
    color: white!important;
    font-size: 60px!important;
    height: 60px!important;
    line-height: 60px!important;
    margin-top: -30px!important;
}
.carousel-control {opacity: 0!important;}
.carousel-control:hover {opacity: 1!important;}
.carousel-indicators {bottom: 10px;}
.glyphicon-chevron-left::before,
.glyphicon-chevron-right::before {
    content: "";
}
</style>