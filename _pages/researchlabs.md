---
layout: page
title: researchlabs
permalink: /researchlabs/
description: Affiliated Research Labs
nav: true
nav-order: 5
display_categories: [Dept. Geomatics Engineering, Dept. Electrical & Software Engineering, Dept. Biomedical Engineering]
horizontal: false
---

<div class="labs">
{%- if site.enable_place_categories and page.display_categories %}
  <!-- Display categorized labs -->
  {%- for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {%- assign categorized_labs = site.labs | where: "category", category -%}
  {%- assign sorted_labs = categorized_labs | sort: "importance" %}
  <!-- Generate cards for each project -->
  <div class="grid">
    {%- for labs in sorted_labs -%}
      {% include lab.html %}
    {%- endfor %}
  </div>
  {% endfor %}

{%- else -%}
<!-- Display labs without categories -->
  {%- assign sorted_labs = site.labs | sort: "importance" -%}
  <!-- Generate cards for each project -->
  <div class="grid">
    {%- for labs in sorted_labs -%}
      {% include lab.html %}
    {%- endfor %}
  </div>
{%- endif -%}
</div>