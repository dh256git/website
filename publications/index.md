---
title: Publications
layout: default
---

# Publications

{% assign pubs_by_year = site.publications | group_by: "year" | sort: "name" | reverse %}
{% for g in pubs_by_year %}
## {{ g.name }}
<ul class="pub-list">
  {% for p in g.items %}
    {% include pub-card.html p=p show_links=true %}
  {% endfor %}
</ul>
{% endfor %}
