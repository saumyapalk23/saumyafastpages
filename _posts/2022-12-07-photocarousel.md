---
layout: default
title: Photo Carousel
description: an awesome carousel
permalink: /frontend12/PhotoCarousel
image: /images/IMG_3501.jpg
categories: [pbl]
tags: [javascript]
---

{% include nav_frontend.html %}

<html>
<!-- Slideshow container -->
<div class="slideshow-container">

  <!-- Full-width images with number and caption text -->
  <div class="mySlides fade">
    <div class="numbertext">5 / 16</div>
    <img src="{{site.baseurl}}//imagescarousel/IMG_7613.jpg" style="width:100%">
    <div class="text">heh</div>
  </div>

<div class="mySlides fade">
    <div class="numbertext">2 / 16</div>
    <img src="{{site.baseurl}}//imagescarousel/IMG_1157.JPG" style="width:100%">
    <div class="text">yeehaw</div>
  </div>

  <div class="mySlides fade">
    <div class="numbertext">3 / 16</div>
    <img src="{{site.baseurl}}//imagescarousel/IMG_6068.jpg" style="width:100%">
    <div class="text">yessir</div>
  </div>

  <div class="mySlides fade">
    <div class="numbertext">4 / 16</div>
    <img src="{{site.baseurl}}//imagescarousel/0101161417_HDR_Original.jpg" style="width:100%">
    <div class="text">!!</div>
  </div>

   <!-- <div class="mySlides fade">
    <div class="numbertext">6 / 16</div>
    <img src="{{site.baseurl}}//imagescarousel/IMG_0653.jpg" style="width:100%">
    <div class="text">Caption Three</div>
  </div> -->

  <div class="mySlides fade">
    <div class="numbertext">7 / 16</div>
    <img src="{{site.baseurl}}//imagescarousel/9B60FA77-226E-4C2C-A2CE-8C1BA9A9DA77.jpg" style="width:100%">
    <div class="text">awsum</div>
  </div>

  
  <div class="mySlides fade">
    <div class="numbertext">8 / 16</div>
    <img src="{{site.baseurl}}//imagescarousel/446A7ECE-D696-432A-8408-92317011EDFD.jpg" style="width:100%">
    <div class="text">lolol</div>
  </div>

  <div class="mySlides fade">
    <div class="numbertext">9 / 16</div>
    <img src="{{site.baseurl}}//imagescarousel/446A7ECE-D696-432A-8408-92317011EDFD.jpg" style="width:100%">
    <div class="text">yaws</div>
  </div>

  <!-- <div class="mySlides fade">
    <div class="numbertext">10 / 16</div>
    <img src="{{site.baseurl}}//imagescarousel/imageone.jpg" style="width:100%">
    <div class="text">Caption Three</div>
  </div> -->

  <div class="mySlides fade">
    <div class="numbertext">1 / 16</div>
    <img src="{{site.baseurl}}//imagescarousel/IMG_3501.jpg" style="width:100%">
    <div class="text">hopefully ppl dont see this</div>
  </div>

  <div class="mySlides fade">
    <div class="numbertext">11 / 16</div>
    <img src="{{site.baseurl}}//imagescarousel/imagetwo.jpg" style="width:100%">
    <div class="text">!!!</div>
  </div>

  <div class="mySlides fade">
    <div class="numbertext">12 / 16</div>
    <img src="{{site.baseurl}}//imagescarousel/imagethree.JPG" style="width:100%">
    <div class="text">yaass</div>
  </div>

  <div class="mySlides fade">
    <div class="numbertext">13 / 16</div>
    <img src="{{site.baseurl}}//imagescarousel/PHOTO-2022-05-29-16-05-27.jpg" style="width:100%">
    <div class="text">ayyy</div>
  </div>

  <div class="mySlides fade">
    <div class="numbertext">14 / 16</div>
    <img src="{{site.baseurl}}//imagescarousel/PHOTO-2022-06-17-16-58-00.jpg" style="width:100%">
    <div class="text">wowza</div>
  </div>

  
  <div class="mySlides fade">
    <div class="numbertext">15 / 16</div>
    <img src="{{site.baseurl}}//imagescarousel/qinnis.jpg" style="width:100%">
    <div class="text">yawzers</div>
  </div>

  
  <div class="mySlides fade">
    <div class="numbertext">16 / 16</div>
    <img src="{{site.baseurl}}//imagescarousel/queens.jpg" style="width:100%">
    <div class="text">kweens</div>
  </div>

  <!-- Next and previous buttons -->
  <a class="prev" onclick="plusSlides(-1)">&#10094;</a>
  <a class="next" onclick="plusSlides(1)">&#10095;</a>

</div>
<br>

<!-- The dots/circles -->
<div style="text-align:center">
  <span class="dot" onclick="currentSlide(1)"></span>
  <span class="dot" onclick="currentSlide(2)"></span>
  <span class="dot" onclick="currentSlide(3)"></span>
  <span class="dot" onclick="currentSlide(3)"></span>
  <span class="dot" onclick="currentSlide(4)"></span>
  <span class="dot" onclick="currentSlide(5)"></span>
  <span class="dot" onclick="currentSlide(6)"></span>
  <span class="dot" onclick="currentSlide(7)"></span>
  <span class="dot" onclick="currentSlide(8)"></span>
  <span class="dot" onclick="currentSlide(9)"></span>
  <span class="dot" onclick="currentSlide(10)"></span>
  <span class="dot" onclick="currentSlide(11)"></span>
  <span class="dot" onclick="currentSlide(12)"></span>
  <span class="dot" onclick="currentSlide(13)"></span>
  <span class="dot" onclick="currentSlide(14)"></span>
  <span class="dot" onclick="currentSlide(15)"></span>
  <span class="dot" onclick="currentSlide(16)"></span>



</div>
</html>


<style>
    * {box-sizing:border-box}

/* Slideshow container */
.slideshow-container {
  max-width: 1000px;
  position: relative;
  margin: auto;
}

/* Hide the images by default */
.mySlides {
  display: none;
}

/* Next & previous buttons */
.prev, .next {
  cursor: pointer;
  position: absolute;
  top: 600%;
  left: 200%;
  right: 200%;
  width: auto;
  margin-top: -22px;
  padding: 16px;
  color: white;
  font-weight: bold;
  font-size: 18px;
  transition: 0.6s ease;
  border-radius: 0 3px 3px 0;
  user-select: none;
}

/* Position the "next button" to the right */
.next {
  right: 0;
  border-radius: 3px 0 0 3px;
}

/* On hover, add a black background color with a little bit see-through */
.prev:hover, .next:hover {
  background-color: rgba(0,0,0,0.8);
}

/* Caption text */
.text {
  color: #f2f2f2;
  font-size: 15px;
  padding: 8px 12px;
  position: absolute;
  bottom: 8px;
  width: 100%;
  text-align: center;
}

/* Number text (1/3 etc) */
.numbertext {
  color: #f2f2f2;
  font-size: 12px;
  padding: 8px 12px;
  position: absolute;
  top: 0;
}

/* The dots/bullets/indicators */
.dot {
  cursor: pointer;
  height: 15px;
  width: 15px;
  margin: 0 2px;
  background-color: #bbb;
  border-radius: 50%;
  display: inline-block;
  transition: background-color 0.6s ease;
}

.active, .dot:hover {
  background-color: #717171;
}

/* Fading animation */
.fade {
  animation-name: fade;
  animation-duration: 1.5s;
}

@keyframes fade {
  from {opacity: .4}
  to {opacity: 1}
}
</style>
<script>
let slideIndex = 1;
showSlides(slideIndex);

// Next/previous controls
function plusSlides(n) {
  showSlides(slideIndex += n);
}

// Thumbnail image controls
function currentSlide(n) {
  showSlides(slideIndex = n);
}

function showSlides(n) {
  let i;
  let slides = document.getElementsByClassName("mySlides");
  let dots = document.getElementsByClassName("dot");
  if (n > slides.length) {slideIndex = 1}
  if (n < 1) {slideIndex = slides.length}
  for (i = 0; i < slides.length; i++) {
    slides[i].style.display = "none";
  }
  for (i = 0; i < dots.length; i++) {
    dots[i].className = dots[i].className.replace(" active", "");
  }
  slides[slideIndex-1].style.display = "block";
  dots[slideIndex-1].className += " active";
}

</script>