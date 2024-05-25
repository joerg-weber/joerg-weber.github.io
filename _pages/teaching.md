---
layout: page
permalink: /teaching/
title: teaching
description: 
nav: true
nav_order: 3
display_categories: [current, past]
---

<div class="projects">
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_teaching = site.teaching | where: "category", category %}
  {% assign sorted_teaching = categorized_teaching %}
  <!-- Generate cards for each project -->
  <div class="row row-cols-1 row-cols-md-3">
    {% for teaching in sorted_teaching %}
      {% include teaching.liquid %}
    {% endfor %}
  </div>
  {% endfor %}
</div>

<a id="current teaching" href=".#current teaching"></a>

<h2 class="category">current teaching</h2>
<div class="container">
    <div class="row row-cols-1 row-cols-md-2">
        <div class="card-item col">
                           <div class="card-body">
                            <h5 class="card-title">Linear and Combinatorial Optimization</h5>
                            <p class="card-text">Lecturer (Lund, Spring Term 2024) </p>
                            <div class="row ml-1 mr-1 p-0">
                        </div>
                    </div>
                </div>              
