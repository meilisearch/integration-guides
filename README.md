<p align="center">
  <img src="assets/logos/logo.svg" alt="Meilisearch" width="200" height="200" />
</p>


<h1 align="center">Meilisearch Integrations</h1>
<h5 align="center">This repository is the central reference for developing and maintaining integrations for <a href="https://github.com/meilisearch/meilisearch">Meilisearch</a>.
</h5>

<h4 align="center">
  <a href="https://github.com/meilisearch/meilisearch">Meilisearch</a> |
  <a href="https://docs.meilisearch.com">Documentation</a> |
  <a href="https://discord.meilisearch.com">Discord</a> |
  <a href="https://www.meilisearch.com">Website</a> |
  <a href="https://blog.meilisearch.com">Blog</a> |
  <a href="https://fr.linkedin.com/company/meilisearch">LinkedIn</a> |
  <a href="https://twitter.com/meilisearch">Twitter</a> |
  <a href="https://www.meilisearch.com/docs/faq/">FAQ</a>
</h4>

**The Integration Team owns all the repositories and tools that help the users integrate Meilisearch in their project.**

## 🛠 Our Integrations

Here are the different groups of integrations:

- the **SDKs**: the *devkits* that help the devs to use Meilisearch with their favorite language.
- the **Front-End Integrations**: to integrate a smooth search experience in the front-end of the projects.
- the **Web Framework Integrations**: to connect the web frameworks with Meilisearch.
- the **DevOps Tools**: to make the deployement of Meilisearch easier.
- the **Platform Plugins**: to sync your data with Meilisearch and/or add a search experience on different platforms.

The exhaustive list of the maintained repositories by the team is available below.

### <img src="assets/icons/dev.png" width="20"> SDKs for Meilisearch API

- [.Net](https://github.com/meilisearch/meilisearch-dotnet)
- [Dart](https://github.com/meilisearch/meilisearch-dart)
- [Golang](https://github.com/meilisearch/meilisearch-go)
- [Java](https://github.com/meilisearch/meilisearch-java)
- [JavaScript](https://github.com/meilisearch/meilisearch-js)
- [PHP](https://github.com/meilisearch/meilisearch-php)
- [Python](https://github.com/meilisearch/meilisearch-python)
- [Ruby](https://github.com/meilisearch/meilisearch-ruby)
- [Rust](https://github.com/meilisearch/meilisearch-rust)
- [Swift](https://github.com/meilisearch/meilisearch-swift)

### 🏗 Framework Integrations

- Laravel: the official [Laravel-Scout](https://github.com/laravel/scout) package supports Meilisearch.
- [Ruby on Rails](https://github.com/meilisearch/meilisearch-rails)
- [Symfony](https://github.com/meilisearch/meilisearch-symfony)

### <img src="assets/icons/front.png" width="20"> Front-End Integrations

- [Angular](https://github.com/meilisearch/meilisearch-angular)
- [React](https://github.com/meilisearch/meilisearch-react)
- [Vue](https://github.com/meilisearch/meilisearch-vue)
- [instant-meilisearch](https://github.com/meilisearch/instant-meilisearch): A search client that enables the integration of the open-source tool [instantsearch.js](https://www.algolia.com/doc/guides/building-search-ui/what-is-instantsearch/js/) with Meilisearch. This client allows you to combine the functionalities of Meilisearch with InstantSearch.js, resulting in a powerful and interactive search user interface.
- [Autocomplete client](https://github.com/meilisearch/meilisearch-js-plugins/tree/main/packages/autocomplete-client): A search client that enables the integration of the open-source tool [autocomplete-js](https://www.algolia.com/doc/ui-libraries/autocomplete/introduction/what-is-autocomplete/) with Meilisearch. This client allows you to utilize the powerful features of Meilisearch in combination with autocomplete functionality for an enhanced search experience.
- [docs-searchbar.js](https://github.com/meilisearch/docs-searchbar.js): a search bar integration for all kinds of documentation.

### 🧩 Platform Plugins

- [Firestore](https://github.com/meilisearch/firestore-meilisearch/)
- [Gatsby](https://github.com/meilisearch/gatsby-plugin-meilisearch/)
- [Strapi](https://github.com/meilisearch/strapi-plugin-meilisearch)
- [VuePress](https://github.com/meilisearch/vuepress-plugin-meilisearch)

### 🐳 DevOps Tools

- [Cloud Providers](https://github.com/meilisearch/cloud-providers): Centralize a set of tools to build Meilisearch images for multiple platforms.
  How to deploy a Meilisearch instance on every provider:
  - See this [dedicated page for AWS](https://www.meilisearch.com/docs/learn/cookbooks/aws) to use it.
  - See this [dedicated page for DigitalOcean](https://www.meilisearch.com/docs/learn/cookbooks/digitalocean) to use it.
  - See this [dedicated page for GCP](https://www.meilisearch.com/docs/learn/cookbooks/gcp) to use it.
- [meilisearch-kubernetes](https://github.com/meilisearch/meilisearch-kubernetes): how to deploy a Meilisearch instance on Kubernetes.

### <img src="assets/icons/other.png" width="20"> Misc

- [docs-scraper](https://github.com/meilisearch/docs-scraper): a scraper tool to automatically read the content of your documentation and store it into Meilisearch.
- [JS boilerplate](https://github.com/meilisearch/js-project-boilerplate/): a boilerplate to start a JS project.
- [meilisearch-migration](https://github.com/meilisearch/meilisearch-migration/)
- [mini-dashboard](https://github.com/meilisearch/mini-dashboard/)

### 🧑‍🔧 Work In Progress

- [WordPress plugin](https://github.com/meilisearch/meilisearch-wordpress) (Stopped at the moment)

## 📍 Roadmap and Discussions

- Our general discussions are available in the [issues of this repository](https://github.com/meilisearch/integration-guides/issues). Here is our [issue management process](https://github.com/meilisearch/integration-guides/blob/main/resources/issues.md).
- Our [roadmap](https://github.com/meilisearch/integration-guides/blob/main/roadmap/2021.md).

Feel free to take part of our current discussions, or [create a new issue](https://github.com/meilisearch/integration-guides/issues/new).

## 📖 Documentation

[Meilisearch docs](https://docs.meilisearch.com) is the official documentation project for Meilisearch.

## 🚀 Building an Integration

If you want to build an integration for Meilisearch, you are more than welcome to! And we would be more than happy to help you in the process :)

We are proud that some of our libraries were developed and are still maintained by external contributors ❤️

Here are [some guidelines](./resources/build-integration.md) that you should follow, as we want to guarantee consistency and coherence across the different integrations, as well as technical quality for the different Meilisearch users.
