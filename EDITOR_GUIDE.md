# 编辑手册

这份文档给日常负责内容编辑的同事使用，目标是用最少的技术门槛完成两件事：

1. 编辑或新增站内文章
2. 把修改发布到公开站点

站点地址：[https://twoeggdu.github.io/](https://twoeggdu.github.io/)

## 先了解这个站的结构

这个站是一个基于 Jekyll 的 GitHub Pages 静态站，常用目录如下：

- `_notes/`：站内文章，发布后会出现在 `/notes/` 列表页
- `assets/images/`：公开图片
- `assets/files/`：公开附件，建议放 PDF 等可下载文件
- `index.md`：首页
- `docs.md`：文档入口页
- `notes.md`：文章列表页
- `projects.md`：项目页

对编辑来说，最常做的是修改 `_notes/` 和 `assets/`。

## 新增一篇文章

### 1. 新建文章文件

在 `_notes/` 目录下新建一个 Markdown 文件：

```text
_notes/your-article-slug.md
```

文件名决定文章地址，建议使用：

- 小写英文
- 单词之间用 `-` 连接
- 不要用空格
- 不要直接用中文文件名

例如：

```text
_notes/family-awakening.md
_notes/fogg-behavior-model.md
_notes/education-stages.md
```

对应网址会是：

```text
https://twoeggdu.github.io/notes/family-awakening/
```

### 2. 复制下面这个模板

```markdown
---
title: 文章标题
category: 分类名称
summary: 一句话摘要，建议 20-50 字
order: 4
---

> 文章导语，可选。

## 一、一级内容标题

正文内容。

## 二、第二部分

- 要点 1
- 要点 2
- 要点 3
```

### 3. 头部字段怎么写

- `title`：文章标题，页面上会直接显示
- `category`：分类名称，会影响 `/notes/` 页的分组
- `summary`：列表页和首页摘要
- `order`：排序值，数字越小越靠前

建议：

- 新文章的 `order` 不要和现有文章重复
- 如果只是普通文章，不需要写 `layout`，仓库已经默认配置好了

## 排版规范

这个站支持标准 Markdown，优先使用简单、稳定的写法。

### 标题

```markdown
## 二级标题
### 三级标题
```

建议：

- 一篇文章正文从 `##` 开始即可
- 不要跳级太多
- 标题尽量短，方便目录式阅读

### 段落与强调

```markdown
这是普通段落。

**这是加粗**

`这是行内重点`
```

建议：

- 一段只讲一个意思
- 少量加粗，不要整段加粗
- 行内代码样式可用于术语、路径、命令或变量名

### 列表

无序列表：

```markdown
- 要点 1
- 要点 2
- 要点 3
```

有序列表：

```markdown
1. 第一步
2. 第二步
3. 第三步
```

### 引用

```markdown
> 这是引用内容。
```

适合放：

- 金句
- 原书摘录
- 一句话总结

### 表格

```markdown
| 项目 | 说明 |
| --- | --- |
| 标题 | 文章标题 |
| 摘要 | 列表页显示 |
```

表格适合做对比、清单、参数说明。内容太长时，优先改成列表。

### 分隔代码或命令

如果要展示命令或代码，用代码块：

````markdown
```bash
git add .
git commit -m "add note"
git push origin main
```
````

## 图片怎么放

### 推荐目录

建议按文章单独建目录：

```text
assets/images/notes/文章slug/
```

例如：

```text
assets/images/notes/family-awakening/mindmap.jpg
assets/images/notes/fogg-behavior-model/cover.png
```

### 推荐命名

建议图片文件名也使用英文和 `-`：

- `cover.jpg`
- `mindmap.jpg`
- `quote-card-01.png`

不要使用：

- `图片1.jpg`
- `最终版(改2).png`
- 带空格的文件名

### 在文章里引用图片

推荐写法：

```markdown
![家庭的觉醒思维导图]({{ '/assets/images/notes/family-awakening/mindmap.jpg' | relative_url }})
```

说明：

- `[]` 里写图片说明文字
- `()` 里写图片路径
- `relative_url` 是 Jekyll 的安全写法，后续即使站点路径调整，也更稳

如果想让图片下面有一句说明，可以这样写：

```markdown
![家庭的觉醒思维导图]({{ '/assets/images/notes/family-awakening/mindmap.jpg' | relative_url }})

*图：家庭的觉醒思维导图*
```

### 图片使用建议

- 优先使用压缩后的公开版图片
- 原始大图、截图原件、OCR 过程文件不要放到公开站
- 尽量保证文件清晰，但不要过大

## 文档和附件怎么引用

### 推荐目录

公开附件建议放在：

```text
assets/files/notes/文章slug/
```

例如：

```text
assets/files/notes/family-awakening/source.pdf
```

### 在文章中引用 PDF 或附件

```markdown
[下载 PDF]({{ '/assets/files/notes/family-awakening/source.pdf' | relative_url }})
```

也可以加说明文字：

```markdown
如需查看原始公开版资料，可点击：[下载 PDF]({{ '/assets/files/notes/family-awakening/source.pdf' | relative_url }})
```

建议只上传：

- 确认可以公开的 PDF
- 读者确实需要下载的附件

不要上传：

- 原始扫描件
- 含个人信息的材料
- 仅内部使用的工作文档

## 怎么引用站内其他文章

如果要在一篇文章里链接到另一篇文章，推荐写法：

```markdown
[查看《家庭的觉醒》]({{ '/notes/family-awakening/' | relative_url }})
```

如果要链接到首页、文档页、笔记页、项目页：

```markdown
[返回首页]({{ '/' | relative_url }})
[查看文档页]({{ '/docs/' | relative_url }})
[查看全部笔记]({{ '/notes/' | relative_url }})
[查看项目页]({{ '/projects/' | relative_url }})
```

## 编辑时的内容边界

这个仓库是公开站点仓库，只放允许对外展示的内容。

可以放：

- 整理完成的 Markdown 文章
- 已确认可公开的图片
- 已确认可公开的 PDF 或附件

不要放：

- 原始截图
- OCR 中间稿
- 私密笔记
- 包含个人隐私或版权风险的附件

如果某个素材不确定能不能公开，先不要上传。

## 发布方式

这个站当前使用 GitHub Pages，从 `main` 分支发布。

对编辑来说，最简单的是以下两种方式。

### 方式一：直接在 GitHub 网页上编辑

适合轻量修改。

1. 打开仓库：[TwoEggDu/twoeggdu.github.io](https://github.com/TwoEggDu/twoeggdu.github.io)
2. 找到要修改的文件
3. 点击编辑
4. 修改内容或上传文件
5. 直接提交到 `main` 分支

提交后，GitHub Pages 会自动发布，通常几分钟内生效。

### 方式二：本地修改后提交

适合批量改动或需要同时上传多张图片、多份附件。

常用命令如下：

```bash
git add .
git commit -m "update note"
git push origin main
```

推送到 `main` 后，站点会自动发布。

## 发布前检查清单

发布前至少检查以下几项：

1. 文章头部字段是否完整
2. 标题和摘要有没有明显错别字
3. 图片路径是否正确
4. PDF 或附件链接是否能打开
5. 是否误传了不该公开的素材
6. 新文章是否能在 `/notes/` 页面看到

## 发布后怎么验收

发布后检查：

1. 首页：[https://twoeggdu.github.io/](https://twoeggdu.github.io/)
2. 文档页：[https://twoeggdu.github.io/docs/](https://twoeggdu.github.io/docs/)
3. 笔记页：[https://twoeggdu.github.io/notes/](https://twoeggdu.github.io/notes/)
4. 对应文章页，例如：
   `https://twoeggdu.github.io/notes/family-awakening/`

如果刚提交完还没更新，先等 1 到 5 分钟再刷新。

## 常见问题

### 为什么文章没有出现在列表里？

优先检查：

- 文件是不是放在 `_notes/` 下
- 文件头部有没有 `title`、`category`、`summary`、`order`
- 文件是不是 `.md`

### 为什么文章地址不对？

文章地址由文件名决定，不是由标题决定。

例如：

- 文件名是 `family-awakening.md`
- 地址就是 `/notes/family-awakening/`

### 为什么图片不显示？

优先检查：

- 图片文件是否真的上传了
- 路径大小写是否一致
- 路径是否从 `/assets/...` 开始
- 文件名里是否有空格或中文符号

## 最简工作流

如果只记住最少步骤，按下面做就够了：

1. 在 `_notes/` 新建或修改文章
2. 把图片放到 `assets/images/notes/文章slug/`
3. 把附件放到 `assets/files/notes/文章slug/`
4. 在文章里用 Markdown 链接引用它们
5. 提交到 `main`
6. 打开线上页面检查是否正常


