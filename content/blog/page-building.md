---
_schema: default
title: Page Building
post_hero:
  heading: Page Building
  date: 2025-05-06T11:18:38+12:00
  author: T Richardson
  image: /images/blog/pexels-edmond-dantes.jpg
  image_alt: A group collaborating around a table.
tags:
  - bookshop
  - components
  - schemas
  - editing
  - building
  - WYSIWYG editing
  - live editing
thumb_image_path: /images/blog/pexels-edmond-dantes.jpg
thumb_image_alt: A group collaborating around a table.
seo:
  page_description: A post describing what page building features come with the Hugo starter.
  canonical_url:
  featured_image: /images/blog/pexels-edmond-dantes.jpg
  featured_image_alt: A group collaborating around a table.
  open_graph_type: article
  no_index: false
---
## Schemas

A schema is a predefined template that determines what should populate a collection file. You can configure several schemas for each collection, creating a list of file templates for you and your team.

Schemas are used for creating files with consistent content and populating the initial contents of a new file. Schemas can apply to structured, markup, and combination files by containing both front matter and markup content or only data or markup content. When you use a schema to populate a new file, you can be sure that the inputs you need are available in the sidebar of the Visual or Content Editor.

A blog schema might contain title, author, and hero image inputs in the front matter. A changelog schema for a technical documentation site might contain a date input in the front matter and headings for “Features” and “Fixes” in the Markdown content. A review schema might contain inputs for title, author, and rating, and “Today, we are reviewing the…” as the opening line in the Markdown content.

## Bookshop

Build custom components that non-technical editors can use in a page building experience in CloudCannon. [Bookshop](/blog/bookshop/) enables live editing in CloudCannon's visual editor.

Editors can reuse existing components with new content to build new pages in the CMS.

## Content Editor

Edit a page's body content in CloudCannon's WYSIWYG Content Editor if a page's changeable content is mainly markdown body content, which shares a common layout. This is great for sections like the blog you are reading this in.