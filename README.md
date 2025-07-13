# ᕦʕ •ᴥ•ʔᕤ Hugo Black Bear

[![GitHub Pages](https://github.com/codertesla/hugo-black-bear/actions/workflows/gh-pages.yml/badge.svg)](https://github.com/codertesla/hugo-black-bear/actions/workflows/gh-pages.yml)
[![MIT license](https://img.shields.io/github/license/codertesla/hugo-black-bear)](https://github.com/codertesla/hugo-black-bear/blob/main/LICENSE)

## 概览

🐻 一款基于 [Bear Blog](https://bearblog.dev) 和 [Hugo Bear Blog](https://github.com/janraasch/hugo-bearblog) 的轻量级 [Hugo](https://gohugo.io/) 主题。

**Hugo Black Bear** 专注于速度与优化，让您可以心无旁骛地创作优质内容。它免费、开源、支持多语言、对搜索引擎友好、设计简洁、响应迅速，并且速度快如闪电。

此版本经过特别优化，尤其适合用于构建**知识库**、**技术文档**和**指南类网站**。

## 主要特性

- **极致性能**: Google PageSpeed 测试得分接近满分，页面加载体积仅约 5KB。
- **专业知识库皮肤**: 内置专为知识分享设计的 `knowledge-dark` 暗色主题。
- **全面的内容组件**: 提供信息块、可折叠内容、增强代码高亮、专业表格等。
- **高度可访问性**: 优化的色彩对比度，符合 WCAG 标准，并提供“跳至主内容”链接。
- **SEO 友好**: 自动生成 RSS 订阅、`robots.txt` 和 Open Graph / Twitter Cards 元数据。
- **安全纯净**: 无 JavaScript、无追踪脚本、无广告，并遵循严格的内容安全策略。
- **多语言支持**: 开箱即用的多语言模式配置。

![PageSpeed score](https://raw.githubusercontent.com/codertesla/hugo-black-bear/main/images/pagespeed.webp)

## 知识库功能展示

我们引入了全新的 `knowledge-dark` 皮肤和一系列组件，旨在提升文档的可读性和专业性。

### 1. 优化的信息块

使用样式优美的 `<blockquote>` 来突出显示重要信息、提示或警告。

> **提示**: `knowledge-dark` 皮肤为文档提供了卓越的排版和可读性。

### 2. 可折叠内容

对于冗长的内容，例如安装说明或配置代码，可以使用可折叠的 `details` 短代码，保持页面整洁。

```go-html-template
{{</* details "点击查看安装指南" */>}}
1. 克隆本仓库
2. 安装依赖 `npm install`
3. 运行开发服务器 `npm run dev`
{{</* /details */>}}
```

**效果:**
<details>
<summary>点击查看安装指南</summary>

1. 克隆本仓库
2. 安装依赖 `npm install`
3. 运行开发服务器 `npm run dev`

</details>

### 3. 增强的代码高亮

代码是技术文档的核心。本主题提供了清晰、易读的代码高亮方案。

```javascript
// 示例：从 API 获取数据
async function fetchUserData(userId) {
  try {
    const response = await fetch(`/api/users/${userId}`);
    if (!response.ok) {
      throw new Error('User not found');
    }
    return await response.json();
  } catch (error) {
    console.error('Error fetching user:', error);
  }
}
```

### 4. 专业的数据表格

使用经过精心设计的表格来清晰地呈现结构化数据。

| 功能 | 描述 | 状态 |
|---|---|---|
| 暗色主题 | 专业的暗色配色方案 | ✅ 已实现 |
| 内容目录 | 自动生成页面导航 | ✅ 已实现 |
| 折叠内容 | 组织长篇内容 | ✅ 已实现 |
| 信息块 | 高亮重要信息 | ✅ 已实现 |

## 安装

遵循 Hugo 的[快速入门](https://gohugo.io/getting-started/quick-start/)创建一个新站点，然后将本主题作为 [Git 子模块](https://git-scm.com/book/en/v2/Git-Tools-Submodules)克隆到 `themes` 目录下：

```sh
git submodule add https://github.com/codertesla/hugo-black-bear.git themes/hugo-black-bear
```

最后，将下面这行添加到你的站点配置文件 `hugo.toml` 中：

```sh
echo 'theme = "hugo-black-bear"' >> hugo.toml
```

## 配置

通过 `hugo.toml` 文件可以轻松自定义你的网站。以下是一个示例配置，更多信息请参考[示例站点配置](https://github.com/codertesla/hugo-black-bear/blob/main/exampleSite/hugo.toml)。

```toml
# 基础配置
baseURL = "https://example.com"
theme = "hugo-black-bear"
copyright = "John Doe (CC BY 4.0)"
defaultContentLanguage = "en"
enableRobotsTXT = true

# 语法高亮配置
[markup]
  [markup.highlight]
    lineNos = true
    lineNumbersInTable = false
    noClasses = false # 确保 hugo-black-bear 可以应用自定义的无障碍高亮主题

# 多语言模式配置
[languages]
  [languages.en]
    title = "My Knowledge Base"
    languageName = "en-US 🇺🇸"
    LanguageCode = "en-US"
    contentDir = "content"
    [languages.en.params]
      madeWith = "Made with [Hugo Black Bear](https://github.com/codertesla/hugo-black-bear)"

[params]
  # 网站描述
  description = "A knowledge base built with Hugo Black Bear"

  # Favicon 路径
  favicon = "images/favicon.png"

  # 社交媒体分享预览图
  images = ["images/share.webp"]

  # 日期格式
  dateFormat = "2006-01-02"

  # (重要) 主题皮肤选择
  # 可选项: "original", "herman", "knowledge-dark"
  # "knowledge-dark" 是为知识库优化的全新暗色皮肤
  themeStyle = "knowledge-dark"

  # (可选) 动态生成社交分享图
  # 如果文章没有在 front matter 中指定 `images`，将自动生成分享图
  generateSocialCard = true

  # 作者信息，用于 RSS 和文章页脚的 "Reply by email"
  [params.author]
    name = "Your Name"
    email = "your.email@example.com"
```

## 贡献

如果你在使用过程中遇到任何问题，欢迎提交 [Issue](https://github.com/codertesla/hugo-black-bear/issues) 或 [Pull Request](https://github.com/codertesla/hugo-black-bear/pulls)。
