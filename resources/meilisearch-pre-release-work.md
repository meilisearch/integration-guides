# Integration work related to Meilisearch pre-release

Every eight weeks, the engine team releases a new version of the Meilisearch engine. The last four weeks are the "pre-release time" where no new additions are made by the engine team, and release candidates (RCs) are done.

For each Meilisearch release, a central issue should be opened in the [integration-guide repository](https://github.com/meilisearch/integration-guides/issues). This central issue is an exhaustive list of the changes applied to the integration scope related to the future release of Meilisearch.

👇👇👇 Here is the template of the central issue to copy & paste. Replace the `TBD`. 👇👇👇

---

This issue gathers the changes related to the vX.Y.0 of Meilisearch that will impact the integrations scope.

📅 Release date: TBD

## TODO

### Pre-release

- [ ] Define (with the help of PMs) which integrations should be updated to include the new features in the latest version of Meilisaearch. Most of the time, it will be tier #1 integrations.
Integration to update: TBD
- [ ] With the help of [this CI](https://github.com/meilisearch/meilisearch/actions/workflows/sdks-tests.yml) running on `rc0`, define in which SDKs we have to update the tests
- [ ] Create a branch by running [Octopus script](https://github.com/meilisearch/integration-automations/tree/main/octopus): only open branches for the integrations we choose to update + Kubernetes repository + Cloud provider repository (changing the version) + SDKs/integrations where we must update the test suite.
- [ ] Update integrations according to the new Meilisearch features (cf below which feature and how 👇)
⚠️ If possible, this step is done before pre-release, once the feature is ready thanks to the prototype released by the engine team
  - [ ] TBD
- [ ] Update integrations having failing test suites with the new RC of Meilisearch (refer to this [CI](https://github.com/meilisearch/meilisearch/actions/workflows/sdks-tests.yml))
  - [ ] TBD
- [ ] Add code samples for the chosen up-to-date integrations with the new version of Meilisearch
- [ ] Update the library version of the related integrations and prepare the changelogs

### Release day

- [ ] Release the integrations
- [ ] Merge the related PR in [K8s repository](https://github.com/meilisearch/meilisearch-kubernetes/pulls)
- [ ] Publish [DevOps tools](https://github.com/meilisearch/cloud-providers/):
  - [ ] create the git tag
  - [ ] publish images (steps are in CONTRIBUTING.md)
- [ ] Open issues in the repositories that are not up-to-date with the latest version of Meilisearch (**including code samples**)

## Features to implement

*TBD: here list the features, link the related specs/issues/PRDs, and some implementation details if necessary*

---
