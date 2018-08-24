---
permalink: /notes/
layout: page
---

## Notes

{% for item in site.notes %}
<h2>{{ item.title  }}</h2>
<p>{{ item.description  }}</p>
<p><a href="{{ item.url  }}">{{ item.title  }}</a></p>
{% endfor %}


