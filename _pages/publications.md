---
layout: page
permalink: /publications/
title: publications
description: A list of my publications
years_talks: [2021, 2019]
years_preprints: [2021]
nav: true
---
<div class="publications">
<h2> pre-prints </h2>

{% for y in page.years_preprints %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f papers -q @unpublished[year={{y}}] %}
{% endfor %}


<h2> talks </h2>

{% for y in page.years_talks %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f papers -q @inproceedings[year={{y}}] %}
{% endfor %}

</div>
