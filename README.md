<p align="center">
  <img src="assets/logos/logo.svg" alt="MeiliSearch" width="200" height="200" />
</p>


<h1 align="center">MeiliSearch Integrations</h1>
<h5 align="center">This repository is the central reference for developing and maintaining integrations for <a href="https://github.com/meilisearch/MeiliSearch">MeiliSearch</a>.
</h5>

<h4 align="center">
  <a href="https://github.com/meilisearch/MeiliSearch">MeiliSearch</a> |
  <a href="https://docs.meilisearch.com">Documentation</a> |
  <a href="https://slack.meilisearch.com">Slack</a> |
  <a href="https://www.meilisearch.com">Website</a> |
  <a href="https://blog.meilisearch.com">Blog</a> |
  <a href="https://fr.linkedin.com/company/meilisearch">LinkedIn</a> |
  <a href="https://twitter.com/meilisearch">Twitter</a> |
  <a href="https://docs.meilisearch.com/faq/">FAQ</a>
</h4>

<p align="center">
  <a href="https://slack.meilisearch.com"><img src="https://img.shields.io/badge/slack-MeiliSearch-blue.svg?logo=slack" alt="Slack"></a>
</p>

**The Integration Team owns all the repositories and tools that help the users integrate MeiliSearch in their project.**

## 🛠 Our Integrations

Here are the different groups of integrations:

- the **SDKs**: the *devkits* that help the devs to use MeiliSearch with their favorite language.
- the **Front-End Integrations**: to integrate a smooth search experience in the front-end of the projects.
- the **Web Framework Integrations**: to connect the web frameworks with MeiliSearch.
- the **DevOps Tools**: to make the deployement of MeiliSearch easier.
- the **Platform Plugins**: to sync your data with MeiliSearch and/or add a search experience on different platforms.

The exhaustive list of the maintained repositories by the team is available below.

### <img src="assets/icons/dev.png" width="20"> SDKs for MeiliSearch API

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

- Laravel: the official [Laravel-Scout](https://github.com/laravel/scout) package supports MeiliSearch.
- [Ruby on Rails](https://github.com/meilisearch/meilisearch-rails)
- [Symfony](https://github.com/meilisearch/meilisearch-symfony)

### <img src="assets/icons/front.png" width="20"> Front-End Integrations

- [Angular](https://github.com/meilisearch/meilisearch-angular)
- [React](https://github.com/meilisearch/meilisearch-react)
- [Vue](https://github.com/meilisearch/meilisearch-vue)
- [instant-meilisearch](https://github.com/meilisearch/instant-meilisearch): a plugin to establish the communication between MeiliSearch and the open-source [InstantSearch](https://github.com/algolia/instantsearch.js) tools (powered by Algolia) for your front-end application.
- [docs-searchbar.js](https://github.com/meilisearch/docs-searchbar.js): a search bar integration for all kinds of documentation.

### 🐳 DevOps Tools

- [meilisearch-digitalocean](https://github.com/meilisearch/meilisearch-digitalocean): how to deploy a MeiliSearch instance on DigitalOcean. See this [dedicated page](https://docs.meilisearch.com/create/how_to/digitalocean_droplet.html) to use it.
- [meilisearch-aws](https://github.com/meilisearch/meilisearch-aws): how to deploy a MeiliSearch instance on AWS. See this [dedicated page](https://docs.meilisearch.com/create/how_to/aws.html) to use it.
- [meilisearch-gcp](https://github.com/meilisearch/meilisearch-gcp): how to deploy a MeiliSearch instance on GCP.
- [meilisearch-kubernetes](https://github.com/meilisearch/meilisearch-kubernetes): how to deploy a MeiliSearch instance on Kubernetes.
- [Cloud Scripts](https://github.com/meilisearch/cloud-scripts): centralize all the configurations to help our DevOps tool handle MeiliSearch.

### <img src="assets/icons/other.png" width="20"> Misc

- [docs-scraper](https://github.com/meilisearch/docs-scraper): a scraper tool to automatically read the content of your documentation and store it into MeiliSearch.

### 🧩 Platform Plugins

- [VuePress](https://github.com/meilisearch/vuepress-plugin-meilisearch)
- [Strapi](https://github.com/meilisearch/strapi-plugin-meilisearch)

### 🧑‍🔧 Work In Progress

- [meilisearch-wordpress](https://github.com/meilisearch/meilisearch-wordpress)

## 📍 Roadmap and Discussions

- Our general discussions are available in the [issues of this repository](https://github.com/meilisearch/integration-guides/issues). Here is our [issue management process](https://github.com/meilisearch/integration-guides/blob/main/guides/issues.md).
- Our [roadmap](https://github.com/meilisearch/integration-guides/blob/main/roadmap/2021.md).

Feel free to take part of our current discussions, or [create a new issue](https://github.com/meilisearch/integration-guides/issues/new).

## 📖 Documentation

[MeiliSearch docs](https://docs.meilisearch.com) is the official documentation project for MeiliSearch.

## 🚀 Building an Integration

If you want to build an integration for MeiliSearch, you are more than welcome to! And we would be more than happy to help you in the process :)

We are proud that some of our libraries were developed and are still maintained by external contributors ❤️

Here are [some guidelines](./guides/build-integration.md) that you should follow, as we want to guarantee consistency and coherence across the different integrations, as well as technical quality for the different MeiliSearch users.
