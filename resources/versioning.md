# Versioning policy

This page describes the versioning rules Meilisearch SDKs follow after the release of Meilisearch engine v1.0.0. It explains how and when the Integrations Team should increase the MAJOR, MINOR, and PATCH of the versions.

## 🤖 Basic rules

Meilisearch SDKs releases follow the [SemVer rules](https://semver.org/), including the following basic ones:

> 🔥 Given a version number MAJOR.MINOR.PATCH, increment the:
>
> 1. MAJOR version when you make incompatible API changes
> 2. MINOR version when you add functionality in a backwards compatible manner
> 3. PATCH version when you make backwards compatible bug fixes


**Changes that MAY lead the Meilisearch users (developers) to change their code are considered API incompatibility and will make us increase the MAJOR version of Meilisearch SDK.**

**In other terms, if the users MAY have to do more steps than just downloading the new Meilisearch package and running it, a new MAJOR is needed.**

Examples of changes making the code break and then, involving increasing the MAJOR:

- Any change related to the public API the SDK exposes like:
    - Renaming a method name or classes
    - Removing or changing a positional argument of a method.

## Reasons why releasing a major version is needed

### New runtimes adoption

There is no strict policy yet regarding the minimum support of the language version. Example:

Ruby SDK has a `required_ruby_version >= 2.6`, which prevents users from using the gem if they run their apps with a `Ruby 2.5`.

It is often good to only allow newer versions of the runtimes because they are maintained :sparkles: and there are always new features is possible to adopt in the code and improve maintenance time.

But there is a price for that. When that cut is made, the number of users who can adopt the SDK is reduced.

Currently, all supported versions are set in the CI of each repository.

This is the list of minimum supported language version runtimes*:

| Language/Framework | Version |
| ------------------ | ------- |
| .NET | netstandard2.0 |
| Dart | >= 2.12.0 |
| Go | >= 1.16 |
| Java | >= 8.0 |
| JavaScript/Node | >= 14 |
| Swift | >= 5.2 |
| PHP | >= 7.4 |
| Python | >= 3.7 |
| Ruby | >= 2.6 |
| Rust | N/A |

When an SDK drops a minimum required version of the runtime, a new MAJOR version of the SDK should be released.

\* This list may be outdated. Always check the current version in the integration's repository.

## Correlation between Meilisearch engine versioning and the SDKs

SDKs do not follow the Meilisearch engine version. It means that there is no correlation between SDK's version and Meilisearch; an SDK may be in version `v8.0.0` while the Meilisearch engine is in `v1.0.0`.

Suppose the version of an SDK is the same as the latest version of Meilisearch. It is just a happy coincidence.

You can find out which version of the Meilisearch engine an SDK is compatible with by going to the `Compatibility with Meilisearch` section of every SDK README page. For example, the [README](https://github.com/meilisearch/meilisearch-ruby/#-compatibility-with-meilisearch) page of the ruby SDK.

To illustrate, every repository will have a similar table like this:

| Meilisearch engine version | Integration version |
| -------------------------- | ------------------- |
| v0.30 | v0.14.0 |
| v1.0 | >= v0.15.0 |
| v1.1 | >= v0.18.0 |

Given the table above, a user using Meilisearch v1.1 does not need to have the v0.18 version of its SDK.
Of course, some features will not be present, but they should still work.

## When SDKs will be stable (v1)?

The Integrations Team is still working on making all of the SDKs stable, but there is no roadmap yet. First, some questions need to evolve, like having more feedback about the public API exposed to the users.

If you have a specific use case where you need the SDKs in v1, or if you want to share feedback about them, **please share it through the issues**.

## Important facts

:warning: Always check the Meilisearch engine version you are running and the version supported by your current SDK version.

:warning: If you use a `raw` method like `GetAllRawIndexesAsync`, `allRaw`, `rawSearch`, and similar. Please double-check the Meilisearch version you're running.

Since these methods' responses are made directly by the Meilisearch engine, the SDKs, may be unable to keep backward compatibility in a possible Meilisearch v2, for example. So, if possible, don't use them.
