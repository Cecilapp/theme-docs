---
title: New release
description: "Collapsible navigation, search without a service, copy buttons and accessibility improvements: a tour of the new version of the theme."
date: 2026-10-01
authors:
  - cecil
  - name: Jane Doe
    title: Contributor
    url: https://example.com
    image: images/authors/jane-doe.png
---
A new version of the _Docs_ theme is available! It brings a better navigation, a search that works without any external service, and many accessibility and maintainability improvements. Here is a tour of what's new.

## Collapsible navigation

Each sub-section of the documentation is now a collapsible group in the sidebar. Groups are open by default, and the group of the current page is always expanded. To collapse a group, add `collapsed: true` to the front matter of its `index.md` file:

```yaml
---
title: Advanced
weight: 3
collapsed: true
---
```

Or collapse all of them at once, in the configuration:

```yaml
sidebar:
  collapsed: true
```

Section pages also got their own template: they now display the sidebar, cards linking to their sub-pages, and the previous/next navigation.

## Search without a service

[Algolia DocSearch](https://docsearch.algolia.com) is still supported (with the [DocSearch component theme](https://github.com/Cecilapp/theme-docsearch)), but you can now use the [FlexSearch component theme](https://github.com/Cecilapp/theme-flexsearch) instead: the search index is generated at build time, and the search runs entirely in the browser.

```yaml
theme:
  - docs
  - flexsearch
```

:::tip
Press `Ctrl` + `K` (or `⌘` + `K` on macOS) to open the search box from anywhere.
:::

## Small things that matter

Some changes are less visible, but make the daily use of the theme more pleasant:

| Feature                | Description                                                    |
|------------------------|----------------------------------------------------------------|
| Copy button            | Every code block can be copied to the clipboard in one click   |
| Last updated date      | Set the `updated` front matter variable to display it          |
| Mermaid on demand      | The library is loaded only on pages containing a diagram       |
| Theme-aware diagrams   | Mermaid diagrams are re-rendered when switching the color mode |
| Custom 404 page        | With links to the home page, the documentation and the search  |

## Accessibility

We also went through the theme with keyboard and screen reader users in mind:

1. A "Skip to content" link is the first focusable element of each page.
2. The mobile menu can be closed with the `Escape` key, and the focus is moved accordingly.
3. Current pages are announced with `aria-current`, and the breadcrumb is a proper navigation landmark.
4. Contrast has been improved in dark mode.

:::important
The dropdown theme selector (`partials/selector-theme.html.twig`) has been removed in favor of the icon button. If you included it in your own templates, replace it with `partials/selector-theme-icon.html.twig`.
:::

## Upgrading

Update the theme with Composer, then rebuild your website:

```bash
composer update cecil/theme-docs
php cecil.phar build
```

Thanks to everyone who reported issues and suggested improvements. Your feedback shapes the next releases, so keep it coming!
