# Hugo Starter by CloudCannon

A starting template for Hugo sites that are editable in place in CloudCannon's Visual Editor, using [editable regions](https://github.com/CloudCannon/editable-regions). Created by, and optimized for, CloudCannon.

Create your own copy, and start creating your own components quickly, to build your own component-based page building system. A blog section demonstrates best practices for editing longer form text in CloudCannon, using fixed layouts with changing content, instead of the component-based approach with pages that have unique layouts.

This template is aimed at helping developers build sites quickly, rather than providing editors with a fully built editable site. If you are an editor looking for an fully built template, have a look at [CloudCannon's templates page](https://cloudcannon.com/templates/).

[See a demo version of this site](https://frank-pine.cloudvent.net/).

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

5. Navigate to http://localhost:1313.

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
## Editing Locally with CloudCannon

Run CloudCannon against your local files with the [CloudCannon CLI](https://cloudcannon.com/documentation/developer-reference/cli/)
dev server. This is the fastest way to iterate on `cloudcannon.config.yml`, inputs, and structures —
you see the editing experience without committing and pushing first.

1. Install the CLI and log in (requires Node.js 24+):

   ```bash
   npm install --global @cloudcannon/cli
   cloudcannon login
   ```

2. Build the site, so the dev server has output to serve:

   ```bash
   npm run build
   ```

3. Start CloudCannon locally, pointing it at the build output:

   ```bash
   cloudcannon dev public
   ```

The dev server runs on port `10101` by default and opens CloudCannon in your browser, pointed at the
files in this repo. Content edits sync to disk as you make them; re-run the build after changing
components or templates to refresh the preview.

On CloudCannon, `.cloudcannon/postbuild` runs Pagefind after the Hugo build. To get site search in
the local preview too, run it yourself after building:

```bash
npx -y pagefind --site public
```

Before you commit configuration changes, validate them:

```bash
cloudcannon validate
```

The dev server is a development tool only — editors never access it. See
[Build your editing experience locally](https://cloudcannon.com/blog/build-your-editing-experience-locally-with-the-cloudcannon-dev-server/)
for the full workflow.

## Features

- [Blog with pagination & tags](https://frank-pine.cloudvent.net/blog/paginated-collection/)

- [Markdown options & styles](https://frank-pine.cloudvent.net/blog/markdown/)

- [Tailwind](https://frank-pine.cloudvent.net/blog/tailwind/)

- [Font Awesome icons](https://frank-pine.cloudvent.net/blog/icons/)

- [Page building in CloudCannon with editable regions](https://frank-pine.cloudvent.net/blog/editable-regions/)

- [Built-in search with Pagefind](https://frank-pine.cloudvent.net/blog/search/)

- [Image processing](https://frank-pine.cloudvent.net/blog/processed-images/)

- [Pre-configured shortcodes](https://frank-pine.cloudvent.net/blog/markdown/#snippets)

- [Header and Footer controls](https://frank-pine.cloudvent.net/blog/data-files/)

- [Creating and deleting pages](https://frank-pine.cloudvent.net/blog/page-building/)

- [Accessibility controls](https://frank-pine.cloudvent.net/blog/lighthouse-scores/#accessibility)

- [SEO controls](https://frank-pine.cloudvent.net/blog/seo/)

- [Color palette controls](https://frank-pine.cloudvent.net/blog/data-files/)
