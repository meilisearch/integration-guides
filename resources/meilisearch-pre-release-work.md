# Integration work related to Meilisearch pre-release

Every eight weeks, the engine team releases a new version of the Meilisearch engine. The last four weeks are the "pre-release time" where no new additions are made by the engine team, and release candidates (RCs) are done.

For each Meilisearch release, a central issue should be opened in the [integration-guide repository](https://github.com/meilisearch/integration-guides/issues). This central issue is an exhaustive list of the changes applied to the integration scope related to the future release of Meilisearch.

👇👇👇 Here is the template of the central issue to copy & paste. Replace the `TBD`. 👇👇👇

---

This issue gathers the changes related to the vX.Y.0 of Meilisearch that will impact the integrations scope.

📅 Release date: TBD

## Timelines & steps

### Pre-release

- [ ] With the help of the Product team and [this CI](https://github.com/meilisearch/meilisearch/actions/workflows/sdks-tests.yml), define which integrations should be updated and how (New feature? Update README? Update tests?) -> **Fill in** the "What to implement?" section below in this issue 👇.
- [ ] Create a branch by running [Octopus script](https://github.com/meilisearch/integration-automations/tree/main/octopus): only open branches for the integrations we choose to update (defined in the previous step) + Kubernetes repository + Cloud provider repository (changing the version)
- [ ] Update integrations according to the decisions (cf "What to implement?" section below in this issue 👇)
⚠️ If possible, this step is done before pre-release, once the feature is ready thanks to the prototype released by the engine team
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

## What to implement?

### Template: feature name

Related issue in the engine:

Brief explanation of the feature and the impact potential impact on the integrations

TODO:
- [ ] JS: TBD
- [ ] PHP: TBD
- [ ] TBD

The following integrations will not have the feature available for the release day: TBD

---
