# Pre-Release Week <!-- omit in toc -->

> ### **What's the pre-release week?**
>
> Four weeks before the official release of Meilisearch, the Engine Team creates a release candidate (RC) version of Meilisearch. For the Integrations Team, the main purpose of this RC is to implement the new features (in the integrations tools) related to the next release by testing them against the RC version.
>
> So **the pre-release week is a sprint for the Integrations Team** who needs to complete all the tests and integrate most of the changes before the official release of Meilisearch.
>
> The pre-release and release days are visible on the Meili/Team calendar (only available internally). A Meilisearch release is out every 8 weeks.

Before any Meilisearch release, and during the pre-release week, the following tasks should be done:

- [💬 Discussing](#-discussing)
- [📌 First Preparations](#-first-preparations)
- [🧪 Testing](#-testing)
- [💻 Coding](#-coding)
- [🥳 After the Meilisearch official release](#-after-the-meilisearch-official-release)

## 💬 Discussing

> 💡 This step can be done before the beginning of the pre-release week by actively following the Meilisearch's Milestones and issues.

- **Open a new issue in [integration-guides](https://github.com/meilisearch/integration-guides/issues/new)** (labeled `Meilisearch bump`) about the changes in the next release of Meilisearch that will impact one or several integration tools. See [an issue example](https://github.com/meilisearch/integration-guides/issues/52).<br>
Based on the [Meilisearch milestones](https://github.com/meilisearch/meilisearch/milestones), this issue should be divided into sub-sections for each feature/fix. These sub-sections explain in a concise way how the change impacts the integration tool(s) and how to fix/implement it if necessary.<br>
If a change involves a huge implementation in the integration tools, a separated issue can be created and linked to the main issue.

- **Discuss and approve the issue**. All the Integrations Team members are requested.

## 📌 First Preparations

> 💡 Use [this script](https://github.com/meilisearch/integration-scripts/tree/main/pre-release-script) (only available internally) to automate the following steps. Please read carefully the README of this tool before applying any changes.

The script automates the following tasks:

- In each integration repository, create a blank draft PR. The branch name originating this PR should be `bump-meilisearch-vX.X.X`. In most cases, only the `README.md` file changes.
- In the [cloud-scripts](https://github.com/meilisearch/cloud-scripts) repository, create a branch named `bump-meilisearch-vX.X.X-rc` where the old version of Meilisearch is changed **into the RC version**. Also, create a tag named `vX.X.X-rc` on this commit and push it.

## 🧪 Testing

- **Test manually the RC** with a Engine team member or on your own. Should be done by all the Integration team members.
- **Test manually the [DigitalOcean](https://github.com/meilisearch/meilisearch-digitalocean), [AWS](https://github.com/meilisearch/meilisearch-aws/) and [GCP](https://github.com/meilisearch/meilisearch-gcp) images with the RC** by following the `Test before Releasing` steps **without submitting or publishing the image**:
  - [testing process steps of `meilisearch-digitalocean`](https://github.com/meilisearch/meilisearch-digitalocean/blob/main/CONTRIBUTING.md#test-before-releasing-)
  - [testing process steps of `meilisearch-aws`](https://github.com/meilisearch/meilisearch-aws/blob/main/CONTRIBUTING.md#test-before-releasing-)
  - [testing process steps of `meilisearch-gcp`](https://github.com/meilisearch/meilisearch-gcp/blob/main/CONTRIBUTING.md#test-before-releasing-)

## 💻 Coding

⚠️ [`meilisearch-js`](https://github.com/meilisearch/meilisearch-js) and [`instant-meilisearch`](https://github.com/meilisearch/instant-meilisearch/) implementations should start as soon as possible since:
- they are dependencies of the [`mini-dashboard`](https://github.com/meilisearch/mini-dashboard).
- they may raise bad design choices or relevancy issues of the Meilisearch API when used in front-end.

For each implementation or fix:

- **Create a PR** up-to-date with `bump-meilisearch-vX.X.X` and pointing to `bump-meilisearch-vX.X.X` with all the changes.
- **Make all the tests green**: the tests are running against the RC and not the latest stable version of Meilisearch.<br>
If they don't pass, please explain the reason: another PR concerning other changes might indeed be needed.
- **Ask for reviews**: the team member responsible to make the review [is written here](https://github.com/meilisearch/integration-guides/blob/main/resources/scopes.md).
- **Merge the PR** with the `Squash and Merge` button once you get an approval.<br>
Don't use Bors: this tool would not run the tests against the RC so will not merge your PR.<br>
Some tests still might fail on this main PR until the new release of Meilisearch is out.

## 🥳 After the Meilisearch official release

- Remove the `bump-meilisearch-vX.X.X-rc` branch and the `vX.X.X-rc` tag from the [cloud-scripts](https://github.com/meilisearch/cloud-scripts) repository. Both removals can be done via the GitHub interface for every Integration team member.
- Merge all the PRs in the repositories that **don't** depend on other integration packages (e.g. do **not** merge meilisearch-symfony or docs-scraper):
  - Make the PRs ready for review (change the draft status).
  - Run the tests with the `bors try` command.
  - Ask for or/and do a final reviews.
  - Merge the PRs with Bors (`bors merge`).
- Release the just-modified packages if necessary. Follow the steps in the [release process guide](./integration-tool-release.md).
- For the repositories depending on other integration packages (like meilisearch-rails or instant-meilisearch): upgrade the dependency, commit to `bump-meilisearch-vX.X.X` and merge the PR with the same process than above.
- Release these packages if necessary. Follow the steps in the [release process guide](./integration-tool-release.md).
- Close the related issue in [integration-guides](https://github.com/meilisearch/integration-guides/issues) only when the original plan was achieved. 
  - Open new issues in all the repositories which were not part of the planned tiers. E.g., since most features are not done in tier #3, issues should be opened in those repositories.
- The Integration team does a retrospective meeting internally to take notes on what went well and what did not and improve it for the next time.
