# MeiliSearch integrations and SDKs guide

Fully maintained:

- [Javascript](https://github.com/meilisearch/meilisearch-js)
- [Python](https://github.com/meilisearch/meilisearch-python)
- [Ruby](https://github.com/meilisearch/meilisearch-ruby)
- [Golang](https://github.com/meilisearch/meilisearch-go)
- [Swift](https://github.com/meilisearch/meilisearch-swift)
- [PHP](https://github.com/meilisearch/meilisearch-php)
- [Laravel Scout](https://github.com/meilisearch/meilisearch-laravel-scout)

Work in progress:

- [Java](https://github.com/meilisearch/meilisearch-java)

This repository aims to centralize all information about the different SDKs & integrations that are built around MeiliSearch.

## Documentation

Here is the [MeiliSearch documentation](https://docs.meilisearch.com).
There is no documentation for the different SDKs except the dedicated READMEs. There is a [discussion about it](https://github.com/meilisearch/sdks/issues/3).

## Building an integration

If you want to build an integration for MeiliSearch, you are more than welcome to and we would be happy to help you :)

We are proud to say that some of our libraries was done and still maintained by external contributors!

Here are some guidelines that you should follow though, if we want to guarantee consistency across the differents integrations and technical quality for the different MeiliSearch users.

#### README

All the README should follow the same patterns. This repository should hold the README template and at some point, we might want to automatically update all the readmes from here.

Since we don't provide a official template in this repository, here are the minimum part that the README must contain:

- A well-explained `Getting Started` part: the user should be able to copy/paste the code and command examples and everything should work as expected.
- Basic code examples
- A `Development Workflow` part so that everyone can easily contribute

We recommand to check out the READMEs of our SDKs repositories 🙂

#### Tests

If you want to start writing tests you can read what the [PHP SDK](https://github.com/meilisearch/meilisearch-php) is testing to get an overview of minimum viable tests that your SDK should support. The [JS](https://github.com/meilisearch/meilisearch-js) and the [Ruby](https://github.com/meilisearch/meilisearch-ruby) SDKs are also good examples of deeper tests.

#### Linter

A linter should be added to optimize contributions.
