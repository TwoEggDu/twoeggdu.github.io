---
layout: page
title: 笔记
permalink: /notes/
---

{% assign grouped_notes = site.notes | sort: "order" | group_by: "category" %}

{% for group in grouped_notes %}
## {{ group.name }}

{% for note in group.items %}
- [{{ note.title }}]({{ note.url | relative_url }})：{{ note.summary }}
{% endfor %}

{% endfor %}