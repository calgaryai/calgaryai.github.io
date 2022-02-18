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

  <h2 class="grid-title">Faculty by Research Area</h2>
  {% include people_categories.html categories=page.research_categories %}

  <h2 class="grid-title">Faculty by Affiliation</h2>
  {% include people_categories.html categories=page.affiliations %}
</div>