---
layout: page
permalink: /publications/
title: publications
description: List of my publications in reversed chronological order. <i>(Last update 27/06/2022)</i>
years: [2022, 2021, 2020, 2019, 2018, 2017, 2016, 2014]
nav: true
nav_order: 2
---
<!-- _pages/publications.md -->
<div class="publications">

{%- for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f papers -q @*[year={{y}}]* %}
{% endfor %}

</div>
