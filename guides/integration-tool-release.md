# Releasing an Integration Tool

This guide is about releasing integration tools and has nothing to do with MeiliSearch releases that are handled during the [pre-release week](./pre-release-week.md).

> ⚠️ Integration tool releases are public and are certainly among our most consulted contents with the READMEs.<br>
> Indeed, users reading the release changelogs are mostly users wanting to upgrade their dependencies, so they might consult the release description really carefully.
>
> **The Integration team should keep this in mind during the release process.**

### Why Doing a Release?

First of all, you need to check the release would include user-oriented changes. A release is not always needed after merging PRs.<br>
Don't do a release without any usage purpose, for example for the update of a text file/test/CI or for an internal refacto.

📢 **A release should be done only when there are changes concerning the code usage.**

### And Next?

Follow the steps in the `Release Process` section in the `CONTRIBUTING.md` file of the repository carefully. These steps should be precise; if it's not, please open an issue on the related repository.

During these steps, you might publish a release via the GitHub interface and so provide a description with the release changelogs.<br>
The [Release Drafter tool](./release-drafter.md), integrated into most repositories, helps you provide a kind of structure, but please, feel free to add final modifications to ensure these changelogs are:
- **accurate**: describe what changed, with links to the PRs, and the consequences of the changes if needed. Also, check all the breaking changes are in the `Breaking Changes` section.
- **user-friendly**: add documentation links if necessary.
- **user-oriented**: do not add changelogs that do not impact the code usage (e.g., internal refacto, documentation, tests, CI modifications).
- **contributor-friendly**: thank all the contributors, especially the ones who don't appear on the changelogs because they helped on the tests or the documentation.

Also, when writing the final changelogs, you might notice some inconsistencies, e.g., a PR that should have been identified as a breaking change or a PR that should not appear in the changelogs: please, do not update the release description manually. Instead:
- Go to the related PR.
- Add the missing label (`breaking-change` or `skip-changelog`).
- Re-run the last `Release Drafter` job in the `Actions` tab of the repository.

**This keeps consistency between the PRs history and the release changelogs**.
