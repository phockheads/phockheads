---
layout: home
title: Home
exclude: true
---

<ul class="assets">
{% for series in site.series %}
{% assign artist = site.artists | where_exp: 'item', "item.title == series.author" %}
  <li>
    <img src="{% if series.image != null and series.image != '' %}{{ series.image }}{% else %}{{'assets/placeholder.png' | relative_url}}{% endif %}">
    <a href="series/{{ series.name | downcase }}">
      <b>{{ series.name }}</b>
    </a>
    <p class="small">Artist: {% if artist[0] %}<a href="{{ artist[0].url | relative_url }}">{{ series.author }}</a>{% else %}{{ series.author }}{% endif %}</p>
  </li>
{% endfor %}
</ul>