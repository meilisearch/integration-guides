# Pre-Release Week <!-- omit in toc -->

> ### **What's the pre-release week?**
>
> One week before the official release of MeiliSearch, the Core team creates a release candidate (RC) version of MeiliSearch. For the integration team, the main purpose of this RC is to implement the new features (in the integrations tools) related to the next release by testing them against the RC version.
>
> So **the pre-release week is a sprint for the Integration team** who needs to complete all the tests and integrate most of the changes before the official release of MeiliSearch.
>
> The pre-release and release days are visible on the Meili/Team calendar (only available internally). A MeiliSearch release is out every 4 weeks.

Before any MeiliSearch release, and during the pre-release week, the following tasks should be done:

- [📌 First Preparations](#-first-preparations)
- [🧪 Testing](#-testing)
- [💬 Discussing](#-discussing)
- [💻 Coding](#-coding)
- [🥳 After the MeiliSearch official release](#-after-the-meilisearch-official-release)

## 📌 First Preparations

> ⚠️ All the following steps in this section should be done with the [meili-bot](https://github.com/meili-bot) credentials.

> 💡 Use [this script](https://github.com/meilisearch/integration-scripts/tree/main/release-pr-creator) (only available internally) to automate the following steps. *(WIP: this tool should handle the different points and the exceptions with a detailed guide to follow. For the moment only @curquiza will do this section.)*

- In each integration repository, create a draft PR modifying the old version of MeiliSearch into the future release version. The branch name originating this PR should be `bump-meilisearch-v*.*.*`. In most cases, only the `README.md` file changes.

- Create a draft PR in the [meilisearch-digitalocean](https://github.com/meilisearch/meilisearch-digitalocean) repository modifying the old MeiliSearch version **into the RC version**. This branch originating the PR should be named `bump-meilisearch-v*.*.*-test`. This branch is only created for test purposes and will be closed at the end of the pre-release week.

## 🧪 Testing

- **Test manually the RC** with a Core team member or on your own. Should be done by all the Integration team members.
- **Run all the SDKs automatic test suites against the RC** thanks to [this script](https://github.com/meilisearch/integration-scripts/tree/main/sdks-tests). If tests are not green, these should be justified.
- **Test manually the DO image with the RC** on the `bump-meilisearch-v*.*.*-test` branch by following the [testing process steps](https://github.com/meilisearch/meilisearch-digitalocean/blob/master/CONTRIBUTING.md#test-before-releasing) **without merging the branch or submitting the image.**

## 💬 Discussing

- **Open a new issue in [integration-guides](https://github.com/meilisearch/integration-guides/issues/new)** (labeled `MeiliSearch bump`) about the changes in the next release of MeiliSearch that will impact one or several integration tools. See [an issue example](https://github.com/meilisearch/integration-guides/issues/52).<br>
Based on the [MeiliSearch milestones](https://github.com/meilisearch/MeiliSearch/milestones), this issue should be divided into sub-sections for each feature/fix. These sub-sections explain in a concise way how the change impacts the integration tool(s) and how to fix/implement it if necessary.<br>
If a change involves a huge implementation in the integration tools, a separated issue can be created and linked to the main issue.

- **Discuss and approve the issue**. All the Integration team members are requested. The 🚀 emoji means approval.

## 💻 Coding

For each implementation or fix:

- **Create a PR** up-to-date with `bump-meilisearch-v*.*.*` and pointing to `bump-meilisearch-v*.*.*` with all the changes.
- **Make all the tests green**: the tests are running against the RC and not the latest stable version of MeiliSearch.<br>
If they don't pass all, please explain the reason: another PR concerning other changes might indeed be needed.
- **Ask for reviews**.
- **Merge the PR** with the `Squash and Merge` button once you get an approval.<br>
Don't use Bors: this tool would not run the tests against the RC so will not merge your PR.<br>
Some tests still might fail on this main PR until the new release of MeiliSearch is out.

## 🥳 After the MeiliSearch official release

- Close the PR originating the `bump-meilisearch-v*.*.*-test` branch in [meilisearch-digitalocean](https://github.com/meilisearch/meilisearch-digitalocean/pulls).
- Merge all the PRs in the repositories that **don't** depend on other integration packages (e.g. do **not** merge meilisearch-laravel-scout or docs-scraper):
  - Make the PRs ready for review (change the draft status).
  - Run the tests with the `bors try` command.
  - Ask for or/and do a final reviews.
  - Merge the PRs with Bors (`bors merge`).
- Release the just-modified packages if necessary. Follow the steps in the [release process guide](./integration-tool-release.md).
- For the repositories depending on other integration packages: upgrade the dependency, commit to `bump-meiliserch-v*.*.*` and merge the PR with the same process than above.
- Release these packages if necessary. Follow the steps in the [release process guide](./integration-tool-release.md).
- Close the related issue in [integration-guides](https://github.com/meilisearch/integration-guides/issues). If some features have not been integrated into one or several integration tools, issues about the implementations must be opened in the concerned repositories before closing the main issue in integration-guides.
