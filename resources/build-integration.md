# Build an Integration for Meilisearch

To guarantee consistency and quality across all Meilisearch integrations, we request that you consider the following guidelines when creating a new integration.

## 1. Leading Principle: User Experience First

The integration should consider user experience: it should be as easy to use and intuitive as possible. In particular, the primary usage of the integration must be accessible.

Feel free to [contact us](https://docs.meilisearch.com/learn/what_is_meilisearch/contact.html#contact-us) if you're hesitating over an implementation decision.

## 2. README

At a minimum, the README must contain:

- A well-explained `Getting Started` section: the user should be able to copy/paste the code and command examples, and everything should work as expected.
- Basic code examples for the most common actions.

We recommend checking out the READMEs of our other integration repositories, like [this one](https://github.com/meilisearch/meilisearch-ruby/blob/main/README.md).

## 3. CONTRIBUTING.md

All integration repositories must contain a file titled `CONTRIBUTING.md`. The template is [here](/templates/CONTRIBUTING.md) and should be filled according to the details of your repository..

### 3.1 Docker & Docker-compose

To ease the maintenance, the integration should be ready to use with `Docker`, and it must contain a `Docker Compose` file configurated following these patterns:
- Must have a service `package` and a `meilisearch` service.
  - Must depend and contain a link to `meilisearch` service.
- The `meilisearch` service should point to `latest` tag.
  - `MEILI_NO_ANALYTICS` should be set to `true`
  - `MEILI_MASTER_KEY` should be set to `masterKey`

<details>
  <summary>See the Docker and Docker-compose sample</summary>

  ```yml
  version: "3.8"

  volumes:
    pub:

  services:
    package:
      image: dart:latest # this sample comes from the Dart SDK.
      tty: true
      stdin_open: true
      working_dir: /home/package
      environment:
        - MEILISEARCH_URL=http://meilisearch:7700
        - PUB_CACHE=/vendor/pub-cache
      depends_on:
        - meilisearch
      links:
        - meilisearch
      volumes:
        - pub:/vendor/pub-cache
        - ./:/home/package

    meilisearch:
      image: getmeili/meilisearch:latest
      ports:
        - "7700"
      environment:
        - MEILI_MASTER_KEY=masterKey
        - MEILI_NO_ANALYTICS=true
  ```
</details>

## 4. Minimal Provided Methods

At a minimum, your integration must support the following:

- all functionality related to [document manipulation](https://docs.meilisearch.com/reference/api/documents.html).
- all functionality related to [search](https://docs.meilisearch.com/reference/api/search.html), including [search parameters](https://docs.meilisearch.com/reference/features/search_parameters.html).
- a basic error handler that wraps and throws the [Meilisearch errors](https://docs.meilisearch.com/reference/api/#errors-status-code).
- ensure the correct headers are being sent:
  - the `User-Agent` header should contain this value i.e. `Meilisearch PHP (v1.0.1)`, `Meilisearch Strapi (v1.0.1)`, can also contain more than one: `Meilisearch PHP (v1.0.1); Meilisearch Laravel (v12.1.5);`

⚠️ All routes not yet implemented in the integration should be reported as an issue in the repository.

## 5. Tests

Each public method (i.e., the exposed part of the integration) should be tested against the Meilisearch instance. This ensures the provided methods work at any time.

Mock testing is accepted but should not be prioritized since it would require regularly updating the mocked server to account for breaking changes.

If you want to start writing your tests and are looking for a reference, you can find tests in most of our repositories, such as [meilisearch-php](https://github.com/meilisearch/meilisearch-php/) and [meilisearch-js](https://github.com/meilisearch/meilisearch-js/).

## 6. Linter and Style

Your integration should contain a linter to ease contributions and maintenance.

We recommend adding a [`.editorconfig` file](https://editorconfig.org/) so everyone can follow minimal styling rules.

## 7. Continuous Integration (CI)

All integration repositories should run a CI workflow before merging into the main branch. It should ensure that:

- the tests are successful with the latest version of Meilisearch. No need to support older versions of Meilisearch since Meilisearch is not stable at this time.
- the linter does not throw any errors.

This guarantees the quality of the package and provides a welcoming environment for contributions.

## 8. Publishing

The release versioning should follow the [Semantic Versioning Convention](https://docs.meilisearch.com/reference/api/#errors-status-code) and should have clear changelogs (in a `CHANGELOG.md` file or in the GitHub release description [as we do in our repositories](https://github.com/meilisearch/meilisearch-ruby/releases)).

---

Thank you for reading this through ❤️ Feel free to contact us with any questions!
