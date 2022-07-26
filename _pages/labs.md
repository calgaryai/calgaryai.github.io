---
layout: page
title: research labs
permalink: /labs/
description: Calgary AI Research Labs
nav: true
nav-order: 2
display_categories: [Geomatics Engineering, Electrical and Software Engineering, Biomedical Engineering]
---

<div class="labs">
{%- if site.enable_lab_categories and page.display_categories %}
  <!-- Display categorized labs -->
  {%- assign sorted_categories = page.display_categories | sort %}
  {%- for category in sorted_categories %}
    <h2 class="category">{{ category }}</h2>
    {%- assign categorized_labs = site.labs | where: "category", category -%}
    {%- assign sorted_labs = categorized_labs | sort: "name" %}
    <!-- Generate cards for each project -->
    <div class="grid">
      {%- for lab in sorted_labs -%}
        {% include labs.html %}
      {%- endfor %}
    </div>
  {% endfor %}

{%- else -%}
<!-- Display labs without categories -->
  {%- assign sorted_labs = site.labs | sort: "name" -%}
  <!-- Generate cards for each project -->
  <div class="grid">
    {%- for lab in sorted_labs -%}
      {% include labs.html %}
    {%- endfor %}
  </div>
{%- endif -%}

  <!-- Generate cards for each project -->
  <div class="grid">
    {%- for labs in site.labs -%}
      {% include labs.html %}
    {%- endfor %}
  </div>
</div>
