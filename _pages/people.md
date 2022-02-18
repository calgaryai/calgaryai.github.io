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

<div class="people">
  <!-- <ul class="nav nav-tabs justify-content-end" id="peopleviewselect">
    <li class="nav-item">
      <a href="#lastname" class="nav-link active" data-toggle="tab" data-target="#lastname" role="tab" aria-controls="lastname" aria-selected="true">Alphabetically</a>
    </li>
    <li class="nav-item">
      <a href="#researcharea" class="nav-link" data-toggle="tab" data-target="#researcharea" role="tab" aria-controls="researcharea" aria-selected="false">Research Area</a>
    </li>
    <li class="nav-item">
      <a href="#affiliation" class="nav-link" data-toggle="tab" data-target="#affiliation" role="tab" aria-controls="affiliation" aria-selected="false">Affiliation</a>
    </li>
  </ul> -->
  <!-- <div class="tab-content">
    <div class="tab-pane fade masonry-container show active" id="lastname"> -->
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
    <!-- </div>
    <div class="tab-pane fade masonry-container" id="researcharea"> -->
      <h2 class="grid-title">Faculty by Research Area</h2>
      {% include people_categories.html categories=page.research_categories %}
    <!-- </div>
    <div class="tab-pane fade masonry-container" id="affiliation"> -->
      <h2 class="grid-title">Faculty by Affiliation</h2>
      {% include people_categories.html categories=page.affiliations %}
    <!-- </div> -->
  <!-- </div> -->
</div>

{% include scripts/jquery.html %}
<script defer>
$("#researcharea").toggleClass('active');
$("#affiliation").toggleClass('active');
$("#researcharea").toggleClass('show');
$("#affiliation").toggleClass('show');
</script>
<!-- {% include scripts/jquery.html %}
{% include scripts/bootstrap.html %}
{% include scripts/masonry.html %}
<script type="text/javascript">
var $container = $('.grid div');
console.log($container)
$container.imagesLoaded( function () {
  $container.masonry({
    columnWidth: '.grid-item',
    itemSelector: '.grid-item'
  });
});

$('a[data-toggle=tab]').each(function () {
  var $this = $(this);

  $this.on('shown.bs.tab', function () {
    console.log('tab shown');
    $container.imagesLoaded( function () {
      $container.masonry({
        columnWidth: '.grid-item',
        itemSelector: '.grid-item'
      });
    });

  }); //end shown
});  //end each
</script> -->