# MeiliSearch Integrations and SDKs Guide

This repository aims to centralize all information about the different SDKs & integrations that are built around MeiliSearch.

### Language SDKs

- [Golang](https://github.com/meilisearch/meilisearch-go)
- [JavaScript](https://github.com/meilisearch/meilisearch-js)
- [Laravel Scout](https://github.com/meilisearch/meilisearch-laravel-scout)
- [PHP](https://github.com/meilisearch/meilisearch-php)
- [Python](https://github.com/meilisearch/meilisearch-python)
- [Ruby](https://github.com/meilisearch/meilisearch-ruby)
- [Swift](https://github.com/meilisearch/meilisearch-swift)

Work in progress:

- [Java](https://github.com/meilisearch/meilisearch-java)

### Front-End Integrations

- [VuePress plugin](https://github.com/meilisearch/vuepress-plugin-meilisearch)
- [docs-searchbar.js](https://github.com/meilisearch/docs-searchbar.js): a search bar integration for all kinds of documentation.

### Other integration tools

- [docs-scraper](https://github.com/meilisearch/docs-scraper): a scraper tool to automatically read the content of your documentation and store it into MeiliSearch.
- [meilisearch-digital-ocean](https://github.com/meilisearch/meilisearch-digital-ocean): how to deploy a MeiliSearch instance on DigitalOcean

## Documentation

Here is the [MeiliSearch documentation](https://docs.meilisearch.com).
There is no documentation for the different SDKs except the dedicated READMEs. There is a [discussion about it](https://github.com/meilisearch/sdks/issues/3).

## Building an integration

If you want to build an integration for MeiliSearch, you are more than welcome to and we would be happy to help you :)

We are proud that some of our libraries were developed and are still maintained by external contributors ❤️

Here are some guidelines that you should follow though, if we want to guarantee consistency across the differents integrations and technical quality for the different MeiliSearch users.

#### README

All READMEs should follow the same pattern. This repository should hold the README template and at some point, we might want to automatically update all the READMEs from here.

Since we don't provide an official template in this repository, here are the minimum part that the README must contain:

- A well-explained `Getting Started` part: the user should be able to copy/paste the code and command examples and everything should work as expected.
- Basic code examples for the most common actions.
- A `Development Workflow` part so that everyone can easily contribute.

We recommend to check out the READMEs of our SDKs repositories 🙂

#### Tests

If you want to start writing tests you can read what the [PHP SDK](https://github.com/meilisearch/meilisearch-php) is testing to get an overview of minimum viable tests that your SDK should support. The [JS](https://github.com/meilisearch/meilisearch-js) and the [Ruby](https://github.com/meilisearch/meilisearch-ruby) SDKs are also good examples of deeper tests.

#### Linter and Style

A linter should be added to ease contributions and maintainers work.

We also recommend to add a `.editorconfig` file so that everyone can follow minimal styling rules.

#### About Publishing

We ask external contributors to **not** publish the package on the official platforms before we move the work to the MeiliSearch organization. Meili team will handle this part since we will automate it 😉
