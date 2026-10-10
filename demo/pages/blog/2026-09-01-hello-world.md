---
title: Hello world
description: "Welcome to the blog of the _Docs_ theme! This first post introduces the theme, explains why it exists, and shows how a blog can live next to your documentation in the same Cecil website."
date: 2026-09-01
author: cecil
---
Welcome to the blog of the _Docs_ theme! This first post introduces the theme, explains why it exists, and shows how a blog can live next to your documentation in the same Cecil website.

## Why a documentation theme?

Writing documentation is hard enough: the tool rendering it should get out of the way. The _Docs_ theme was designed with a few principles in mind:

- **Content first**: pages are plain Markdown files, organized in folders, with no special syntax to learn.
- **Navigation for free**: the sidebar is built from the folders structure of `pages/docs/`, so adding a page is enough to make it reachable.
- **Fast by default**: static HTML, a single stylesheet, and JavaScript loaded only when a page needs it (Mermaid diagrams, for example).
- **Readable everywhere**: a responsive layout, a dark mode following the system preference, and accessible components.

> Good documentation is like a good map: you only notice it when it's missing.

## A blog, next to the docs

Release notes, tutorials and announcements don't always fit in the reference documentation. That's why the theme also ships templates for a `blog` section: create a `pages/blog/` folder, add an `index.md` file and start writing posts.

```bash
mkdir pages/blog
cat > pages/blog/index.md <<EOF
---
title: Blog
sortby: date
---
EOF
```

Each post displays its date, an estimated reading time, and its author(s). Authors can be defined once in `data/authors.yml`, then referenced by their key in the front matter of each post:

```yaml
# data/authors.yml
cecil:
  name: Cecil
  title: Static site generator
  url: https://cecil.app
```

```yaml
# front matter of a post
---
title: Hello world
date: 2026-09-01
author: cecil
---
```

## What's next?

In the next posts, we'll cover the new features of the theme: collapsible navigation groups, client side search, copy buttons on code blocks, and more.

In the meantime, have a look at the [documentation](../../docs/), and feel free to open an issue on [GitHub](https://github.com/Cecilapp/theme-docs) if something is missing.

Happy writing!
