---
layout: page
permalink: /courses
title: Coursework
description: A quick summary of the courses taken so far
nav: false
---

`My UG Learning Journey @ IITM`

**Sem 2**
* Mathematics for Data Science II (MA1003) - Prof Sarang Sane (Dept of Maths IITM)
* Statistics for Data Science II (MA1004) - Prof Andrew Thangaraj (Dept of EE IITM)
* Programming in Python (CS1002) - Prof Sudarshan Iyengar (HOD, CSE, IITR)
* English II (HS1002) - Prof Rajesh Kumar and Karthika Sathyanathan (Dept of Humanities and Social Sciences IITM)

**Sem 1**
* Mathematics for Data Science I (MA1001) - Prof Neelesh Upadhye (Dept of Maths IITM), Madhavan Mukund (CMI)
* Statistics for Data Science I (MA1002) - Prof Usha Mohan (Dept of Management Studies IITM)
* Computational Thinking (CS1001) - Prof Madhavan Mukund (CMI) and G Venkatesh (Dept of Humanities and Social Sciences IITM)
* English I (HS1001) - Prof Rajesh Kumar and Karthika Sathyanathan (Dept of Humanities and Social Sciences IITM)

`External Courses`

* Intro to Programming in C by IITK (NPTEL OC)


{% assign courses = site.data.courses %}
{% for course in courses %}
<div class="course">
  <a href="#{{ course.id }}" data-toggle="modal">{{ course.title }}</a>
  <div id="{{ course.id }}" class="modal">
    <div class="modal-content">
      <span class="close">&times;</span>
      <h2>{{ course.title }}</h2>
      <p>{{ course.description }}</p>
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
