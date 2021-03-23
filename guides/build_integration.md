# Build an Integration for MeiliSearch

In order to guarantee consistency and quality across all MeiliSearch integrations, we request that you consider the following guidelines when creating a new integration.

## 1. Main Principle: User Experience First

The integration should take user experience into account: it should be as easy to use and intuitive as possible. In particular, the basic usage of the integration must be accessible.

Feel free to [contact us](https://docs.meilisearch.com/learn/what_is_meilisearch/contact.html#contact-us) if you're hesitating over an implementation decision.

## 2. README

At minimum, the README must contain:

- A well-explained `Getting Started` section: the user should be able to copy/paste the code and command examples and everything should work as expected.
- Basic code examples for the most common actions.

We recommend checking out the READMEs of our other integration repositories.

## 3. CONTRIBUTING.md

All integration repositories must contain a file titled `CONTRIBUTING.md`. The template is [here](/templates/CONTRIBUTING.md) and should be filled according to the details of your repository..

## 4. Minimal Provided Methods

The minimal routes/behaviors an integration should handle are:

- the [documents manipulation](https://docs.meilisearch.com/reference/api/documents.html).
- the [search](https://docs.meilisearch.com/reference/api/search.html) with and without [search parameters](https://docs.meilisearch.com/reference/features/search_parameters.html).
- a basic error handler that wraps and throws the [MeiliSearch errors](https://docs.meilisearch.com/reference/api/#errors-status-code).

⚠️ All the other routes that are not handled by the integration yet should be clearly reported as an issue in the repository.

## 5. Tests

Each public method (so the exposed part of the tool) should be tested against the MeiliSearch instance. This ensures the provided methods work at any time.

Mocking tests are accepted but should not be prioritized since it would involve updating regularly the mocked server: until v1 of MeiliSearch, most new versions introduce breaking changes.

If you want to start writing tests you can checkout the tests in our several repositories like [this one](https://github.com/meilisearch/meilisearch-php/).

## 6. Linter and Style

A linter should be added to ease contributions and maintainers work.

We also recommend to add a [`.editorconfig` file](https://editorconfig.org/) so that everyone can follow minimal styling rules.

## 7. Continuous Integration (CI)

A CI must run before merging into the main branch and should check:

- the tests run against the latest version of MeiliSearch. No need to support older version of MeiliSearch since MeiliSearch is not stable.
- the linter does not throw any error.

This guarantees the quality of the package and provides a welcoming environment for contributions.

## 8. Publishing

The release versioning should follow the [Semantic Versioning Convention](https://docs.meilisearch.com/reference/api/#errors-status-code) and should have clear changelogs (in a CHANGELOG.md or in the GitHub release description [as we do in our repositories](https://github.com/meilisearch/meilisearch-ruby/releases)).
