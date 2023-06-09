---
layout: page
title: Gallery
permalink: /gallery
nav: false
---

<!-- pages/gallery.md -->
<div class="gallery">
  <figure>
    <img src="path/to/image1.jpg" alt="Image 1">
    <figcaption>Caption for Image 1</figcaption>
  </figure>
  
  <figure>
    <img src="path/to/image2.jpg" alt="Image 2">
    <figcaption>Caption for Image 2</figcaption>
  </figure>
  
  <!-- Add more image figures here -->
</div>

<style>
.gallery {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  grid-gap: 20px;
}

figure {
  margin: 0;
  text-align: center;
}

img {
  max-width: 100%;
  height: auto;
}
</style>
