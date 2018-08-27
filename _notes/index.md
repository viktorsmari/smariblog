---
permalink: /notes/
layout: page
title: Notes
---

{% for item in site.notes %}
  <p class="mb-0 mt-4">{{ item.date | date: "%b %-d, %Y" }}</p>
  <h2><a href="{{site.baseurl}}{{ item.url  }}">{{ item.title  }}</a></h2>
  <p>{{ item.tags | join: ', ' }}</p>
{% endfor %}


