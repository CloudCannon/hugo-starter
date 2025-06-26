---
_schema: default
title: Font Awesome Icons
post_hero:
  heading: Font Awesome Icons
  date: 2025-05-06T11:18:38+12:00
  author: T Richardson
  image: /images/blog/featured-image-3.jpg
  image_alt: A man in front of a laptop with a coffee in a dimly lit cafe.
tags:
  - icons
  - components
  - styling
thumb_image_path: /images/blog/pexels-cottonbro.jpg
thumb_image_alt: >-
  Someone writing a todo list in a notebook. Next to them on the table is a
  coffee and a small plant. Seen from the POV of the writer.
seo:
  page_description: A post describing how to use FontAwesome Icons throughout your site.
  canonical_url:
  featured_image: /images/blog/pexels-cottonbro.jpg
  featured_image_alt: >-
    Someone writing a todo list in a notebook. Next to them on the table is a
    coffee and a small plant. Seen from the POV of the writer.
  open_graph_type: article
  no_index: false
---
This project hosts its own free Font Awesome icon sets. This means you can avoid setting up your own custom icon kit in Font Awesome. This could be replaced with the basic CDN method of adding Font Awesome icons to your site if you have your own Font Awesome kit.

The complete icon list is present in the `icons.yml` file. This file contains objects containing an editor readable name, paired with a Font Awesome class that will add an icon to the locations it's added to in the layouts. This icon list can be used to populate CloudCannon input's wherever it's needed.

To add your own custom icons to this list, you can follow the example set out in the top of the `icons.yml` file for the CloudCannon logo. An editor-readable name is paired with a custom CSS class that we add styles to in our `static/css/custom-icons.css` file. Replicate the CSS in that file to add your own custom icons. An example of using an icon is present in our button components.

To remove Font Awesome Icons:

1. Remove the `static/fontawesome` directory.
2. Remove `static/css/custom-icons.css` , and the example custom icon `static/icons/logo.svg`.
3. Remove the icon links from the head of your site in `partials/head.html`:

```html
  <!-- Font Awesome icons -->
  <link href="/fontawesome/css/fontawesome.min.css" rel="stylesheet" />
  <link href="/fontawesome/css/brands.min.css" rel="stylesheet" />
  <link href="/fontawesome/css/solid.min.css" rel="stylesheet" />
  <link href="/fontawesome/css/regular.min.css" rel="stylesheet" />
  <link href="/css/custom-icons.css" rel="stylesheet" />
```

4. Remove `icons.yml`
5. Remove any select inputs that were using the icon

```yaml
icon:
  type: select
  options:
    values: data.icons
```

6. Remove icons from your defined data in `cloudcannon.config.yml`

```yaml
data_config:
  icons:
    path: data/icons.yml
```