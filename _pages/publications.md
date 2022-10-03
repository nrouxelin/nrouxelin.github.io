---
layout: page
permalink: /publications/
title: publications
description: A list of my publications
years_talks: [2022, 2021, 2019]
years_preprints: [2021]
years_articles: [2022]
years_posters: [2021, 2018]
nav: true
---
<div class="publications">
<h2> articles </h2>

{% for y in page.years_articles %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f papers -q @article[year={{y}}] %}
{% endfor %}


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

<h2> posters </h2>

{% for y in page.years_posters %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f papers -q @conference[year={{y}}] %}
{% endfor %}
</div>
