---
layout: archive
title: "Selected publications"
permalink: /publications/
author_profile: true
---

{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}

{% include base_path %}

<div class="publication-list">
  {% assign ordered_publications = site.publications | sort: "display_order" %}
  {% for post in ordered_publications %}
    {% include publication-card.html %}
  {% endfor %}
</div>
