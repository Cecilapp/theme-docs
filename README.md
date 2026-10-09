# _Docs_ theme

_Docs_ is a documentation theme for [Cecil](https://cecil.app), designed to provide a modern and responsive interface for your project's documentation, powered by [Tailwind CSS](https://tailwindcss.com) and [Algolia DocSearch](https://docsearch.algolia.com).

![Screenshot](./docs/screenshot.png)

## Features

- Auto-generated navigation sidebar (based on nested sections), with collapsible groups
- Search: [Algolia DocSearch](https://docsearch.algolia.com) or [FlexSearch](https://github.com/Cecilapp/theme-flexsearch) integration
- Copy button on code blocks
- "Edit this page" link and "Last updated" date
- Previous/next navigation through nested sections
- Custom 404 page
- Ready for content localization (l10n)
- Templates internationalization (i18n)
- Mobile friendly
- Dark theme
- Blog posts templates

## Installation

```bash
composer require cecil/theme-docs
```

> Or [download the latest archive](https://github.com/Cecilapp/theme-docs/releases/latest/) and uncompress its content in `themes/docs`.

## Usage

Add `docs` in the `theme` section of the `config.yml`:

```yaml
theme:
  - docs
```

### Configuration

The navigation sidebar is generated automatically from the folders structure of
`pages/docs/`, based on [nested sections](https://cecil.app/documentation/content/#sub-section):
each sub-folder containing an `index.md` file becomes a collapsible group, at
any depth. Ordering is based on pages `weight` (e.g. a `1-` filename prefix or a
`weight` front matter variable).

> [!NOTE]
> The `1-` prefix is removed from file names only: use the `weight` front matter
> variable in the `index.md` file of a sub-folder to order it (the prefix would
> otherwise be kept in its URL).

Groups are open by default. Set `collapsed: true` in the front matter of a section
(`index.md`) to collapse it, or `sidebar.collapsed: true` in the configuration to
collapse all of them: the group of the current page is always open.

The `updated` front matter variable of a page is displayed as its "Last updated"
date (enable `lastupdated` to display the page date otherwise).

```yaml
footer: Copyright © %author%
github:
  url: https://github.com/<org>/<repo> # GitHub link in header
  repo: https://github.com/<org>/<repo> # "Edit this page" link
  branch: <main|master>
  path: pages # pages directory path in the repository (default: pages)
sidebar:
  collapsed: false|true # collapse the navigation groups, except the current one (default: false)
lastupdated: false|true # display the page date as "Last updated" date (default: false)
docsearch:
  enabled: true|false
  appId: <YOUR_APP_ID>
  indexName: <YOUR_INDEX_NAME>
  apiKey: <YOUR_SEARCH_API_KEY>
  debug: false|true
```

### Search with FlexSearch

As an alternative to DocSearch (no external service), install the
[FlexSearch component theme](https://github.com/Cecilapp/theme-flexsearch) and add it after `docs`:

```yaml
theme:
  - docs
  - flexsearch
```

The search button is displayed in the header (DocSearch takes precedence if both are enabled).

## Development

### Install deps

```bash
composer install
```

### Rebuild CSS

```bash
composer css:build
```

CSS is compiled with [tailwind-builder](https://github.com/ArnaudLigny/tailwind-builder),
which uses the [Tailwind](https://tailwindcss.com) standalone binary (no Node.js required).

### Demo site

The `demo/` folder contains a site using this theme (nested sections, notes,
code, Mermaid diagrams, blog, FlexSearch, French translation), to test changes locally with
[Cecil](https://cecil.app/download/):

```bash
php demo/link.php # links the repository as `demo/themes/docs` and installs FlexSearch (once)
cecil serve demo
```

## License

_Docs_ theme is a free software distributed under the terms of the MIT license.

© [Arnaud Ligny](https://arnaudligny.fr)
