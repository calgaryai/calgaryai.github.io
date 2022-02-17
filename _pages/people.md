---
layout: page
title: people
permalink: /people/
description: Faculty Members
nav: true
nav-order: 1
research_categories: [Computer Vision, Machine Learning, Applied Machine Learning, Medical Imaging]
affiliations: [Dept. of Electrical and Software Engineering, Dep. of Biomedical Engineering, Dept. of Geomatics Engineering, Hotchkiss Brain Institute]
---

<!-- pages/people.md -->
<script src="http://ajax.googleapis.com/ajax/libs/jquery/1.9.1/jquery.min.js"></script>
<!-- <script defer>
$("#researcharea").toggleClass('active');
$("#affiliation").toggleClass('active');
$("#researcharea").toggleClass('show');
$("#affiliation").toggleClass('show');
</script> -->
<script type="text/javascript">
$('#peopleviewselect li').click(function (e)
{
  $("[id^='tab']").hide();
  e.preventDefault()
  var ids=$(this).data('tab');
  $("#"+ids).show();
  $('.grid').masonry({
        itemSelector: '.grid-item'
  });
 })
</script>
<div class="people container">
  <ul class="nav nav-pills justify-content-end" id="peopleviewselect">
    <li class="nav-item">
      <a href="#tab-1" class="nav-link active" data-toggle="pill">Alphabetically</a>
    </li>
    <li class="nav-item">
      <a href="#tab-2" class="nav-link" data-toggle="pill">Research Area</a>
    </li>
    <li class="nav-item">
      <a href="#tab-3" class="nav-link" data-toggle="pill">Affiliation</a>
    </li>
  </ul>
  <div class="tab-content">
    <div class="tab-pane fade in show active" id="tab-1">
      <h2 class="grid-title">Faculty Alphabetically by Last Name</h2>
      {%- assign sorted_people = site.people | sort: "lastname" %}
      <!-- Generate cards for each person -->
      <div class="grid">
        {%- for person in sorted_people -%}
          {%- if person.show -%}
            {% include people.html %}
          {%- endif -%}
        {%- endfor %}
      </div>
    </div>
    <div class="tab-pane fade in" id="tab-2">
      <h2 class="grid-title">Faculty by Research Area</h2>
      {% include people_categories.html categories=page.research_categories %}
    </div>
    <div class="tab-pane fade in" id="tab-3">
      <h2 class="grid-title">Faculty by Affiliation</h2>
      {% include people_categories.html categories=page.affiliations %}
    </div>
  </div>
</div>
