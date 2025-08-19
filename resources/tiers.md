# SDK tiers

The objective of Meilisearch's integrations is to **ease Meilisearch usage to as many developers as possible**.

Given this statement, **tiers** are nothing more than a __group of SDKs/integrations__ where the Meilisearch team can fairly divide their attention. Unfortunately, it is not possible to keep all the SDKs 100% updated against the new Meilisearch features from Meilisearch releases all the time. The Meilisearch team is a small team that maintains 30+ different integrations and tools, so it is humanly impossible to consistently meet the Meilisearch quality standards.

The ultimate goal of introducing tiers is to allow the team to have more time to invest in new projects/integrations to impact even more users.

To measure the impact of an SDK, the data come from different places like [telemetry](https://docs.meilisearch.com/learn/what_is_meilisearch/telemetry.html) and GitHub's stars, forks, and watchers.

It is worth remembering that this priority is just a concept introduced by the team that aims to give a **decision weight** before investing time in some issues of the SDKs. So, it does not mean they will never work on feature requests from the bottom tiers anymore, but it says they will prioritize the top tiers most of the time transparently.

:warning: The team will still keep all officially maintained SDKs **working**. :warning:

## Tier #1

👉 Priority of the Meili team

The Meili team ensures these integrations provide all the tools to use the features contained in the latest release of Meilisearch.

Issues and PRs from the community are frequently browsed by the team. If the community cannot be reactive enough, bug fixes and/or important enhancements are implemented by the Meili team.

It is worth remembering that this does not mean open issues are addressed and fixed promptly. Every issue needs time to be understood/confirmed/worked on and consequently closed.<br>

## Tier #2

👉 Mostly improved by the community

Issues and PRs from the community are less frequently browsed by the team but still watched regularly.

Community work is crucial to improve the repository on a daily basis: suggest improvements, fix bugs and implement enhancements.

Integrations in this group will not receive active improvements or maintenance from the Meili team except for specific situations. Most of the work is implemented by the community and reviewed by the Meili team. If the community cannot be reactive enough and for **specific** situations, **critical** bug fixes and/or enhancements are implemented by the Meili team.

## Tier #3

👉 Fully improved by the community

The SDKs in group #3 have relatively low user adoption compared to groups #2 and #1. They are probably new or have a small community behind the tech stack in the first place.

Issues and PRs from the community are not the team's priority, but they are still watched from time to time.

Community work is mandatory to improve the repository on a daily basis: suggest improvements, fix bugs and implement enhancements.

Integrations in this group are prioritized only in **really critical** cases, and they are not going to receive improvements or maintenance from the Meili team. If the community cannot be reactive enough, only **really critical** bugs are fixed by the Meili team.

## Deprecated

Depending on the reasons, integrations in this group tend to be archived at some point (a few months/years). The Meili team does not accept any enhancement in these repositories, even from the community.

Bug fixes have to be done by the community since the Meili team cannot afford to spend time on them.

We made our best to provide alternatives to this tools: check the related README of these repositories to get more information.

## Tiers list

Integration | Tier | Meili maintainer |
-------------|------|-----|
JavaScript | #1 | @brunoocasali |
PHP | #1 | @curquiza |
meilisearch-js-plugins | #1 | @brunoocasali |
Strapi | #1 | @brunoocasali |
| | |
.NET | #2 | @curquiza |
Python | #2 | @curquiza |
Java | #2 | @curquiza |
Go | #2 | @curquiza |
Rails | #2 | @brunoocasali |
Ruby | #2 | @brunoocasali |
Kubernetes Chart | #2 | @brunoocasali |
| | |
Dart | #3 | @brunoocasali |
Rust | #3 | @curquiza |
Gatsby | #3 | @brunoocasali |
Firebase | #3 | @brunoocasali |
Flutter | #3 | @brunoocasali |
Swift | #3 | @curquiza |
Symfony | #3 | @brunoocasali |
Mini-dashboard | #3 | @curquiza |
Angular | #3 | @curquiza |
React | #3 | @curquiza |
Vue | #3 | @curquiza |
| | |
docs-searchbar.js | Deprecated | @curquiza |
docs-scraper | Deprecated | @brunoocasali |
meilisearch-migration | Deprecated | @curquiza |
VuePress | Deprecated | @curquiza |


## Internal maintainers

@curquiza and @brunoocasali are the main maintainers of the integration scope.

They are responsible for:

- Ensuring the release of new versions
- Browsing the issues, which means:
    - Redirect support questions to [Meili Discord](https://discord.meilisearch.com/)
    - Answer and apply triage on issues
    - Browse the requested feature requests: validate them, reject them, or ask for community's opinion.
- Browsing community's PRs and ensure they are reviewed
- Ensuring security fixes by merging bump of Dependabot
- Ensuring and follow [pre-release work related to the new Meilisearch version](./meilisearch-pre-release-work.md)
- Merge regularly Dependabot update to avoid outdated dependencies. We try to do it before releasing a new version of the integration.

## External contributors

Our most impactful contributors were invited to be part of the official maintainers of the SDKs alongside us :heart:.

They have the `Collaborator` badge and rights. So whenever you interact with one of them, you can trust their expertise and remember that they are aligned with our values.

Here is the list of the external collaborators that help us:

- **[@ahmednfwela](https://github.com/ahmednfwela)**: [`meilisearch-flutter`](https://github.com/meilisearch/meilisearch-flutter), [`meilisearch-dart`](https://github.com/meilisearch/meilisearch-dart), [`meilisearch-dotnet`](https://github.com/meilisearch/meilisearch-dotnet)
- **[@mmachatschek](https://github.com/mmachatschek)**: [`meilisearch-php`](https://github.com/meilisearch/meilisearch-php), [`laravel/scout`](https://github.com/laravel/scout)
- **[@norkunas](https://github.com/norkunas)**: [`meilisearch-php`](https://github.com/meilisearch/meilisearch-php), [`meilisearch-symfony`](https://github.com/meilisearch/meilisearch-symfony)
- **[@sanders41](https://github.com/sanders41)**: [`meilisearch-python`](https://github.com/meilisearch/meilisearch-python), [`docs-scraper`](https://github.com/meilisearch/docs-scraper)
- **[@Sherlouk](https://github.com/Sherlouk)**: [`meilisearch-swift`](https://github.com/meilisearch/meilisearch-swift)
- **[@flevi29](https://github.com/flevi29)**: [`meilisearch-js`](https://github.com/meilisearch/meilisearch-js), [`meilisearch-js-plugins`](https://github.com/meilisearch/meilisearch-js-plugins)
- **[@Ja7ad](https://github.com/Ja7ad)**: [`meilisearch-go`](https://github.com/meilisearch/meilisearch-go)

## FAQ

### How are the tiers organized?

The method used is mainly manual and subjective, using previously collected data from the [telemetry](https://docs.meilisearch.com/learn/what_is_meilisearch/telemetry.html) and Github to generate the groups.

Only 3 tiers were defined, but this number may change in the future, and this guide will be updated accordindgly.

### Is it possible for an SDK to move up a level?

Yes, fully possible! Especially if the team detects that more users are interested in and using it.
Whenever a anomaly is detected, a change can be submitted to the `integration-guides` and the groups will be modified to better manage the team's time. The reassessment of the tiers will be carried out every release cycle (8 weeks).

The other way around is also valid. A SDK can move to less important tiers. :shipit:

### Why are SDKs present in a particular tier?

In general, because those SDKs have more and the most active users. By "active users," it means more activity in the repository, like contributions, watching (GitHub watchers), stargazers (GitHub stars), and forks (GitHub clones).

Besides GitHub data, we track the importance of integration by constantly watching the data sent through the [telemetry](https://docs.meilisearch.com/learn/what_is_meilisearch/telemetry.html). Note that data is ANONYMOUS, but we know the used client by looking at the `User-Agent`/`X-Meilisearch-Client` headers.
We also give more weight when we know a particular SDK has more Meilisearch Cloud customers.

PS: Other principles that are not written here may be used to move SDKs around if the team thinks it is relevant.

### When will the new features from a new Meilisearch release be released in the integrations?

#1 integrations are up to date with the latest version of Meilisearch in the coming week of the [Meilisearch release](https://github.com/meilisearch/meilisearch/releases).

For other tiers, the features have to be implemented by the community. Issues are present in the related integration repositories. Once the PR is ready, the maintainers of the repository review and merge it to integrate it into the next integration release.
