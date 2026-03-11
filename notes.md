---
layout: page
title: 笔记
permalink: /notes/
---

如果你想先看一个更精简的总入口，可以先看 [文档页]({{ '/docs/' | relative_url }})。

> 学习机的 14 篇单天视频讲解没有在这里逐条平铺，统一收在[视频整理目录]({{ '/notes/xueersi-learning-machine-14-day-transcript/' | relative_url }})里。

{% assign grouped_notes = site.notes | where_exp: "note", "note.listed != false" | sort: "order" | group_by: "category" %}

{% for group in grouped_notes %}
## {{ group.name }}

{% for note in group.items %}
- [{{ note.title }}]({{ note.url | relative_url }})：{{ note.summary }}
{% endfor %}

{% endfor %}