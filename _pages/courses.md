---
layout: page
permalink: /courses
title: Coursework
description: A quick summary of the courses taken so far
nav: false
---

`My UG Learning Journey @ IITM`

**Year 1 (Updated till sem 2)**

{% assign courses = site.data.courses-ug-y1 %}
{% for course in courses %}
<div class="course">
  <li><a href="#{{ course.id }}" data-toggle="modal" style="color:black;text-decoration:none;">{{ course.title }}</a></li>
  <div id="{{ course.id }}" class="modal">
    <div class="modal-content">
      <h2>{{ course.title }}</h2>
      <p>{{ course.description }}</p>
      <p>Faculty: {{ course.faculty }}</p>
      <h3>Topics Learnt:</h3>
      <ul>
        {% for topic in course.topics %}
        <li>{{ topic }}</li>
        {% endfor %}
      </ul>
    </div>
  </div>
</div>
{% endfor %}
<br>
`External Courses`

<li>Programming in C by IITK (NPTEL OC)</li>


<style>
.modal {
  display: none;
  position: fixed;
  z-index: 1;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  overflow: auto;
  background-color: rgba(0, 0, 0, 0.8);
}

.modal-content {
  background-color: #fefefe;
  margin: 10% auto;
  padding: 20px;
  border: 1px solid #888;
  width: 80%;
  max-width: 800px;
  border-radius: 5px;
}

@media only screen and (max-width: 768px) {
  .modal-content {
    margin: 15% auto;
    padding: 10px;
    width: 90%;
  }
}

.close {
  color: #aaa;
  float: right;
  font-size: 28px;
  font-weight: bold;
}

.close:hover,
.close:focus {
  color: #000;
  text-decoration: none;
  cursor: pointer;
}

.modal-backdrop {
  position: fixed;
  top: 0;
  left: 0;
  height: 100%;
  width: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  z-index: -1;
  pointer-events: none; /* Add this property */
}
</style>


<script>
var modals = document.querySelectorAll('.modal');
var links = document.querySelectorAll('[data-toggle="modal"]');
var closers = document.querySelectorAll('.close');

for (var i = 0; i < links.length; i++) {
  links[i].addEventListener('click', function(e) {
    e.preventDefault();
    var target = this.getAttribute('href');
    document.querySelector(target).style.display = 'block';
  });
}

for (var i = 0; i < closers.length; i++) {
  closers[i].addEventListener('click', function() {
    var modal = this.parentNode.parentNode;
    modal.style.display = 'none';
  });
}
</script>
