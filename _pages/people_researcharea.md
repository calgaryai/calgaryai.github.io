---
layout: page
title: people
permalink: /people_researcharea/
description: Faculty Members by Research Area
nav: false
display_categories: [Computer Vision, Machine Learning, Applied Machine Learning, Medical Imaging]
---

<!-- pages/people.md -->
<div class="people">

{% include people_view_header.html %}

<h2 class="grid-title">Faculty by Research Area</h2>

{%- assign sorted_categories = page.display_categories | sort: "category"  %}
<div class="grid">
  {%- for category in sorted_categories -%}
    <div class="grid-item">
        <h3 class="card hoverable">
          <a href="#{{ category | downcase | remove: " "  }}"><span class="card-title">{{ category }}</span></a>
        </h3>
    </div>
  {%- endfor %}
</div>

<div class="people">
  <!-- Display categorized people -->
  {%- for category in sorted_categories  %}
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

</div>