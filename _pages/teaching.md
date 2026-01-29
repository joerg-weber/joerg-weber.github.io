---
layout: page
permalink: /teaching/
title: teaching
description:
nav: true
nav_order: 3
display_categories: [current, past, supervision, training]
---

<div class="projects">
  {% for category in page.display_categories %}
  {% assign categorized_teaching = site.data.teaching | where: "category", category %}
  {% if categorized_teaching.size > 0 %}
    <a id="{{ category }}" href=".#{{ category }}">
     <h2 class="category">{{ category }}</h2>
    </a>
    {% assign sorted_teaching = categorized_teaching | sort: "number" | reverse %}
    <!-- Generate cards for each course -->
    <div class="row row-cols-1 row-cols-md-1">
      {% for teaching in sorted_teaching %}
        {% include teaching.liquid %}
      {% endfor %}
    </div>
  {% endif %}
  {% endfor %}
</div>
