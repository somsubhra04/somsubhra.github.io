---
layout: page
permalink: /courses
title: Coursework
description: A quick summary of the courses taken so far
nav: false
---

`My UG Learning Journey @ IITM`

**Year 1**
<!--
* 
* Mathematics for Data Science II (MA1003) - Prof Sarang Sane (Dept of Maths IITM)
* Statistics for Data Science II (MA1004) - Prof Andrew Thangaraj (Dept of EE IITM)
* Programming in Python (CS1002) - Prof Sudarshan Iyengar (HOD, CSE, IITR)
* English II (HS1002) - Prof Rajesh Kumar and Karthika Sathyanathan (Dept of Humanities and Social Sciences IITM)
* Mathematics for Data Science I (MA1001) - Prof Neelesh Upadhye (Dept of Maths IITM), Madhavan Mukund (CMI)
* Statistics for Data Science I (MA1002) - Prof Usha Mohan (Dept of Management Studies IITM)
* Computational Thinking (CS1001) - Prof Madhavan Mukund (CMI) and G Venkatesh (Dept of Humanities and Social Sciences IITM)
* English I (HS1001) - Prof Rajesh Kumar and Karthika Sathyanathan (Dept of Humanities and Social Sciences IITM)
-->
(Pls check this page later. This is under dev.)

{% assign courses = site.data.courses-ug-y1 %}
{% for course in courses %}
<div class="course">
  <li><a href="#{{ course.id }}" data-toggle="modal" style="color:black;text-decoration:none;">{{ course.title }}</a></li>
  <div id="{{ course.id }}" class="modal">
    <div class="modal-content">
      <span class="close">&times;</span>      
      <h2>{{ course.title }}</h2>
      <p>{{ course.description }}</p>
      <p>{{ course.faculty }}</p>
      <h3>Topics Covered:</h3>
      <ul>
        {% for topic in course.topics %}
        <li>{{ topic }}</li>
        {% endfor %}
      </ul>
    </div>
  </div>
</div>
{% endfor %}

`External Courses`

* Programming in C by IITK (NPTEL OC)


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
