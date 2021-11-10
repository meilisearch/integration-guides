# Changelogs Automation: the Release-Drafter

The [release-drafter](https://github.com/release-drafter/release-drafter/) tool is used in our GitHub Actions to automatize the content of each release description, so the changelogs.

## Motivations

We maintain a lot of packages and plugins implying several releases that we have to publish regularly.<br>
Our users need to know exactly and clearly what changed in the new release. That's why the changelogs are important and must be accurate.

Of course, it is tedious to manually write the changelogs without any omissions, and this task can easily be automated.

## How does the Release-Drafter work?

For each PR merged on `main`, a GitHub Action is run: it updates the next release description as a draft release in the [GitHub interface](https://github.com/meilisearch/meilisearch-ruby/releases).<br>
If you don't have the right access to this repository, you will not be able to see the draft release until the release is published.

The draft release description is therefore generated and corresponds to all the PRs titles since the previous release. **This means each PR should only do one change, and the title should be descriptive of this change**.

### SemVer and Versioning

MeiliSearch tools follow the [Semantic Versioning Convention](https://semver.org/). Based on the chosen labels for a PR, the release-drafter automatically increases the right number in the version.

### Skip the PR

If you don't want a PR to appear in the release changelogs: add the label `skip-changelog`.

We suggest removing PRs updating the README or the CI. Users don't need this kind of information when updating the package.

### The PR adds a new feature

⚠️ Only for integrations that have a major release version (e.g. `1.x.x`, `2.x.x`).

If the PR introduces a new feature: add the label `new-feature`.

The minor version of the release increases.
Ex: `0.1.4` -> `0.2.0`

### The PR implies breaking changes

If the changes you are doing in the PR are breaking: add the label `breaking-change`.

- If the integration is not stable (e.g. `0.X.Y`) the minor version increases.
Ex: `0.1.4` -> `0.2.0`

- If the integration is stable (e.g. `X.Y.Z` when `X > 0`) the major version increases.
Ex: `2.1.4` -> `3.0.0`

### Other Recommendations

- As the draft release description is generated on every push on `main`, don't change it manually until the final release publishment. Otherwise, your manual changes are going to be overwritten.
- If you made any mistake (for example, the PR is already closed, but you forgot to add a label or you misnamed your PR), don't panic: change what you want in the closed PR and run the job again.

> 💡 How to re-run the "Release Drafter" job?
> - Go to the `Action` tab.
> - Click on the left sidebar `Release Drafter`.
> - Select the latest action.
> - At the top right part of the screen click on `Re-run all jobs`.
