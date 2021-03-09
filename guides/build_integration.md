# Build an Integration for MeiliSearch

Here are some guidelines that you should follow, as we want to guarantee consistency and coherence across the different integrations, as well as technical quality for the different MeiliSearch users.

## 1. Main Principle: User Experience First

The provided package should take into account the user experience: it should be easy to use by the user and as intuitive as possible. The customization is important, but the basic usage of the plugin should be accessible.

Feel free to [contact us](https://docs.meilisearch.com/learn/what_is_meilisearch/contact.html#contact-us) if you hesitate about an implementation choice.

## 2. README

Here are the minimum structure that the README must contain:

- A well-explained `Getting Started` section: the user should be able to copy/paste the code and command examples and everything should work as expected.
- Basic code examples for the most common actions.

We recommend checking out the READMEs of our other integration repositories.

## 3. CONTRIBUTING.md

The repository should contain a CONTRIBUTING.md. The [template is here](/templates/CONTRIBUTING.md) and needs to be filled according to the repository context.

## 4. Minimal Provided Methods

The minimal routes/behaviors an integration should handle are:

- the [documents manipulation](https://docs.meilisearch.com/reference/api/documents.html).
- the [search](https://docs.meilisearch.com/reference/api/search.html) with and without [search parameters](https://docs.meilisearch.com/reference/features/search_parameters.html).
- a basic error handler that wraps and throws the [MeiliSearch errors](https://docs.meilisearch.com/reference/api/#errors-status-code).

⚠️ All the other routes that are not handled by the integration yet should be clearly reported as an issue in the repository.

## 5. Tests

Each public method (so the exposed part of the tool) should be tested against the MeiliSearch instance. This ensures the provided methods work at any time.

Mocking tests are accepted but should not be prioritized since it would involve updating regularly the mocked server: MeiliSearch is indeed not stable yet.

If you want to start writing tests you can checkout the tests in our several repositories like [this one](https://github.com/meilisearch/meilisearch-php/).

## 6. Linter and Style

A linter should be added to ease contributions and maintainers work.

We also recommend to add a [`.editorconfig` file](https://editorconfig.org/) so that everyone can follow minimal styling rules.

## 7. CIs

A CI must run before merging into the main branch and should check:

- the tests run against the latest version of MeiliSearch. No need to support older version of MeiliSearch since MeiliSearch is not stable.
- the linter does not throw any error.

This guarantees the quality of the package and provides a welcoming environment for contributions.

## 8. About Publishing

The release versioning should follow the [Semantic Versioning Convention](https://docs.meilisearch.com/reference/api/#errors-status-code) and should have clear changelogs (in a CHANGELOG.md or in the GitHub release description [as we do in our repositories](https://github.com/meilisearch/meilisearch-ruby/releases)).

The publishement of each new release should be as smooth as possible to do quick updates after bug fixes or feature introductions.
