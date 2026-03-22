---
layout: page
title: Algorithms
permalink: /algorithms/
---

{% assign grouped_docs = site.algorithms | group_by: "subclass" %}

{% for group in grouped_docs %}
  <h3>{{ group.name | default: "General" }}</h3>
  <ul>
    {% for item in group.items %}
      <li>
        <a href="{{ item.url }}">{{ item.title }}</a>
        {% if item.date %}
          <span class="post-meta">- {{ item.date | date: "%b %d, %Y" }}</span>
        {% endif %}
      </li>
    {% endfor %}
  </ul>
{% endfor %}