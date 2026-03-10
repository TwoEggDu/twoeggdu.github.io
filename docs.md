---
layout: page
title: 文档
permalink: /docs/
---

这里集中展示站点内所有公开文档的入口，适合作为统一浏览页。

{% assign notes = site.notes | sort: "order" %}
{% assign grouped_notes = notes | group_by: "category" %}

## 快速入口

- [首页]({{ '/' | relative_url }})：查看站点总览
- [全部笔记]({{ '/notes/' | relative_url }})：按分类浏览全部公开笔记
- [项目页]({{ '/projects/' | relative_url }})：查看对外展示的项目入口

## 当前收录

- 公开笔记：{{ notes | size }} 篇
- 内容分类：{{ grouped_notes | size }} 个

## 按分类浏览

{% for group in grouped_notes %}
### {{ group.name }}（{{ group.items | size }}）

{% for note in group.items %}
- [{{ note.title }}]({{ note.url | relative_url }})：{{ note.summary }}
{% endfor %}

{% endfor %}
