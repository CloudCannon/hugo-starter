# Hugo CloudCannon Starter

A starting template for developers looking to build a site suitable for editing in CloudCannon with Hugo. Created by, and optimized for, CloudCannon.

Create your own copy, and start creating your own components quickly, to build your own component-based page building system. A blog section demonstrates best practices for editing longer form text in CloudCannon, using fixed layouts with changing content, instead of the component-based approach with page's that have unique layouts.

This template is aimed at helping developers build sites quickly, rather than providing editors with a fully built editable site. If you are an editor looking for an fully built template, have a look at [CloudCannon's templates page](https://cloudcannon.com/templates/).

[See a demo version of this site](TODO: Add link here).

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