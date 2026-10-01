---
_schema: default
title: Editable Regions
post_hero:
  heading: Editable Regions
  date: 2025-05-08T10:03:53+12:00
  author: T Richardson
  image: /images/blog/featured-image-1.jpg
  image_alt: A child working at a computer, seen from behind.
tags:
  - editable regions
  - components
  - live editing
thumb_image_path: /images/blog/blog-thumb-1.jpg
thumb_image_alt: A birds eye view of a group of people working on laptops around a table.
seo:
  page_description: >-
    A post describing how editable regions make a Hugo site editable in place in
    CloudCannon's Visual Editor.
  canonical_url:
  featured_image: /images/blog/featured-image-1.jpg
  featured_image_alt: A child working at a computer, seen from behind.
  open_graph_type: article
  no_index: false
---
[Editable regions](https://github.com/CloudCannon/editable-regions) are `data-` attributes you add to your own templates to tell CloudCannon which parts of a page an editor can change, and which file or key each change writes back to. There is no component framework to adopt and no build step to run — your Hugo partials stay plain Hugo partials.

Editable regions are fully open-source and available on GitHub at CloudCannon/editable-regions. As tooling that integrates into your codebase, we want to ensure you aren't vendor-locked to our platform. Sites built with editable regions remain fully portable and can be built or hosted anywhere on the web.

To add a new component, create a partial in `layouts/partials/`, add its styles at `assets/scss/components/<name>.scss`, and add a value with a matching `_name` to `_structures.content_blocks` in `cloudcannon.config.yml`.

## How it works in Hugo

The integration ships as a Hugo module. It is imported in `hugo.yaml` and loaded by `{{ partial "editable-regions" . }}` in the site `<head>`, where it self-gates on the editor and stays inert on your live site.

Marking something up as editable is a matter of adding attributes to the element you already render:

{{< accordion "Marking up a heading and a page builder array" >}}
A text region binds an element to a key in the page's front matter:

```html
<h1 data-editable="text" data-prop="heading.heading_text" data-type="span">
  {{ .heading.heading_text }}
</h1>
```

An array region binds a list of blocks, with each item naming the partial that renders it:

```html
<div data-editable="array" data-prop="content_blocks" data-component-key="_name">
  {{ range .Params.content_blocks }}
    <div data-editable="array-item" data-id="{{ ._name }}" data-component="{{ ._name }}">
      {{ partial ._name . }}
    </div>
  {{ end }}
</div>
```
{{< /accordion >}}

Region types cover the common cases: `text` for inline and block rich text, `image` for an image and its alt text, `array` and `array-item` for repeatable lists, `component` for a single nested object, and `source` for hard-coded copy that lives in a template rather than in content. Selectors can also point at a data file with `@data[nav]`, or at a page's markdown body with `@content`.

## What this brings to CloudCannon

Once your site is connected to CloudCannon, the Visual Editor uses these attributes to let your team click straight into the page. Editing text updates the file behind it; adding or reordering items in an array region rearranges the list in your front matter.

Anything marked with `data-component` is re-rendered in the browser by a WebAssembly build of Hugo, so a change to a block's inputs redraws that block with your real template — no separate component engine, and no second copy of your markup to keep in sync.

Components that are not marked up are still fully editable through the sidebar inputs, which is often the right call: derived lists, formatted dates and values chosen from a fixed set are usually better left to a structured input than to inline typing.
