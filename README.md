# Hugo CloudCannon Starter

A starting template for developers looking to build a site suitable for editing in CloudCannon with Hugo. Created by, and optimized for, CloudCannon.

Create your own copy, and start creating your own components quickly, to build your own component-based page building system. A blog section demonstrates best practices for editing longer form text in CloudCannon, using fixed layouts with changing content, instead of the component-based approach with page's that have unique layouts.

This template is aimed at helping developers build sites quickly, rather than providing editors with a fully built editable site. If you are an editor looking for an fully built template, have a look at [CloudCannon's templates page](https://cloudcannon.com/templates/).

[See a demo version of this site](TODO: Add link here).

## Features

Hugo CloudCannon Starter has many built-in features to aid developers trying to get building quickly, while trying to keep the amount of placeholder content as easy to delete as possible. Some of these features include:

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

    a. [Create a CloudCannon account](TODO: Link to signup) if you haven't already

    b. Create an [organisation](TODO: Link to concept of org in docs) if you haven't already
    
    c. Go to `Sites`

    d. Select `Create a new site`

    e. Select `Connect to a GitHub repository`

    f. Authenticate CloudCannon as an application on your GitHub if you haven't already

    g. Select build site

    h. Any changes to your repository will trigger a rebuild for your attached site in CloudCannon.

## Local development

Any changes you make locally, which you then push to your git repository, will trigger a rebuild on the site associated with that repository in CloudCannon, and update your live site. Similarly when you make changes to your repository - via CloudCannon, or by any other means - run `git pull` to keep your local environment up to date.

To create a copy of your repository to work on your local machine:

1. Run `git clone` in the directory you want your repository
2. `cd` into your newly cloned Hugo starter directory. 

3. Run `npm install` at the root of your cloned directory

4. Run `npm start`

5. Navigate to https://localhost:1313


## Pages and Collections
Editors build unique pages in 'blocks', using a [component page-building](#components) system called Bookshop. These components are stored in our markdown page's frontmatter with their properties (TODO: Properties or property's). Non-technical editors can edit the values of these properties via inputs in the CMS. Developers have full control over each property's input therefore controlling how editors update property values. Using Bookshop components allows CloudCannon's Visual Editor to show editor's changes live as they're making them. This is demonstrated in the pages collection of this template.

Some collections - such as a blog, or documentation section - tend to follow a common layout. In practice, this means these type of sections don't need to be built with components. Usually all that needs to be editable in these collections is our markdown body content, so in general it is recommended to use the Content Editor - a WYSIWYG text editor - instead of the Visual Editor. If we need more complex parts - something that can't be represented by markdown syntax - of a page using this editing approach we can use [snippets](#components-in-markdown-content). You can set up the visual editor so that you can use the content editor on the visual preview page, if visual previews are important for that collection.

Both content collections include schemas, demonstrating how an editor would add new pages to a collection with the appropriate initial content and frontmatter. A separate data collection is set up to demonstrate how to use data files for site-wide values, and to populate list inputs in CloudCannon. All of these collections are configured for CloudCannon, and aim to provide a good boilerplate to build your own site and editing experience on top of.

## Components
Pages are built with components using a system called [Bookshop](TODO: Link here). Some commonly used ones come with this template, to save time and demonstrate how to build your own. Bookshop is responsible for keeping frontmatter in sync with your Visual Editor preview, meaning it is essential in CloudCannon if you want live previews of your changes.

### Content blocks
Page's are built with components by adding them to a list of page blocks. The page's layouts then loop through that list, rendering them out onto the page. Components are stored and referenced by a concept called a [structure](#structures). Content blocks is the default structure that components are added to.

### Hero block
Page frontmatter is set up encourage editors to begin a page with a hero block. A non-technical editor may not know what a 'Hero' component is, or why it is important to begin the page with a Hero block. This is a good example of how you can choose your own editing workflows depending on how you structure your pages and site. Note that this input demonstrates how to add structures to objects inputs in CloudCannon, meaning you can allow just one component, or - in the case of the content_blocks inputs - an ordered list of components depending on the editing workflow you for that particular section of your site.

In this template, hero components belong to a [structure](#structures) called `hero_blocks` and reference that structure from the input `hero_block` (as configured in our `cloudcannon.config.yml`). This will provide editors a list of those components belonging to `hero_blocks` to add to the page. 

### Creating new components
TODO: Finish this para

## Markdown
CloudCannon - at a very high level - is an interface to write and edit markdown files and commonly used formats of data files. Basically it allows you to write markdown, without having to know how to write markdown. Hugo will then transform this markdown content into the HTML, CSS, and JavaScript that make up your end site.

### Markdown toolbar
CloudCannon comes with most conventional [markdown features](TODO: Link CC docs) out-of-the-box for editing markdown content. CloudCannon will output markdown on the page - appropriate to the formatting you have selected - which is then transformed into the correct HTML in your build. You can allow or disallow formatting options for editors in the `cloudcannon.config.yml` file. For body content markdown - edited in the WYSIWYG editor - this is controlled under the `_editables.content` object in the CloudCannon configuration file. For markdown inputs - often edited in the visual editor - those same options are configured under the `options` object for each input key configuration with.

## Blog & Documentation
The blog section in this starter template demonstrates best practices for setting up long-form text editing in CloudCannon. Documentation, news, or blog sections should replicate how this collection has been set up for Hugo and CloudCannon. 

The `_default/taxonomy.html` layout controls each tag's index page and the `blog/list.html` layout controls the blog's index page. Both use the `article-list.html` partial to list out an array of articles. The `article-list.html` partial accepts a `page_size` property that paginates when the article list size is greater than the `page_size`.

### Components in markdown content
Sometimes you will want to add things throughout your long-form text content that is not able to be represented by traditional markdown syntax. To achieve this we can use components throughout our body content. 

In Hugo this concept is called a [shortcode](TODO: Link here). Different SSGs refer to this concept by different names. In CloudCannon this concept is agnostically referred to as a [Snippet](TODO: Link here). 

This template comes with built in Hugo shortcodes, as well as two custom shortcodes - meant to demonstrate how to achieve something similar for your own use case.

To create a new custom shortcode, reference the `snippets` object in our `cloudcannon.config.yml` file and check out our [documentation](TODO: Link here). If you're having trouble, [get in touch](TODO: Link here) with our friendly support team.

## Pagefind search
This template comes with search out-of-the-box, using an open-source static search called [Pagefind](TODO: Link to pagefind docs). The search is present in the `article-list.html` partial, meaning it is present on the blog index page, and taxonomy pages. 

The search has been scoped to only include blog posts by using the key `data-pagefind-body` on the container element of the blog posts' layout. Only content nested within an element with this key will be indexed to be included search results.

To run search locally run `npm run pagefind-server`, and go to `http://localhost:1414/`.

## Navigation
Navigation is controlled through the data file `data/nav.yml`.

Controls for logos, colors, and links are present for the header and footer. 

Provide a starting year for the copyright statement, and it will stay up to date automatically each year.

Hero blocks that overlap with the header have page-specific style overrides to allow for changing of header colors on a page if needed.

## Tailwind
This template has Tailwind set up and ready to style if needed. 

If you would rather not use Tailwind and want to remove it from the project:
TODO: List here

## Icons
This project hosts it's own free Font Awesome icon sets. This means you can avoid setting up your own custom icon kit in Font Awesome. This could be replaced with the basic CDN (TODO: Check this) method of adding Font Awesome icons to your site if you have your own Font Awesome kit. 

The complete icon list is present in the `icons.yml` file. This file contains objects containing an editor readable name, paired with a Font Awesome class that will add an icon to the locations it's added to in the layouts. This icon list can be used to populate CloudCannon input's wherever it's needed.

To add your own custom icons to this list, you can follow the example set out in the top of the `icons.yml` file for the CloudCannon logo. An editor-readable name is paired with a custom CSS class that we add styles to in our `static/css/custom-icons.css` file. Replicate the CSS in that file to add your own custom icons. An example of using an icon is present in our button components

To remove icons, (TODO: Add remove list)

## Accessibility
- A focus on semantic HTML elements
  - `<nav>`
  - `<main>`
  - `<header>`
  - `<footer>`
  - `<section>`
  - [`links` vs `buttons`](https://www.a11yproject.com/checklist/#use-the-button-element-for-buttons).
- A `Skip to content` button.
- Alt tags for images and [logos](https://www.a11yproject.com/checklist/#for-images-containing-text-make-sure-the-alt-description-includes-the-images-text)
- Prefers reduced motion header and hero animations
- Background videos are pausable

## SEO
A general focus on performance, accessibility and SEO best practices mean this template is set up for SEO success.

Editors can control metadata values for SEO both at a site-wide level, and on a page-by-page basis, depending on each page's needs.

## Color controls
A color palette is controlled via the `data/colors.yml` file, which is used to populate the dropdown list editors will see in the app for select and multiselect inputs with the `values: data.colors` under their `options` key.

This demonstrates how to populate your own select and multiselect inputs with data files in CloudCannon.

## Input config
A range of different inputs are configured in CloudCannon, with corresponding templating in our code, to demonstrate how you can customise your non-technical editors workflows.

## Structures
Objects and arrays in CloudCannon need know what value to add when an editor wants to add to them. This is defined by a concept called structures. Any kind of array or object input or data file in this template should have a corresponding structure associated with them.

Bookshop components can belong to structures in CloudCannon. This means an array input like `content_blocks` with `structures: _structures.content_blocks` under it's `options` key will show options to add anything that belongs to the `content_blocks` structure. 

Similarly the `hero_block` input has the configuration `structures: _structures.hero_block` under it's `options` key. Components that are a part of the `content_blocks` structure but not `hero_blocks` will not show up in the list of components to add for `hero_block`, meaning an editor can not add them. 

This shows how you can scope certain components to certain inputs, depending on what components you would like made available in the place that input is used. A component can be added to multiple structures, allowing you to create whatever subsets of components you like.