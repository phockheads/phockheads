---
layout: null
---
{% assign name = page.name | upcase | split: '.' %}{% assign filtered = site.series | where_exp: "item", "item.name == name[0]" %}{% for series in filtered %}{% assign item = series %}{% endfor %}{% raw %}{{% endraw %}
"success": true,
"asset": "{{ page.title }}",
"asset_issuer_address": "{{ page.address }}",
"asset_owner_address": "{{ page.address }}",
"asset_supply": "{{ page.supply }}",
"asset_divisible": {{ page.divisible }},
"asset_locked": {{ page.locked }},
"image": "{{ item.image }}",
"image_large": "{{ item.image }}",
"image_title": "{{ item.name }}",
"description": "<div style=\"padding-left:20px;\"><h2 style=\"font-family:monospace;font-size:14px;font-weight:bold;\">{{ item.name }}</h2><div><img src=\"{{ item.image }}\"></div><br><p style=\"font-family:monospace;font-size:12px;\">{{ item.description }}</p><div style=\"padding-right:184px;overflow: hidden;\">{% for subs in item.subs %}<div style=\"font-family:monospace;float: left; padding-right: 16px; padding-bottom: 16px;\"><img style=\"margin-right:4px;\" src=\"{{ subs.image }}\" width=\"46\"><br><a href=\"https://xchain.io/asset/{{ item.name }}.{{ subs.name }}\">{{ subs.name }}</a></div>{% endfor %}</div></div>",
"website": "https://phockheads.com/"
{% raw %}}{% endraw %}