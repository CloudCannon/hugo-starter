# Hugo CloudCannon Starter

A starting template for developers looking to build a site suitable for editing in CloudCannon with Hugo. Created by, and optimized for, CloudCannon.

Create your own copy, and start creating your own components quickly, to build your own component-based page building system. A blog section demonstrates best practices for editing longer form text in CloudCannon, using fixed layouts with changing content, instead of the component-based approach with pages that have unique layouts.

This template is aimed at helping developers build sites quickly, rather than providing editors with a fully built editable site. If you are an editor looking for an fully built template, have a look at [CloudCannon's templates page](https://cloudcannon.com/templates/).

[See a demo version of this site](https://moss-goldfish.cloudvent.net/).

## Getting started 

1. Select `Use as template` in GitHub to create a copy of the repository on your own GitHub account.

2. Build a site on CloudCannon, using your newly copied repository.

    a. [Create a CloudCannon account](https://app.cloudcannon.com/register) if you haven't already
    
    b. Go to `Sites`

    c. Select `Create a new site`

    d. Select `Connect to a GitHub repository` (or whatever Git provider you use).

    e. Authenticate CloudCannon as an application on your Git provider if you haven't already

    f. Select build site

    g. Any changes pushed to your repository will trigger a rebuild for your attached site in CloudCannon. Similarly any changes you make on CloudCannon will push to your connected Git repository.

## Prerequisites

- Hugo [install](https://gohugo.io/installation/). `brew install hugo`
- Go [install](https://go.dev/learn/). `brew install go`

## Local development

Any changes you make locally, which you then push to your git repository, will trigger a rebuild on the site associated with that repository in CloudCannon, and update your live site. Similarly when you make changes to your repository - via CloudCannon, or by any other means - run `git pull` to keep your local environment up to date.

To create a copy of your repository to work on your local machine:

1. Run `git clone` in the directory you want your repository.

2. `cd` into your newly cloned Hugo starter directory. 

3. Run `npm install` at the root of your cloned directory.

4. Run `npm start`.

5. Navigate to https://localhost:1313.

## Components and page building

Components are plain Hugo partials in `layouts/partials/`, marked up with
[CloudCannon editable regions](https://github.com/CloudCannon/editable-regions)
so they can be edited in place in the Visual Editor. The integration is a Hugo
module, imported in `hugo.yaml` and loaded by `{{ partial "editable-regions" . }}`
in the site `<head>`.

The page builder is the `content_blocks` array in a page's front matter. Each
block names its component in `_name`, which resolves as both a partial name and
a structure in `cloudcannon.config.yml`:

```yaml
content_blocks:
  - _name: hero        # renders layouts/partials/hero.html
    heading:
      heading_text: Hello
```

To add a component: create `layouts/partials/<name>.html`, add its styles at
`assets/scss/components/<name>.scss` (picked up automatically), and add a value
with `_name: <name>` to `_structures.content_blocks` in `cloudcannon.config.yml`.

Templates that use Hugo's asset pipeline (`resources.Get`, `.Resize`) need a
fallback for the Visual Editor, which cannot run it. Use `site.Params.ENV_CLIENT`
— see `layouts/partials/processed-image.html`.

## Features

- [Blog with pagination & tags](https://moss-goldfish.cloudvent.net/blog/paginated-collection/)

- [Markdown options & styles](https://moss-goldfish.cloudvent.net/blog/markdown/)

- [Tailwind](https://moss-goldfish.cloudvent.net/blog/tailwind/)

- [Font Awesome icons](https://moss-goldfish.cloudvent.net/blog/icons/)

- [Page building in CloudCannon with editable regions](https://moss-goldfish.cloudvent.net/blog/editable-regions/)

- [Built-in search with Pagefind](https://moss-goldfish.cloudvent.net/blog/search/)

- [Image processing](https://moss-goldfish.cloudvent.net/blog/processed-images/)

- [Pre-configured shortcodes](https://moss-goldfish.cloudvent.net/blog/markdown/#snippets)

- [Header and Footer controls](https://moss-goldfish.cloudvent.net/blog/data-files/)

- [Creating and deleting pages](https://moss-goldfish.cloudvent.net/blog/page-building/)

- [Accessibility controls](https://moss-goldfish.cloudvent.net/blog/lighthouse-scores/#accessibility)

- [SEO controls](https://moss-goldfish.cloudvent.net/blog/seo/)

- [Color palette controls](https://moss-goldfish.cloudvent.net/blog/data-files/)
