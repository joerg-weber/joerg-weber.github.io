---
layout: page
permalink: /teaching/
title: teaching
description: 
nav: true
nav_order: 3
display_categories: [current, past, supervision, upskilling]
---

<div class="projects">
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_teaching = site.teaching | where: "category", category %}
  {% assign sorted_teaching = categorized_teaching | sort: "number" | reverse %}
  <!-- Generate cards for each course -->
  <div class="row row-cols-1 row-cols-md-1">
    {% for teaching in sorted_teaching %}
      {% include teaching.liquid %}
    {% endfor %}
  </div>
  {% endfor %}
</div>           
