---
layout: archive
title: "Posts by Year"
permalink: /year-archive/
entries_layout: list
---

{% assign groups = site.posts | group_by_exp: "p", "p.date | date: '%Y'" | sort: "name" | reverse %}
{% for y in groups %}
  <h2 id="{{ y.name }}">{{ y.name }}</h2>
  <div class="entries-list">
    {% for post in y.items %}
      {% include archive-single.html %}
    {% endfor %}
  </div>
{% endfor %}