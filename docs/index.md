---
layout: home
title: Home
exclude: true
---

<ul class="assets">
{% for series in site.series %}
  <li>
    <img src="{% if series.image != null and series.image != '' %}{{ series.image }}{% else %}{{'assets/placeholder.png' | relative_url}}{% endif %}">
    <a href="series/{{ series.name | downcase }}">
      <b>{{ series.name }}</b>
    </a>
    <p class="small">Artist: {{ series.author }}</p>
  </li>
{% endfor %}
</ul>