---
_schema: default
title: Processed Images
post_hero:
  heading: Processed Images
  date: 2025-06-21T02:42:53Z
  author: T Richardson
  image: /images/blog/pexels-polina-tankilevitch.jpg
  image_alt: >-
    A woman sitting sideways on a chair, working at a desk on a laptop. The only
    other thing on the desk is a small pot plant.
tags:
  - images
  - seo
  - components
  - live editing
thumb_image_path: /images/blog/pexels-polina-tankilevitch.jpg
thumb_image_alt: >-
  A woman sitting sideways on a chair, working at a desk on a laptop. The only
  other thing on the desk is a small pot plant.
seo:
  page_description: >-
    A blog post describing the image processing present on this starter
    template.
  canonical_url:
  featured_image: /images/blog/pexels-polina-tankilevitch.jpg
  featured_image_alt: >-
    A woman sitting sideways on a chair, working at a desk on a laptop. The only
    other thing on the desk is a small pot plant.
  open_graph_type: article
  no_index: false
---
Sometimes editors will&nbsp;inadvertently upload and use images that are unnecessarily large for use on your site. This can bloat the page size, leading to long load times. Processing the images as part of the build and using this processed image can help safeguard against this, without the editor needing to consider image sizes. Of course it is probably best for editors to at least somewhat consider it, to prevent your Git repository becoming excessively large, but at least with this protection in place your production site's load times will be protected.&nbsp;

{{< alert background_color="#034AD8" alert_message="If your Git repository is becoming excessively large, consider using a Digital Asset Manager for your image management." color="#ffffff" icon="fas fa-info-circle" >}}

The image processing on this template makes use of Hugo's built in [image processing methods](https://gohugo.io/content-management/image-processing/). These take your original image, resize it into a more appropriate size for your site, and change it to a format of your choosing.

In this template, image processing is handled by the `processed-image` partial, which is used in:

* The placeholder components on the site, such as `hero` and `left-right`.
* The blog post layout, `layouts/blog/single.html`, and the `blog-hero` partial.
* The `header-logo` and `footer` partials.
* The `article-list` partial, which is used in the&nbsp;`layouts/blog/list.html` layout file, and in the `/layouts/\_default/taxonomy.html` layout file.

## Visual Editing Fallbacks

As part of the image processing, the `resources.Get` function is used to fetch the image from the assets folder. An image living in the assets folder is referred to as a global resource in Hugo. The `resources.Get` function doesn't work in the Visual Editor, so we must detect when we're being rendered there and use a fallback. The editable regions Hugo module sets a `site.Params.ENV_CLIENT` site parameter for exactly this: it is `false` in a normal build and `true` in the Visual Editor's renderer. The fallback is just a normal HTML image element, meaning it won't use the `resources.Get` function, and will come from the `static` folder. The `static` folder is mounted to the `assets` folder in the `hugo.yaml` config file so that images can be used out of either location with the same path.

This applies everywhere, not just inside components. The Visual Editor re-renders the whole page, so any template that calls `resources.Get` needs the fallback — including layouts and partials like the header logo, footer and article list. Without it those images render as nothing at all in the editor.

All image rendering in this template goes through the `processed-image` partial, which handles the fallback in one place. Pass it an `image_path` and `image_alt`, plus optional `prop_src` and `prop_alt` selectors to make the image editable in place.

## A note on videos

The placeholder component `hero-video` has a video background that is self-hosted - meaning it comes straight from the `static` folder. This video uses a [poster](https://developer.mozilla.org/en-US/docs/Web/API/HTMLVideoElement/poster) image while it loads the video. There is no way to process the image used for the poster, so care must be taken to ensure the image used is a reasonable size. (Something in the realm of &lt;100kb as a ballpark figure.)

Similarly, no processing is run by Hugo on the video itself. Videos can quickly bloat your page size, and slow load times. If you want to use a video background on your site, it is recommended to use a video hosting platform like Vimeo (which lets you customize the video to fit with the styles on your site), or YouTube (not-so-customizable). You could also use a DAM like Cloudinary to avoid self-hosting the video.