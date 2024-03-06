---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
title: AZTEC Model Documentation
---

The Analyzer of Zero-emission Transportation Energy and Costs (AZTEC) model is an upgraded version of
the ICCT's first fleet-level total cost of ownership (TCO) tool, the Toolkit for Urban Bus Operations (TURBO).

TURBO was first developed in 2020 by Caleb Braun, Claire Buysse, and Josh Miller. 
AZTEC was first developed in 2022 by Gabe Hillman Alvarez, Erik Pronk, Josh Miller, and Arijit Sen.

## Versions

AZTEC is under continuing development. Documentation of all versions since v1.0 can be found here.

{% assign pages = site.pages | sort: "title" | reverse %}
{% for page in pages %}
{% if page.dir contains '/versions/' and page.title contains 'AZTEC v'%}
<li><a class="page-link" href="{{ page.url | relative_url }}">{{ page.title | escape }}</a></li>
{% endif %}
{% endfor %}
