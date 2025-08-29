---
layout: archive
title: "Tags"
permalink: /tags/
---

{% assign tags = site.tags | sort %}

<ul class="taxonomy__index">
  {% for tag in tags %}
    <li>
      <a href="#{{ tag[0] | slugify }}">
        <strong>{{ tag[0] }}</strong>
        <span class="taxonomy__count">{{ tag[1].size }}</span>
      </a>
    </li>
  {% endfor %}
</ul>

{% for tag in tags %}
  <section id="{{ tag[0] | slugify }}" class="taxonomy__section">
    <h2 class="archive__subtitle">{{ tag[0] }}</h2>
    <div class="entries-list">
      {% for post in tag[1] %}
        {% include archive-single.html %}
      {% endfor %}
    </div>
    <p><a href="#top">Back to top</a></p>
  </section>
{% endfor %}