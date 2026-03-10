---
layout: page
title: 笔记
permalink: /notes/
---

如果你想从一个页面查看全部公开内容的入口，可以先看 [文档页]({{ '/docs/' | relative_url }})。

{% assign grouped_notes = site.notes | sort: "order" | group_by: "category" %}

{% for group in grouped_notes %}
## {{ group.name }}

{% for note in group.items %}
- [{{ note.title }}]({{ note.url | relative_url }})：{{ note.summary }}
{% endfor %}

{% endfor %}
