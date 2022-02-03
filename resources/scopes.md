# Scopes

**This guide is to describe which internal developer at Meili is responsible for which repository.**

The developer responsible for the repository has to:
- ensure the issues are well answered.
- merge PRs: this involves you need to review and/or request the right reviewers to safely merge the PRs.
- make releases on a regular basis
- ensure the documentation (README.md and CONTRIBUTING.md) is up to date

A developer responsible for a scope is the only one to have the access to merge PRs using Bors (expect Admin GitHub users).

🥰 Being responsible for a repository does not mean you are alone. Feel free to ask for any help by pinging your colleagues on issues or PRs.
Same, if you are not responsible for a scope, you are always encouraged to check and comments PRs and issues in the other repositories.

👥 Some repositories are handled by external contributors, and we are really grateful for this! This table only describes who is internally responsible at Meili, even if many contributors are highly present on this repository. This person can be considered as the Meili referent for the community. You can ping her/him if you have any question.

| Repository | Meili's developer |
|------------|-------------------|
| [.Net SDK](https://github.com/meilisearch/meilisearch-dotnet) | [brunoocasali](https://github.com/brunoocasali/) |
| [Dart SDK](https://github.com/meilisearch/meilisearch-dart) | [brunoocasali](https://github.com/brunoocasali/) |
| [Golang SDK](https://github.com/meilisearch/meilisearch-go) | [alallema](https://github.com/alallema/) |
| [Java SDK](https://github.com/meilisearch/meilisearch-java) | [alallema](https://github.com/alallema/) |
| [JavaScript SDK](https://github.com/meilisearch/meilisearch-js) | [bidoubiwa](https://github.com/bidoubiwa/) |
| [PHP SDK](https://github.com/meilisearch/meilisearch-php) | [alallema](https://github.com/alallema/) |
| [Python SDK](https://github.com/meilisearch/meilisearch-python) | [alallema](https://github.com/alallema/) |
| [Ruby SDK](https://github.com/meilisearch/meilisearch-ruby) | [brunoocasali](https://github.com/brunoocasali/) |
| [Rust SDK](https://github.com/meilisearch/meilisearch-rust) | [curquiza](https://github.com/curquiza/) |
| [Swift SDK](https://github.com/meilisearch/meilisearch-swift) | [bidoubiwa](https://github.com/bidoubiwa/) |
|||
| [Laravel-Scout integration](https://github.com/laravel/scout) | [brunoocasali](https://github.com/brunoocasali/) |
| [Rails integration](https://github.com/meilisearch/meilisearch-rails)| [brunoocasali](https://github.com/brunoocasali/) |
| [Symfony integration](https://github.com/meilisearch/meilisearch-symfony)| [brunoocasali](https://github.com/brunoocasali/) |
|||
| [Angular integration](https://github.com/meilisearch/meilisearch-angular) | [bidoubiwa](https://github.com/bidoubiwa/) |
| [React integration](https://github.com/meilisearch/meilisearch-react) | [bidoubiwa](https://github.com/bidoubiwa/) |
| [Vue integration](https://github.com/meilisearch/meilisearch-vue) | [bidoubiwa](https://github.com/bidoubiwa/) |
| [instant-meilisearch](https://github.com/meilisearch/instant-meilisearch) | [bidoubiwa](https://github.com/bidoubiwa/) |
| [docs-searchbar.js](https://github.com/meilisearch/docs-searchbar.js) | [bidoubiwa](https://github.com/bidoubiwa/) |
|||
| [Firestore extension](https://github.com/meilisearch/firestore-meilisearch) (WIP) | [bidoubiwa](https://github.com/bidoubiwa/) |
| [Gatsby plugin](https://github.com/meilisearch/gatsby-plugin-meilisearch) | [bidoubiwa](https://github.com/bidoubiwa/) |
| [Strapi plugin](https://github.com/meilisearch/strapi-plugin-meilisearch) | [bidoubiwa](https://github.com/bidoubiwa/) |
| [VuePress plugin](https://github.com/meilisearch/vuepress-plugin-meilisearch) | [bidoubiwa](https://github.com/bidoubiwa/) |
|||
| [meilisearch-digitalocean](https://github.com/meilisearch/meilisearch-digitalocean) | [alallema](https://github.com/alallema/) |
| [meilisearch-aws](https://github.com/meilisearch/meilisearch-aws) | [alallema](https://github.com/alallema/) |
| [meilisearch-gcp](https://github.com/meilisearch/meilisearch-gcp) | [alallema](https://github.com/alallema/) |
| [meilisearch-kubernetes](https://github.com/meilisearch/meilisearch-kubernetes) | [alallema](https://github.com/alallema/) |
| [Cloud Scripts](https://github.com/meilisearch/cloud-scripts) | [alallema](https://github.com/alallema/) |
|||
| [docs-scraper](https://github.com/meilisearch/docs-scraper)| [bidoubiwa](https://github.com/bidoubiwa/) |
| [js-project-boilerplate](https://github.com/meilisearch/js-project-boilerplate)| [bidoubiwa](https://github.com/bidoubiwa/) |
| [meilisearch-migration](https://github.com/meilisearch/meilisearch-migration)| [bidoubiwa](https://github.com/bidoubiwa/) |
|||
| [WordPress integration](https://github.com/meilisearch/meilisearch-wordpress) (Stopped)| [curquiza](https://github.com/curquiza/) |

### Access

When a member of the integration team owns a repository, they have full access to this repository, i.e. Admin access on GitHub.

However, with great power comes great responsibility 🕸. It means:
- Merging with Bors (using `bors merge`) should always be privileged. Only merge manually if there is no other alternative.
- Informing the whole integration team (on Slack) before modifying settings in the `Settings` section of a repository: in case the change is too impactful and should not be applied or it could interest the other repositories of the team.
