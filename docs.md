---
layout: page
title: 文档
permalink: /docs/
---

这里集中展示站点内主要公开文档的入口。

{% assign notes = site.notes | where_exp: "note", "note.listed != false" | sort: "order" %}
{% assign grouped_notes = notes | group_by: "category" %}

## 快速入口

- [首页]({{ '/' | relative_url }})：查看站点总览
- [学而思学习机使用指南]({{ '/notes/xueersi-learning-machine-14-day-summary/' | relative_url }})：查看 14 天伴学的完整整理版
- [14 天伴学视频整理目录]({{ '/notes/xueersi-learning-machine-14-day-transcript/' | relative_url }})：按天查看学习机讲解
- [全部笔记]({{ '/notes/' | relative_url }})：按分类浏览全部公开笔记

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