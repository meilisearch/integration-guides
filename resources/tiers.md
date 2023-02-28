# SDK tiers

The objective of Meilisearch's Integrations Team is to **ease Meilisearch usage to as many developers as possible**.

Given this statement, **tiers** are nothing more than a __group of SDKs/integrations__ where the Integrations Team can fairly divide their attention. Unfortunately is not possible to keep all the SDKs 100% updated against the new Meilisearch features from Meilisearch releases all the time. The Integrations Team is a polyglot small team that maintains 30+ different integrations and tools, so it is humanly impossible to consistently meet the Meilisearch quality standards.

The ultimate goal of introducing tiers is to allow the team to have more time to invest in new projects/integrations to impact even more users.

To measure the impact of an SDK, the data come from different places like [telemetry](https://docs.meilisearch.com/learn/what_is_meilisearch/telemetry.html) and GitHub's stars, forks, and watchers.

It is worth remembering that this priority is just a concept introduced by the team that aims to give a **decision weight** before investing time in some issues of the SDKs. So it does not mean they will never work on feature requests from the bottom tiers anymore, but it says they will prioritize the top tiers most of the time transparently.

:warning: The team will still keep all officially maintained SDKs **working**. :warning:

## Tier #1

The SDKs in group #1 have absolute priority over the team's time. For example, issues are visited before issues are present in tier #2.
It is worth remembering that this does not mean open issues are addressed and fixed promptly. Every issue needs time to be understood/confirmed/worked on and consequently closed.

All new Meilisearch features that make sense for those SDKs will be available on the release day.

## Tier #2

Tier #2 SDKs are the emergent ones. The Integrations Team believes they can move further and are betting on them.
In any case, since they bring less value than tier #1, the team will only spend the time required to keep these SDKs working and do the necessary maintenance code and code cleanup.

Only in urgent cases where, for example, the SDK is no longer working issues from the SDKs in group #2 prioritized over Tier #1.

## Tier #3

The SDKs in group #3 have relatively low user adoption compared to groups #2 and #1. They are probably new or have a small community behind the tech stack in the first place.
As with tier #2, SDKs in this group are prioritized only in critical cases, and they are not going to receive active improvements or maintance from the integrations team.

This is a very special group because the Integrations Team really need help from the community here.


## Tiers list

Integration | Tier |
-------------|------|
Javascript | #1 |
PHP | #1 |
Instant Meilisearch | #1 |
Python | #1 |
Go | #1 |
Strapi | #2 |
Ruby | #2 |
Rails | #2 |
.NET | #2 |
Rust | #2 |
Symfony | #3 |
docs-searchbar.js | #3 |
Firebase | #3 |
Dart | #3 |
Java | #3 |
Swift | #3 |
Vuepress | #3 |
Gatsby | #3 |

## FAQ
### How are the tiers organized?

The method used is mainly manual and subjective, using previously collected data from the [telemetry](https://docs.meilisearch.com/learn/what_is_meilisearch/telemetry.html) and Github to generate the groups.

Only 3 tiers were defined, but this number may change in the future, and this guide will be updated accordindgly.

### Is it possible for an SDK to move up a level?

Yes, fully possible! Especially if the team detects that more users are interested in and using it.
Whenever a anomaly is detected, a change can be submitted to the `integration-guides` and the groups will be modified to better manage the team's time. The reassessment of the tiers will be carried out every release cycle (8 weeks).

The other way around is also valid. A SDK can move to less important tiers. :shipit:

### How to identify which tier an SDK belongs to?

It is possible by accessing the README.md of each repository. A tier badge is present below the Meilisearch logo. The badge can have the following values: "tiers #1", "tiers #2" and "tiers #3". For example:

[![tiers - #1](https://img.shields.io/static/v1?label=tiers&message=%231&color=blue)](https://github.com/meilisearch/integration-guides/blob/main/resources/tiers.md)
[![tiers - #2](https://img.shields.io/static/v1?label=tiers&message=%232&color=2ea44f)](https://github.com/meilisearch/integration-guides/blob/main/resources/tiers.md)
[![tiers - #3](https://img.shields.io/static/v1?label=tiers&message=%231&color=critical)](https://github.com/meilisearch/integration-guides/blob/main/resources/tiers.md)

#### Why SDKs are present in a particular tier?

In general, because those SDKs have more and the most active users. By "active users," it means more activity in the repository, like contributions, watching (GitHub watchers), stargazers (GitHub stars), and forks (GitHub clones).

Besides GitHub data, we track the importance of integration by constantly watching the data sent through the [telemetry](https://docs.meilisearch.com/learn/what_is_meilisearch/telemetry.html). Note that data is ANONYMOUS, but we know the used client by looking at the `User-Agent`/`X-Meilisearch-Client` headers.
We also give more weight when we know a particular SDK has more Meilisearch Cloud customers.

PS: Other principles that are not written here may be used to move SDKs around if the team thinks it is relevant.
