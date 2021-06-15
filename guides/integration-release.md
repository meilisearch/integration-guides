# Releasing an Integration

This guide is about releasing integrations and has nothing to do with MeiliSearch releases that are handled during the [pre-release week](./pre-release-week.md).

> ⚠️ Integration releases are public and are certainly among our most consulted contents with the READMEs.<br>
> Indeed, users reading the release changelogs are mostly users wanting to upgrade their dependencies, so they might consult the release description really carefully.
>
> **The Integration team should keep this in mind during the release process.**

### Why Doing a Release?

First of all, you need to check the release would include user-oriented changes. A release is not always needed after merging PRs.<br>
Don't do a release without any usage purpose, for example for the update of a text file/test/CI or for an internal refacto.

📢 **A release should be done only when there are changes concerning the code usage.**

### And Next?

Follow the steps in the `Release Process` section in the `CONTRIBUTING.md` file of the repository carefully. These steps should be precise; if it's not, please open an issue on the related repository.

#### Writing the Release Description

During these release steps, depending on the integration, releasing is done via the GitHub interface. The release comes with a description containing the changelogs. <br>
The [Release Drafter tool](./release-drafter.md), integrated into most repositories, provides a release description structure containing the changelogs. Please add additional content in the release description to ensure these changelogs are:
- **accurate**: describe what changed, with links to the PRs, and the consequences of the changes if needed. Also, check all the breaking changes are in the `Breaking Changes` section.
- **user-friendly**: add documentation links if necessary.
- **user-oriented**: do not add changelogs that do not impact the code usage (e.g., internal refacto, documentation, tests, CI modifications).
- **contributor-friendly**: thank all the contributors, especially the ones who don't appear on the changelogs because they helped on the tests or the documentation.

Also, when writing the final changelogs, you might notice some inconsistencies, e.g., a PR that should have been identified as a breaking change or a PR that should not appear in the changelogs: in this case, please, do not update the release description manually. Instead:
- Go to the related PR.
- Add the missing label (`breaking-change`, `new feature` or `skip-changelog`, [see guide](./release-drafter#how-does-the-release-drafter-work)).
- Re-run the last `Release Drafter` job in the `Actions` tab of the repository.

> 💡 How to re-run the "Release Drafter" job?
> - Go to the `Action` tab.
> - Click on the left sidebar `Release Drafter`.
> - Select the latest action.
> - At the top right part of the screen click on `Re-run all jobs`.

**This keeps consistency between the PRs history and the release changelogs**.
