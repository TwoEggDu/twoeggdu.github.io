# AGENTS.md

## Repo Purpose

这是公开 GitHub Pages 站点仓库，只放允许公开的内容。

- 公开文章放在 `_notes/`
- 首页和入口页是 `index.md`、`docs.md`、`notes.md`、`projects.md`
- 发布方式是推送到 `main` 分支

## Public Content Boundary

可以放：

- 整理完成的 Markdown 文章
- 已确认可公开的图片和附件

不要放：

- 原始截图
- OCR 中间稿
- 含隐私或版权风险的素材

## Critical Encoding Rule

这个仓库里的 Jekyll 文件必须使用 `UTF-8 without BOM`。

重点包括：

- `_notes/*.md`
- `index.md`
- `docs.md`
- `notes.md`
- `projects.md`
- `_config.yml`

如果这些文件带了 `BOM`，GitHub Pages / Jekyll 可能无法正确识别 front matter，常见表现包括：

- 新文章页面 `404`
- 首页或文档页的新入口不显示
- 页面没有按预期生成

## Windows / PowerShell Caveat

在 Windows 下，不要默认假设 `Set-Content -Encoding utf8` 一定安全。写入后必须确认文件仍然是 `UTF-8 without BOM`。

更稳的写法：

```powershell
$enc = New-Object System.Text.UTF8Encoding($false)
$text = [System.IO.File]::ReadAllText("path-to-file.md")
[System.IO.File]::WriteAllText("path-to-file.md", $text, $enc)
```

## Verification

如果怀疑 BOM 问题，可以检查文件前 4 个字节。正常 front matter 文件应该直接以 `---` 开头，也就是类似：

- `45 45 45 10`
- 或 `45 45 45 13`

如果前面出现 `239 187 191`，那就是 BOM，需要去掉。

## Release Checklist

1. front matter 是否完整
2. 文件编码是否为 `UTF-8 without BOM`
3. 推送到 `main` 后线上页面是否可访问
4. 如果新页面是 `404`，先查 BOM，再查路由或链接