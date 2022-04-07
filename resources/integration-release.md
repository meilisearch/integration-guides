# Releasing an Integration

This guide is about releasing integrations and has nothing to do with Meilisearch releases that are handled during the [pre-release week](./pre-release-week.md).

> ⚠️ Integration releases are public and are certainly among our most consulted contents with the READMEs.<br>
> Indeed, users reading the release changelogs are mostly users wanting to upgrade their dependencies, so they might consult the release description really carefully.
>
> **The Integration team should keep this in mind during the release process.**

## Why Doing a Release?

First of all, you need to check the release would include user-oriented changes. A release is not always needed after merging PRs.<br>
Don't do a release without any usage purpose, for example for the update of a text file/test/CI or for an internal refacto.

📢 **A release should be done only when there are changes concerning the code usage.**

## Let's Release!

Follow the steps in the `Release Process` section in the `CONTRIBUTING.md` file of the repository carefully. These steps should be precise; if it's not, please open an issue on the related repository.

### Writing the Release Description

During these release steps, depending on the integration, releasing is done via the GitHub interface. The release comes with a description containing the changelogs. <br>
The [Release Drafter tool](./release-drafter.md), integrated into most repositories, provides a release description structure containing the changelogs. Please add additional content in the release description to ensure these changelogs are:
- **accurate**: describe what changed, with links to the PRs, and the consequences of the changes if needed. Also, check all the breaking changes are in the `Breaking Changes` section.
- **user-friendly**: add documentation links if necessary.
- **user-oriented**: do not add changelogs that do not impact the code usage (e.g., internal refacto, documentation, tests, CI modifications).
- **contributor-friendly**: thank all the contributors, especially the ones who don't appear on the changelogs because they helped on the tests or the documentation.

Also, when writing the final changelogs, you might notice some inconsistencies, e.g., a PR that should have been identified as a breaking change or a PR that should not appear in the changelogs: in this case, please, do not update the release description manually. Instead:
- Go to the related PR.
- Add the missing label (`breaking-change`, `new-feature` or `skip-changelog`, [see guide](./release-drafter#how-does-the-release-drafter-work)).
- Re-run the last `Release Drafter` job in the `Actions` tab of the repository.

> 💡 How to re-run the "Release Drafter" job?
> - Go to the `Action` tab.
> - Click on the left sidebar `Release Drafter`.
> - Select the latest action.
> - At the top right part of the screen click on `Re-run all jobs`.

**This keeps consistency between the PRs history and the release changelogs**.

## What to do when Failing a Release?

In some repositories, [GitHub Actions are triggered](https://github.com/meilisearch/meilisearch-js/blob/main/.github/workflows/publish.yml) after a tag creation following the release publication. It might happen that one of these actions failed because pre-requisites are not met (i.e., the new version in the correct file). Don't worry; it is fixable! These are the steps:

1. Delete the release: go to the "Releases" section on GitHub, then click on the latest release and then on "Delete" in the upper right corner.
2. Delete the tag (`v0.X.Y`):  go to the "Releases" section on GitHub, then click on the "Tags" section, go to the latest tag, click on "Delete" in the upper right corner.
3. Merge the PR with the missing pre-requisites (i.e., adding the current version in the correct file).
4. Once the merge completes, a new release draft is created. You can now publish it!

**Failure situation example**

I release `meilisearch-js@v0.2.0` but I forgot to update the version in my `package.json`. On release, the [`publish to npm`]((https://github.com/meilisearch/meilisearch-js/blob/main/.github/workflows/publish.yml)) GitHub Action is triggered. A test is done to check if the version in `package.json` is the same as the `tag` created by the GitHub release. In this case, `v0.1.0` in my package.json and `v0.2.0` as a tag; thus, the GitHub Action stops, and my package is not published to [npm](https://www.npmjs.com/).

The situation is as follows: `meilisearch-js@v0.2.0` is released on GitHub, the tag `v0.2.0` is created, but it is not published on [npm](https://www.npmjs.com/) which is still at `v0.1.0`.

To solve the situation, I delete the release and the tag on GitHub. I merge the PR with the right version in `package.json`. I go back to the release screen, and I publish the newly created release draft.

## What to do when publishing a broken package?

It might happen that the release worked but the published package on the package manager is broken (completely unusable). In this specific case, some steps must be followed.

⚠️ This only applies when the published package is completely broken. If the package works but bugs were introduced a patch is enough.

If the package was published recently:

1. Delete/deprecate the package in the package manager (ex: `npm deprecate meilisearch@0.1.0 "Missing files breaks the package"`).
2. Follow step one and two of the previous section [What to do when Failing a release](#what-to-do-when-failing-a-release).
3. Fix the package.
4. Increase the patch version (ex: 0.1.0 becomes 0.1.1).
5. Once the merge is completed, a new release draft is created. You can now publish it!

If the package was not published recently:
1. Deprecate the package in the package manager.
2. Write in the body of the broken release that this version is deprecated.
3. Fix the package.
4. Increase the patch version (ex: 0.1.0 becomes 0.1.1).
5. Once the merge completes, a new release draft is created. You can now publish it!


## Release a beta version

For some integrations, we need to release a beta version of the integration before releasing the official one. For instance, during the Meilisearch pre-release, we often need to release a beta version of [meilisearch-js](https://github.com/meilisearch/meilisearch-js) to make the [mini-dashboard](https://github.com/meilisearch/mini-dashboard)) work with the future release of Meilisearch.

Please, follow the instructions detailed in the CONTRIBUTING.md of the repository to release a beta version.
