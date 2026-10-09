---
title: Getting started
description: Install and configure the theme.
---
# Getting started

This page shows the basic Markdown rendering of the theme.

## Installation

```bash
composer require cecil/theme-docs
```

Then add the theme to the `config.yml` file:

```yaml
theme:
  - docs
```

## Text formatting

Some **bold**, _italic_, ~~strikethrough~~ and `inline code` text, with a [link to the guides](../guides/) and an [external link](https://cecil.app).

> A blockquote, to quote something important.

### Lists

- First item
- Second item
  - Nested item
- Third item

1. Step one
2. Step two
3. Step three

### Table

| Option      | Type    | Default |
|-------------|---------|---------|
| `enabled`   | boolean | `false` |
| `indexName` | string  |         |
| `debug`     | boolean | `false` |

## Image

![Screenshot of the theme](/images/screenshot.png "Screenshot of the theme")
