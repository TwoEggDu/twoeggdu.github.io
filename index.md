---
layout: page
title: twoeggs
permalink: /
---

这是一个公开展示层，专门发布已经整理完成、适合对外展示的内容。

## 这里会放什么

- **笔记**：围绕书籍、行为模型和家庭教育主题整理的长文内容
- **项目**：面向外部展示的项目入口，例如 allweather
- **持续更新**：只发布经过筛选和提炼的公开内容

## 最近整理

{% assign notes = site.notes | sort: "order" %}
{% for note in notes limit: 3 %}
- [{{ note.title }}]({{ note.url | relative_url }})：{{ note.summary }}
{% endfor %}

## 入口

- [查看全部笔记]({{ '/notes/' | relative_url }})
- [查看项目页]({{ '/projects/' | relative_url }})
- [家庭的觉醒]({{ '/notes/family-awakening/' | relative_url }})
- [福格行为模型]({{ '/notes/fogg-behavior-model/' | relative_url }})

## 当前发布原则

- 原始图片、PDF、OCR 文本不直接公开
- 只同步允许公开的 Markdown 和静态资源
- 多个私有源仓库最终汇总到这个公开站点