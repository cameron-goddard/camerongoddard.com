---
layout: page
title: Projects
permalink: /projects/
description: Just some things I've worked on, nonexhaustive
nav: true
nav_order: 1
display_categories: [Personal, School]
horizontal: false
---
*This page is a work-in-progress*
<div class="projects">
  <!-- Display categorized projects -->
  {%- for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {%- assign categorized_projects = site.projects | where: "category", category -%}
  {%- assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  <div class="grid">
    {%- for project in sorted_projects -%}
      {% include projects.html %}
    {%- endfor %}
  </div>
  {% endfor %}
</div>