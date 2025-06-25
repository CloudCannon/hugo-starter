---
_schema: default
title: Tailwind
post_hero:
  heading: Tailwind
  date: 2025-05-06T11:28:34+12:00
  author: T Richardson
  image: /images/blog/pexels-ivan-samkov.jpg
  image_alt: A group of people conversing around a laptop.
tags:
  - building
  - styling
  - tailwind
thumb_image_path: /images/blog/pexels-ivan-samkov.jpg
thumb_image_alt: A group of people conversing around a laptop.
seo:
  page_description: A post describing how to use Tailwind to style your site, and how to uninstall it you don't want it.
  canonical_url:
  featured_image: /images/blog/pexels-ivan-samkov.jpg
  featured_image_alt: A group of people conversing around a laptop.
  open_graph_type: article
  no_index: false
---
Use Tailwind to style your HTML, allowing you to style your components without leaving your HTML. This can be used in combination with normal CSS and SCSS styling, leaving you to add styles to your site however you want. Tailwind can be a bit of a pain to set up in Hugo, so we've set it up for you in the hopes that it will save you some time. The placeholder content in this template is styled with traditional CSS, as Tailwind can be a bit polarising.

If you'd rather use traditional CSS to style your site, and would like to remove Tailwind:

1. Run `npm uninstall tailwindcss @tailwindcss/cli`.
2. Remove the file `tailwind.config.js`.
4. Remove talwind filter from the `layouts/partials/css.html` file (` | css.TailwindCSS $opts`).
5. Remove the following from your hugo.yaml file:
```yaml
  - source: (postcss|tailwind)\.config\.js
    target: css
```
6. Remove the import `@import "tailwindcss";` from your main.css file.