---
title: Flow & Interaction Group
layout: default
permalink: /
---

# We are an independent research group exploring how accessibility, cognition, and interaction design intersect.

We use play, systems thinking, and user-centered design to investigate how blind people achieve cognitive flow—when fully immersed in work, games, or problem-solving—and how tools and environments can better support this state for everyone.

We envision a world where everyone has the opportunity for social and economic participation, ensuring that disabled individuals are included and benefit from personal and professional growth. To that end, we believe that accessibility should go beyond reducing barriers—it should create the conditions for clarity, agency, and joy. Our work aims to reframe the role of technology: not merely to be usable, but to enable intuitive, immersive, and empowering experiences that induce a sense of flow for everyone.

Our work is currently funded by [Project27 Consultancy Group C.I.C.](https://project27skills.com). We translate our research into impact through [Project27 Solutions](https://project27skills.com/solutions/index.html).

## Research Themes

Though the specifics of our work continue to evolve, everything we do is in pursuit of a central research enquiry: How do blind people achieve cognitive flow through tools, systems, and play—and how can accessibility design foster flow in ways that work for both blind and sighted users?

{% assign themes = site.themes | sort: "order" %}
<div class="grid grid-2">
{% for t in themes %}
  {% assign theme_key = t.slug | default: t.title | slugify %}
  <div>
    <h3><a href="{{ t.url | relative_url }}">{{ t.title }}</a></h3>

    {% assign has_content = t.content | strip | size %}
    {% if has_content > 0 %}
      {{ t.excerpt | markdownify }}
    {% else %}
      {{ t.description | markdownify }}
    {% endif %}

    {%- comment -%}
      Build a list of matching publications manually to avoid where_exp edge cases.
      We slugify the joined tag string so hyphens/case/spacing never break the match.
    {%- endcomment -%}
    {% assign theme_pubs = "" | split: "" %}
    {% for p in site.publications %}
      {% assign tagbag = p.tags | default: empty | join: " " | slugify %}
      {% if tagbag contains theme_key %}
        {% assign theme_pubs = theme_pubs | push: p %}
      {% endif %}
    {% endfor %}

    {% assign theme_pubs = theme_pubs | sort: "year" | reverse | slice: 0, 2 %}
    {% if theme_pubs.size > 0 %}
      <h4>Selected publications</h4>
      <ul class="list-unstyled">
        {% for p in theme_pubs %}
          <li>
            <a href="{{ p.url | relative_url }}">{{ p.title }}
            {% if p.year %} ({{ p.year }}){% endif %}</a>
          </li>
        {% endfor %}
      </ul>
    {% endif %}
  </div>
{% endfor %}
</div>

{% comment %}
{% assign themes = site.themes | sort: "order" %}
<div class="grid grid-2">
{% for t in themes %}
<div>
  <h3><a href="{{ t.url | relative_url }}">{{ t.title }}</a></h3>
  {{ t.excerpt | default: t.description | markdownify }}
  {% comment %} Selected publications: two most recent tagged with the theme slug {% endcomment %}
  {% assign theme_pubs = site.publications | where_exp: 'p', 'p.tags contains t.slug' | sort: "year" | reverse | slice: 0, 2 %}
  {% if theme_pubs and theme_pubs.size > 0 %}
  <h4>Selected publications</h4>
  <ul class="list-unstyled">
    {% for p in theme_pubs %}
      <li><a href="{{ p.url | relative_url }}">{{ p.title }}</a> ({{ p.year }})</li>
    {% endfor %}
  </ul>
  {% endif %}
</div>
{% endfor %}
</div>
{% endcomment %}

## News

{% assign news_posts = site.posts | where_exp: 'post', 'post.tags contains "news"' | slice: 0, 5 %}
{% if news_posts.size > 0 %}
<ul>
  {% for post in news_posts %}
    <li>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      <span aria-hidden="true">·</span>
      <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%b %-d, %Y" }}</time>
    </li>
  {% endfor %}
</ul>
{% else %}
<p>No news posts yet.</p>
{% endif %}
