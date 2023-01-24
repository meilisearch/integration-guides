# Versioning policy

This page describes the versioning rules Meilisearch SDKs will follow once Meilisearch engine v1.0.0 is released and how/when we should increase the MAJOR, MINOR, and PATCH of the versions.

## 🤖 Basic rules

Meilisearch SDKs releases follow the [SemVer rules](https://semver.org/), including the following basic ones:

> 🔥 Given a version number MAJOR.MINOR.PATCH, increment the:
>
> 1. MAJOR version when you make incompatible API changes
> 2. MINOR version when you add functionality in a backwards compatible manner
> 3. PATCH version when you make backwards compatible bug fixes


**Changes that MAY lead the Meilisearch users (developers) to change their code are considered API incompatibility and will make us increase the MAJOR version of Meilisearch SDK.**

**In other terms, if the users MAY have to do more steps than just downloading the new Meilisearch instance and running it, a new MAJOR is needed.**

Examples of changes making the code break and then, involving increasing the MAJOR:

- Any change related to the public API the SDK exposes like:
    - Renaming a method name or classes
    - Removing or changing a positional argument of a method.

## Reasons why we should release a major version

#### New runtimes adoption

We don't have a strict policy yet regarding the bare minimum support of language version. Example:

Ruby SDK has a `required_ruby_version >= 2.6` which prevents users to use the gem if they are running their apps with a `Ruby 2.5`.

Is often good to only allow newer versions of the runtimes because they are maintained :sparkles: and there is always new features we can adopt in the code.

But, there is a price on that, when we make that cut, we reduce the amount of users that will be able to adopt our SDK/service.

List of current supported language version runtimes*:

| Language/Framework | Version |
| ------------------ | ------- |
| .NET | netstandard2.0 |
| Dart | >= 2.12.0 |
| Go | >= 1.16 |
| Java | >= 8.0 |
| JavaScript | N/A |
| Swift | >= 5.2 |
| PHP | >= 7.4 |
| Python | >= 3.7 |
| Ruby | >= 2.6 |
| Rust | N/A |

When a SDK drops a minium version, we will release a new MAJOR version.

\* This list may be outdated, always check the real version in the integration's repository.

## Correlation between Meilisearch engine versioning and the SDKs

Currently there is no plan to make every SDK be in the v1 state for some reasons:

- Not enough feedback data to validate if the public API we expose to the users is the best.
- Ability to evolve every SDK individually without being attached to the engine version.

It means there is no guarantee that since Meilisearch engine is v1 we will have: Meilisearch Dart v1, Meilisearch JavaScript v1, Meilisearch .NET v1 and so on... 
And also if we got a Meilisearch v2 in the future there is no guarantee that we will have Meilisearch Dart v2 as well.

What you can expect, is a table like this in every integration README:

| Meilisearch engine version | Integration version |
| ----------- | ----------- |
| v0.30 | v0.14.0 |
| v1.0 | v0.15.0 or later |
| v1.1 | v0.18.0 |

It means: The integration v0.15 will work with Meilisearch v1.1 running, but not all the new features introduced in the v1.1 will work in this integration version.


## When SDKs will be v1?

There is no real answer for this question, but the accurated guess is, when we feel confortable with the current state of the integration.
Or external facts that we may not control. So, if you want to only use v1 version of the SDKs please, open an issue in the integration-guides.


## Important facts

:warning: Most of the SDKs have methods like get `GetAllRawIndexesAsync`, `allRaw`, `rawSearch` and similar.

These methods have NO guarantee at all, since you're accessing directly the response given by the Meilisearch engine.
So, if possible don't use them.
