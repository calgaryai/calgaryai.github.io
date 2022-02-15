---
layout: page
title: people
permalink: /people/
description: Faculty Members
nav: true
nav-order: 1
display_categories: [Computer Vision, Machine Learning, Applied Machine Learning, Medical Imaging]
horizontal: false
---

<!-- pages/people.md -->
<div class="people">
  {%- assign sorted_people = site.people | sort: "lastname" %}
<!-- Generate cards for each person -->

<h2 class="grid-title">Faculty</h2>

<div class="grid">
    {%- for person in sorted_people -%}
    {%- if person.show -%}
      {% include people.html %}
    {%- endif -%}
  {%- endfor %}
</div>

<h2 class="grid-title">Faculty by Research Area</h2>
<div class="grid">
  {%- for category in page.display_categories | sort: "category"  %}
    <div class="grid-item">
        <h3 class="card hoverable">
          <a href="#{{ category | downcase | remove: " "  }}"><span class="card-title">{{ category }}</span></a>
        </h3>
    </div>
  {%- endfor %}
</div>

<div class="people">
  <!-- Display categorized people -->
  {%- for category in page.display_categories | sort: "category"  %}
  <a name="{{ category | downcase | remove: " " }}"><h2 class="category">{{ category }}</h2></a>
  {%- assign categorized_people = site.people | where: "category", category -%}
  {%- assign sorted_people = categorized_people | sort: "lastname" %}
  <!-- Generate cards for each person -->
  <div class="grid">
    {%- for person in sorted_people -%}
      {%- if person.show -%}
        {% include people.html %}
      {%- endif -%}
    {%- endfor %}
  </div>
  {% endfor %}
</div>
