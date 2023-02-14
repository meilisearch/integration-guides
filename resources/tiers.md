# SDK tiers

The objective of Meilisearch's Integrations Team is to **ease Meilisearch usage to as many developers as possible**.

Given this statement, **tiers** are nothing more than a __group of SDKs/integrations__ where the integrations team can fairly divide their attention. Unfortunately is not possible to keep all the SDKs 100% updated against the new Meilisearch releases all the time, the Integrations Team is a polyglot small team that maintains 30+ different integrations and tools, so it is humanly impossible to consistently meet the Meilisearch quality standards.

The ultimate goal of introducing tiers is to allow the team to have more time for new projects/integrations so that more time can be invested and more users will be impacted.

It's been using [data collected here](https://docs.meilisearch.com/learn/what_is_meilisearch/telemetry.html) and data like GitHub stars, forks, and watchers to measure the impact of an SDK.

It is worth remembering that this priority is just a concept introduced by the team where it aims to give a decision weight before
we invest time in some issues of some SDK in question.

:warning: We will keep all officially maintained SDKs **working**. :warning:

## Tier #1

The SDKs in group #1 have total priority over the team's time. Issues are visited before issues are present in tier #2, for example.
It is worth remembering that this does not mean open issues will be finalized promptly. Every issue needs time to be understood/confirmed/worked on, and consequently closed.
All new Meilisearch features that make sense for those SDKs will be available in the release day.

## Tier #2

Tier #2 SDKs are the emergent ones, we strongly believe they can move further, and we are betting on them.
In any case, since they do not bring that much value compared to tier #1 we will only apply the amount of time required to keep it working and do important maintenance code and code cleanup.

Only in urgent cases where, for example, the SDK is no longer working issues from the SDKs in group #2 will be prioritized in comparison to tier #1.


## Tier #3

The SDKs in group #3 have relatively low user adoption compared to groups #2 and #1. They are probably new or have a small community behind the tech stack in the first place.
As with tier #2 SDKs in this group will be prioritized only in critical cases, and they are not going to receive active improvements from the integrations team.

This is a very special group because we really need help from the community here.


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
### How will the tiers be organized?

The method used is mostly manual and subjective, where we use the data previously collected from the [telemetry](https://docs.meilisearch.com/learn/what_is_meilisearch/telemetry.html) and Github to generate groups.

At first there are only 3 tiers, and in the future this number may change.

### Is it possible for an SDK to be moved up a level?

Yes, fully possible! Especially if the team detects that more users are interested and definitely using it.
Whenever a anomaly is detected, a change can be submitted to the `integration-guides` and the groups will be modified to better manage the team's time. The reassessment of the tiers will be carried out every release cycle (8 weeks).

### How to identify that an SDK belongs to some level?

It is possible by accessing the README.md of each repository, and it will contain a tier badge
below the Meilisearch logo, this badge says: "tiers #1", "tiers #2" and "tiers #3" like this:

[![tiers - #1](https://img.shields.io/static/v1?label=tiers&message=%231&color=blue)](https://github.com/meilisearch/integration-guides/blob/main/resources/tiers.md)
[![tiers - #2](https://img.shields.io/static/v1?label=tiers&message=%231&color=2ea44f)](https://github.com/meilisearch/integration-guides/blob/main/resources/tiers.md)
[![tiers - #3](https://img.shields.io/static/v1?label=tiers&message=%231&color=critical)](https://github.com/meilisearch/integration-guides/blob/main/resources/tiers.md)

#### Why SDKs are present in a particular tier?

Because those SDKs have the most active users whether in the Meilisearch Cloud or not. Also they have a larger or broader community in general. Other principles could be used to move SDKs around if we think is the right thing to do.
