English | [简体中文](README.zh-CN.md)
***

# ᕦʕ •ᴥ•ʔᕤ Hugo Black Bear

[![GitHub Pages](https://github.com/codertesla/hugo-black-bear/actions/workflows/gh-pages.yml/badge.svg)](https://github.com/codertesla/hugo-black-bear/actions/workflows/gh-pages.yml)
[![MIT license](https://img.shields.io/github/license/codertesla/hugo-black-bear)](https://github.com/codertesla/hugo-black-bear/blob/main/LICENSE)
[![Netlify Status](https://api.netlify.com/api/v1/badges/a1b8352b-7a24-4c40-9571-04987d60916a/deploy-status)](https://app.netlify.com/sites/hugo-black-bear-knowledge/deploys)
[![Demo](https://img.shields.io/badge/Website-Demo-blue)](https://hugo-black-bear.pages.dev/)

## Overview

🐻 A lightweight [Hugo](https://gohugo.io/) theme based on [Bear Blog](https://bearblog.dev) and [Hugo Bear Blog](https://github.com/janraasch/hugo-bearblog).

**Hugo Black Bear** focuses on speed and optimization, so you can focus on writing good content. It's free, open-source, multilingual, SEO-friendly, minimalist, responsive, and lightning-fast.

This version is specially optimized for building **knowledge bases**, **technical documentation**, and **how-to guides**.

## Key Features

- **Extreme Performance**: Near-perfect Google PageSpeed scores with a page size of ~5KB.
- **Professional Knowledge Base Skin**: Includes `knowledge-dark`, a theme designed for knowledge sharing.
- **Comprehensive Content Components**: Provides info blocks, collapsible sections, enhanced code highlighting, professional tables, and more.
- **Highly Accessible**: Optimized color contrast meeting WCAG standards, and includes a "skip to main content" link.
- **SEO Friendly**: Automatically generates RSS feeds, `robots.txt`, and Open Graph / Twitter Cards metadata.
- **Secure & Clean**: No JavaScript, no tracking scripts, no ads, and a strict Content Security Policy.
- **Multilingual Support**: Out-of-the-box configuration for multilingual mode.

![PageSpeed score](https://raw.githubusercontent.com/codertesla/hugo-black-bear/main/images/pagespeed.webp)

## Knowledge Base Showcase

We've introduced the new `knowledge-dark` skin and a set of components to enhance the readability and professionalism of your documentation.

### 1. Optimized Info Blocks

Use beautifully styled `<blockquote>` to highlight important information, tips, or warnings.

> **Tip**: The `knowledge-dark` skin provides excellent typography and readability for documentation.

### 2. Collapsible Content

For lengthy content like installation instructions or configuration code, use the collapsible `details` shortcode to keep your page clean.

```go-html-template
{{</* details "Click to see installation guide" */>}}
1. Clone this repository
2. Install dependencies with `npm install`
3. Run the development server with `npm run dev`
{{</* /details */>}}
```

**Result:**
<details>
<summary>Click to see installation guide</summary>

1. Clone this repository
2. Install dependencies with `npm install`
3. Run the development server with `npm run dev`

</details>

### 3. Enhanced Code Highlighting

Code is the core of technical documentation. This theme provides a clear and readable code highlighting scheme.

```javascript
// Example: Fetch data from an API
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

### 4. Professional Data Tables

Use well-designed tables to present structured data clearly.

| Feature | Description | Status |
|---|---|---|
| Dark Theme | Professional dark color scheme | ✅ Implemented |
| Table of Contents | Auto-generated page navigation | ✅ Implemented |
| Collapsible Sections | Organize long-form content | ✅ Implemented |
| Info Blocks | Highlight important information | ✅ Implemented |

## Installation

Follow Hugo's [quick start](https://gohugo.io/getting-started/quick-start/) to create a new site, then clone this theme as a [Git submodule](https://git-scm.com/book/en/v2/Git-Tools-Submodules) into the `themes` directory:

```sh
git submodule add https://github.com/codertesla/hugo-black-bear.git themes/hugo-black-bear
```

Finally, add the following line to your site's configuration file, `hugo.toml`:

```sh
echo 'theme = "hugo-black-bear"' >> hugo.toml
```

## Configuration

Easily customize your site via the `hugo.toml` file. Below is a sample configuration. For more details, refer to the [example site configuration](https://github.com/codertesla/hugo-black-bear/blob/main/exampleSite/hugo.toml).

```toml
# Basic Configuration
baseURL = "https://example.com"
theme = "hugo-black-bear"
copyright = "John Doe (CC BY 4.0)"
defaultContentLanguage = "en"
enableRobotsTXT = true

# Syntax Highlighting Configuration
[markup]
  [markup.highlight]
    lineNos = true
    lineNumbersInTable = false
    noClasses = false # Ensures Hugo Black Bear can apply a custom, accessible highlight theme

# Multilingual Mode Configuration
[languages]
  [languages.en]
    title = "My Knowledge Base"
    languageName = "en-US 🇺🇸"
    LanguageCode = "en-US"
    contentDir = "content"
    [languages.en.params]
      madeWith = "Made with [Hugo Black Bear](https://github.com/codertesla/hugo-black-bear)"

[params]
  # Site Description
  description = "A knowledge base built with Hugo Black Bear"

  # Favicon Path
  favicon = "images/favicon.png"

  # Social Media Share Preview Image
  images = ["images/share.webp"]

  # Date Format
  dateFormat = "2006-01-02"

  # (Important) Theme Style Selection
  # Options: "original", "herman", "knowledge-dark"
  # "knowledge-dark" is the new dark skin optimized for knowledge bases
  themeStyle = "knowledge-dark"

  # (Optional) Dynamic Social Card Generation
  # A social card will be automatically generated for posts without `images` in front matter
  generateSocialCard = true

  # Author Information for RSS feed and "Reply by email" in post footers
  [params.author]
    name = "Your Name"
    email = "your.email@example.com"
```

## Contributing

If you encounter any issues while using this theme, feel free to open an [Issue](https://github.com/codertesla/hugo-black-bear/issues) or a [Pull Request](https://github.com/codertesla/hugo-black-bear/pulls). 