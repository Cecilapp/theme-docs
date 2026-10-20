---
title: Tags and pagination
description: "Blog posts can be tagged, and the blog can be paginated: how to use these two features of the theme."
date: 2026-10-15
author: cecil
tags: [blog, release]
---
Blog posts can now be tagged, and the list of posts can be paginated.

## Tags

Add a `tags` front matter variable to a post:

```yaml
---
title: My post
tags: [release, blog]
---
```

Tags are displayed on the post and in the list of posts, linked to the page of each tag (e.g. `/tags/release/`). All tags are listed in `/tags/`.

## Pagination

Pagination is disabled by default: enable it in the front matter of the blog section (`pages/blog/index.md`):

```yaml
---
title: Blog
pagination:
  enabled: true
  max: 5 # number of posts by page
---
```
