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

### Skip the PR

If you don't want a PR to appear in the release changelogs: add the label `skip-changelog`.

We suggest removing PRs updating the README or the CI. Users don't need this kind of information when updating the package.

### The PR adds a new feature

⚠️ Only for integrations that has a major version release (`1.x.x`, `2.x.x`).

If the PR introduces a new feature: add the label `new-feature`

the PR is made has already a major version , then, a `Pull request` introducing a new feature should have the `new-feature` label.  

Ex: `1.1.3` -> `1.2.0`

### The PR implies breaking changes

If the changes you are doing in the PR are breaking: add the label `breaking-change`.

### SemVer and Versioning

MeiliSearch tools follow the [Semantic Versioning Convention](https://semver.org/). Based on the chosen labels for a PR, the release-drafter will automatically increase the right number in the version. 

#### In integrations with no major release (`0.x.x`)

- `skip-changelog` or no labels does not impact versioning, except if it is the first accepted PR. In which case, the `patch` number increases.
- `breaking-changes` increases the minor version automatically, ex: `0.2.3` -> `0.3.0`

#### In integrations with a major release ((`1.x.x`, `2.x.x`)

- `skip-changelog` or no labels, does not impact versionning, except if it is the first accepted PR. In which case, the `patch` number increases.
- `new-feature`: Increases the minor version automatically, ex: `0.2.3` -> `0.3.0`
- `breaking-changes` Increases the major version automatically, ex: `1.2.4` -> `2.0.0`

The order is important as `breaking-change` will override the version change of a `new-feature`. If both labels are present in a release, only the major version increases.

Integrations with a major release are an exception. Other integrations will have no major release until [MeiliSearch](https://github.com/meilisearch/MeiliSearch) is stable.

### Other Recommendations

- As the draft release description is generated on every push on `main`, don't change it manually until the final release publishment. Otherwise, your manual changes are going to be overwritten.
- If you made any mistake (for example, the PR is already closed, but you forgot to add a label or you misnamed your PR), don't panic: change what you want in the closed PR and run the job again.

> 💡 How to re-run the "Release Drafter" job?
> - Go to the `Action` tab.
> - Click on the left sidebar `Release Drafter`.
> - Select the latest action.
> - At the top right part of the screen click on `Re-run all jobs`.
