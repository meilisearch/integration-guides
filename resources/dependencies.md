# Dependencies between the repositories

This resource is an exhaustive list of the existing dependencies between the integration team projects.

## JavaScript SDK

They depend on [`meilisearch-js`](https://github.com/meilisearch/meilisearch-js):
- [`docs-searchbar.js`](https://github.com/meilisearch/docs-searchbar.js)
- [`firestore-meilisearch`](https://github.com/meilisearch/firestore-meilisearch/)
- [`gatsby-plugin-meilisearch`](https://github.com/meilisearch/gatsby-plugin-meilisearch/)
- [`instant-meilisearch`](https://github.com/meilisearch/instant-meilisearch/)
- [`strapi-plugin-meilisearch`](https://github.com/meilisearch/strapi-plugin-meilisearch/)

## PHP SDK

They depend on [`meilisearch-php`](https://github.com/meilisearch/meilisearch-php):
- [`laravel/scout`](https://github.com/laravel/scout)
- [`meilisearch-symfony`](https://github.com/meilisearch/meilisearch-symfony/)

## Python SDK

They depend on [`meilisearch-python`](https://github.com/meilisearch/meilisearch-python):
- [`docs-scraper`](https://github.com/meilisearch/docs-scraper/)

## Ruby SDK

They depend on [`meilisearch-ruby`](https://github.com/meilisearch/meilisearch-ruby):
- [`meilisearch-rails`](https://github.com/meilisearch/meilisearch-rails/)

Also, even if they are not parts of the integration team, we should keep in mind the following projects strongly depend on `meilisearch-ruby`:
- the [`meilisearch-cloud`](https://github.com/meilisearch/meilisearch-cloud) backend (link only accessible internally)

## Instant MeiliSearch

They depend on [`instant-meilsearch`](https://github.com/meilisearch/instant-meilisearch/)
- [`meilisearch-angular`](https://github.com/meilisearch/meilisearch-angular/) and the [associated code-sandbox](https://codesandbox.io/s/im-angularis-7xipe?file=/src/app/app.component.ts)
- [`meilisearch-react`](https://github.com/meilisearch/meilisearch-react/) and the [associated code-sandbox](https://codesandbox.io/s/ms-react-is-sh9ud?fontsize=14&hidenavigation=1&theme=dark)
- [`meilisearch-vue`](https://github.com/meilisearch/meilisearch-vue/) and the [associated code-sandbox](https://codesandbox.io/s/ms-vue-is-1d6bi?fontsize=14&hidenavigation=1&theme=dark)
- The [code-sandbox of instant-meilisearch](https://codesandbox.io/s/ms-is-mese9?fontsize=14&hidenavigation=1&theme=dark)

Also, even if they are not parts of the integration team, we should keep in mind the following projects strongly depend on `instant-meilisearch`:
- the [`mini-dashboard`](https://github.com/meilisearch/mini-dashboard)
- the demos of the DevRel team, like [the MoMA demo](https://github.com/meilisearch/demo-MoMA)

## Docs-searchbar.js

They depend on [`docs-searchbar.js`](https://github.com/meilisearch/docs-searchbar.js)
- [`vuepress-plugin-meilisearch`](https://github.com/meilisearch/vuepress-plugin-meilisearch/)

## Cloud scripts

They depend on [`cloud-scripts`](https://github.com/meilisearch/cloud-scripts)
- [`meiliseach-aws`](https://github.com/meilisearch/meilisearch-aws/)
- [`meiliseach-digitalocean`](https://github.com/meilisearch/meilisearch-gcp/)
- [`meiliseach-gcp`](https://github.com/meilisearch/meilisearch-gcp/)

## VuePress plugin

No projects depends on [vuepress-plugin-meilisearch]((https://github.com/meilisearch/vuepress-plugin-meilisearch/) in the integration team.

Also, even if they are not parts of the integration team, we should keep in mind the following projects strongly depend on `vuepress-plugin-meilisearch`:
- The search bar of the [MeiliSearch documentation](https://github.com/meilisearch/documentation/)

## Docs scraper

No projects depends on [docs-scraper](https://github.com/meilisearch/docs-scraper/) in the integration team.

Also, even if they are not parts of the integration team, we should keep in mind the following projects strongly depend on `docs-scraper`:
- The search bar of the [MeiliSearch documentation](https://github.com/meilisearch/documentation/)
