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

## Features

- [Blog with pagination & tags](https://moss-goldfish.cloudvent.net/blog/paginated-collection/)

- [Markdown options & styles](https://moss-goldfish.cloudvent.net/blog/markdown/)

- [Tailwind](https://moss-goldfish.cloudvent.net/blog/tailwind/)

- [Font Awesome icons](https://moss-goldfish.cloudvent.net/blog/icons/)

- [Page building in CloudCannon with Bookshop components](https://moss-goldfish.cloudvent.net/blog/bookshop/)

- [Built-in search with Pagefind](https://moss-goldfish.cloudvent.net/blog/pagefind/)

- [Image processing](https://moss-goldfish.cloudvent.net/blog/processed-images/)

- [Pre-configured shortcodes](https://moss-goldfish.cloudvent.net/blog/markdown/#snippets)

- [Header and Footer controls](https://moss-goldfish.cloudvent.net/blog/data-files/)

- [Creating and deleting pages](https://moss-goldfish.cloudvent.net/blog/page-building/)

- [Accessibility controls](https://moss-goldfish.cloudvent.net/blog/lighthouse-scores/#accessibility)

- [SEO controls](https://moss-goldfish.cloudvent.net/blog/seo/)

- [Color palette controls](https://moss-goldfish.cloudvent.net/blog/data-files/)
