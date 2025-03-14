# Hugo CloudCannon Starter

A starting template for developers looking to build a site suitable for editing in CloudCannon with Hugo. Created by and optimized for CloudCannon.

Create your own copy, and start creating your own components quickly build your own component-based page building system. A blog section is set up, demonstrating best practices for editing longer form text in CloudCannon.

This template is aimed at helping developers build sites quickly, rather than providing editors with a fully built editable site. If you are an editor looking for an already built template, have a look at [CloudCannon's templates page](https://cloudcannon.com/templates/).

[See a demo version of this site](https://tiny-jackal.cloudvent.net/).

## Features

Hugo CloudCannon Starter has many built-in features to aid developers trying to get building quickly, while trying to keep the amount of placeholder content as easy to delete as possible

- [Page building with components](#components)
- [Markdown options & styles](#markdown)
- [Blog with pagination & tags](#blog)
- [Built-in search with Pagefind](#pagefind)
- [Pre-configured shortcodes](#shortcodes)
- [Header and Footer controls](#navigation)
- [Tailwind](#tailwind)
- [Font Awesome icons](#icons)
- [Create and delete pages](#pages-and-collections)
- [Accessibility controls](#accessibility)
- [SEO controls](#seo)
- [Color palette controls](#color-controls)

## Getting started 
TODO: Test this list

1. Select `Use as template` in GitHub to create a copy of the repository on your own GitHub account.
2. Build a site on CloudCannon, using your newly copied repository.

    a. Create a CloudCannon account if you haven't already
    
    b. Go to `Sites`

    c. Select `Create a new site`

    d. Select `Connect to a GitHub repository`

    e. Authenticate CloudCannon as an application on your GitHub if you haven't already

    f. Select build site

## Local development

To create a copy of your repository to work on your local machine:

1. Run `git clone` in the directory you want your repository; eg. `git clone git@github.com/cloudcannon/hugo-starter`
2. `cd` into the newly cloned Hugo starter directory. 
3. Run `npm install` at the root of the cloned directory
4. Run `npm start` to spin up a local server to see a preview of your site served at http://localhost:1313/.

### Components
Pages are built with components using a system called Bookshop. Some commonly used ones come with this template, to save time and demonstrate how to build your own.

#### Content blocks
Page's are built with components by adding them to a list of page blocks. The page's layouts then loop through that list, rendering them out onto the page. Components are stored and referenced by a concept called a [structure](TODO: link here). Content blocks is the default structure that components are added to.

#### Hero block
Page frontmatter is set up encourage editors to begin a page with a hero block. A non-technical editor may not know what a 'Hero' component is, or why it is important to begin the page with a Hero block. This is a good example of how you can choose your own editing workflows depending on how you structure your pages and site. Note that this input demonstrates how to add structures to objects inputs in CloudCannon, meaning you can allow just one component, or - in the case of the content_blocks inputs - an ordered list of components depending on the editing workflow you for that particular section of your site.

In this template, hero components belong to a [structure]() called `hero_blocks` and reference that structure from the input `hero_block` (as configured in our `cloudcannon.config.yml`). This will provide editors a list of those components belonging to `hero_blocks` to add to the page. 

### Markdown

#### Markdown toolbar
CloudCannon - at a very high level - is basically an interface to edit markdown files and commonly formats of data files.

#### Components in markdown content
Sometimes we want to add things throughout our long-form text content that are not able to be represented by traditional markdown syntax. To achieve this we can use components throughout our body content. 

In Hugo this concept is called a [shortcode](TODO: Link here). Different SSGs call this concept different things. In CloudCannon this concept is agnostically referred to as a [Snippet](TODO: Link here). 

This template comes with built in Hugo shortcodes, as well as two custom shortcodes - meant to demonstrate how to achieve something similar for your own use case.

To create a new custom shortcode, reference the `snippets` object in our `cloudcannon.config.yml` file, check out our [documentation](TODO: Link here), or if you're having trouble [get in touch](TODO: Link here) with our friendly support team.

### Blog & Documentation

### Pagefind

### Shortcodes

### Navigation

### Tailwind

### Icons

### Pages and Collections

### Accessibility

### SEO

### Color controls

### Input config

### Structures
Components that are a part of  `content_blocks` but not `hero_blocks` will not show up in this list, meaning an editor can not add them. A component can be added to multiple structures, allowing you to create whatever subsets of components you like.