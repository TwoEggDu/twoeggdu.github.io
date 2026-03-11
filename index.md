---
layout: page
title: twoeggs
permalink: /
---

这是一个公开展示层，专门发布已经整理完成、适合对外展示的内容。

## 这里会放什么？

- **笔记**：围绕书籍、行为模型和家庭教育主题整理的长文内容
- **项目**：面向外部展示的项目入口，例如 allweather
- **持续更新**：只发布经过筛选和提炼的公开内容

## 最近整理

{% assign notes = site.notes | sort: "order" %}
{% for note in notes limit: 4 %}
- [{{ note.title }}]({{ note.url | relative_url }})：{{ note.summary }}
{% endfor %}

## 学习机指南

- [学而思学习机使用指南]({{ '/notes/xueersi-learning-machine-14-day-summary/' | relative_url }})：按 14 天伴学聊天整理的功能入口、缺失天数和原始链接汇总

## 心理专题

- [NPD 是什么？它会怎样影响家人和孩子]({{ '/notes/npd-guide/' | relative_url }})：了解自恋型人格障碍的核心特征、家庭影响、孩子风险与识别方法。

## 入口

- [查看文档入口页]({{ '/docs/' | relative_url }})
- [查看全部笔记]({{ '/notes/' | relative_url }})
- [查看项目页]({{ '/projects/' | relative_url }})

## 笔记分类

{% assign grouped_notes = site.notes | sort: "order" | group_by: "category" %}
{% for group in grouped_notes %}
### {{ group.name }}

{% for note in group.items %}
- [{{ note.title }}]({{ note.url | relative_url }})
{% endfor %}

{% endfor %}

## 当前发布原则

- 原始图片、PDF、OCR 文本不直接公开
- 只同步允许公开的 Markdown 和静态资源
- 多个私有源仓库最终汇总到这个公开站点
