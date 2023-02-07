# Versioning policy

This page describes the versioning rules Meilisearch SDKs follow after the release of Meilisearch engine v1.0.0. It explains how and when we should increase the MAJOR, MINOR, and PATCH of the versions.

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

## Reasons why we should release a major version

### New runtimes adoption

We don't have a strict policy yet regarding the minimum support of the language version. Example:

Ruby SDK has a `required_ruby_version >= 2.6`, which prevents users from using the gem if they run their apps with a `Ruby 2.5`.

It is often good to only allow newer versions of the runtimes because they are maintained :sparkles: and there are always new features we can adopt in the code.

But there is a price for that. When we make that cut, we reduce the number of users who can adopt our SDK/service.

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

When an SDK drops a minimum required version of the runtime, we will release a new MAJOR version of the SDK.

\* This list may need to be updated. Always check the actual version in the integration's repository.

## Correlation between Meilisearch engine versioning and the SDKs

We're still planning to make the SDKs stable, but first, we would like to evolve some questions, like having more feedback about the public API we expose to the users.
So, expect different major version numbers between the Meilisearch engine and the SDKs.

It means there is no guarantee that since the Meilisearch engine is v1, we will have: Meilisearch Dart v1, Meilisearch JavaScript v1, Meilisearch .NET v1, and so on...
And also, if we get a Meilisearch v2 in the future, there is no guarantee that we will have Meilisearch Dart v2.

To illustrate, the idea is to have a similar table in every repository.

| Meilisearch engine version | Integration version |
| -------------------------- | ------------------- |
| v0.30 | v0.14.0 |
| v1.0 | >= v0.15.0 |
| v1.1 | v0.18.0 |

Given the example above, it means that the integration in v0.15 works with Meilisearch v1.1, but may only some of the new features introduced in v1.1 will work with this integration version.

## When to we update SDKs to v1?

We are getting closer to a possible v1 in the SDKs, but there has yet to be a real roadmap.
If you have a specific use case where you need the SDKs in v1, please let us know through the issues.

## Important facts

:warning: Always check the Meilisearch engine version you are running and the version supported by your current SDK version.

:warning: If you use a `raw` method like `GetAllRawIndexesAsync`, `allRaw`, `rawSearch`, and similar. Please double-check the Meilisearch version you're running.

Since these methods' responses are made directly by the Meilisearch engine, we, the SDKs, may be unable to keep backward compatibility in a possible v2, for example. So, if possible, don't use them.
