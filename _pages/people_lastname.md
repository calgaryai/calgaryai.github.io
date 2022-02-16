---
layout: page
title: people
permalink: /people_lastname/
description: Faculty Members
nav: true
nav-order: 1
---

<!-- pages/people.md -->
<div class="people">

{% include people_view_header.html %}

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
