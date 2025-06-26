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

{{< alert background_color="" alert_message="If your Git repository is becoming excessively large, consider using a Digital Asset Manager for your image management." color="" icon="" >}}

The image processing on this template makes use of Hugo's built in [image processing methods](https://gohugo.io/content-management/image-processing/). These take your original image, resize it into a more appropriate size for your site, and change it to a format of your choosing.

In this template there exists the following examples of image processing:

* A Bookshop component for image processing. This should be used when the image needs to update live in CloudCannon's Visual Editor. This is used throughout the placeholder Bookshop components on the site.
* A built in [figure shortcode](https://gohugo.io/shortcodes/figure/), that comes out-of-the-box with Hugo. This is supposed to be used amongst your markdown content, for example in a blog post.
* A 'hardcoded' example in the `layouts/blog/single.html` layout file, and in the `header` and `footer` partials.
* In the `article-list` partial, which is used in the&nbsp;`layouts/blog/list.html` layout file, and in the `/layouts/\_default/taxonomy.html` layout file.

## Visual Editing Fallbacks

As part of the image processing, the `resources.Get` function is used to fetch the image from the assets folder. An image living in the assets folder is referred to as a global resource in Hugo. The `resources.Get` function doesn't work in the Visual Editor so we must [detect when we're in the Visual Editor](https://github.com/CloudCannon/bookshop/blob/main/guides/hugo.adoc#rendering-different-content-when-live-editing), and use a fallback when we are. The fallback will just be a normal HTML image element, meaning it won't use the `resources.Get` function, and will come from the `static` folder. The `static` folder is mounted to the `assets` folder in the `hugo.yml` config file so that images can be used out of either location with the same path.

If we're using this image processing in a part of the site that isn't a Bookshop component, we don't need to use this visual editing fallback, as `resources.Get` will work as usual.

## A note on videos

The placeholder component `heroes/hero-video` has a video background that is self-hosted - meaning it comes straight from the `static` folder. This video uses a [poster](https://developer.mozilla.org/en-US/docs/Web/API/HTMLVideoElement/poster) image while it loads the video. There is no way to process the image used for the poster, so care must be taken to ensure the image used is a reasonable size. (Something in the realm of &lt;100kb as a ballpark figure.)

Similarly, no processing is run by Hugo on the video itself. Videos can quickly bloat your page size, and slow load times. If you want to use a video background on your site, it is recommended to use a video hosting platform like Vimeo (which lets you customize the video to fit with the styles on your site), or YouTube (not-so-customizable). You could also use a DAM like Cloudinary to avoid self-hosting the video.