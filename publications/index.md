---
title: Publications
layout: default
---

# Publications

Browse our publications, groupped by year of publishing.

{% assign pubs_by_year = site.publications | group_by: "year" | sort: "name" | reverse %}
{% for g in pubs_by_year %}
<h2 class="sec-h sec-h--lg">{{ g.name }}</h2>
<ul class="pub-list">
  {% for p in g.items %}
    {% include pub-card.html p=p show_links=true %}
  {% endfor %}
</ul>
{% endfor %}
