---
name: New central issue
about: ⚠️ Should only be used by the internal Meili team ⚠️
title: 'Changes related to Meilisearch v1.Y.0'
labels: 'Meilisearch bump'
assignees: 'curquiza, brunoocasali'
---

This issue gathers the changes related to the v1.Y.0 of Meilisearch that will impact the integrations scope.

📅 Release date: TBD

## Timelines & steps

### Pre-release

- [ ] With the help of the [changelog](https://github.com/meilisearch/engine-team/pulls) &  [this CI](https://github.com/meilisearch/meilisearch/actions/workflows/sdks-tests.yml), define which integrations should be updated and how (New feature? Update README? Update tests?)
  - [ ] **Fill in** the "What to implement?" section below in this issue 👇. Minial implementation: PHP, JS, Instant-meilisearch.
  - [ ] Open implementation issues in repositories that need implementation.
  - [ ] Discuss with the Product team if needed. At least share this issue to let them know about the decisions.
- [ ] Create a branch by running [Octopus script](https://github.com/meilisearch/integration-automations/tree/main/octopus): only open branches for the integrations we choose to update (defined in the previous step) + Kubernetes repository + Cloud provider repository (changing the version)
- [ ] Update integrations according to the decisions (cf "What to implement?" section below in this issue 👇)
⚠️ If possible, this step is done before pre-release, once the feature is ready thanks to the prototype released by the engine team
  - [ ] JS
  - [ ] PHP
  - [ ] ... TBD
- [ ] Add code samples for the chosen up-to-date integrations with the new version of Meilisearch
- [ ] Update the library version of the related integrations and prepare the changelogs

### Release day

- [ ] Release the integrations or only merge the related PRs (sometimes a release is not needed)
  - [ ] JS
  - [ ] PHP
  - [ ] Instant-meilisearch (at least update meilisearch-js version)
  - [ ] ... TBD
- [ ] Merge the related PR in [K8s repository](https://github.com/meilisearch/meilisearch-kubernetes/pulls)
- [ ] Publish [DevOps tools](https://github.com/meilisearch/cloud-providers/):
  - [ ] create the git tag
  - [ ] publish images (steps are in CONTRIBUTING.md)
- [ ] Remove useless AWS images (by using our [internal script](https://github.com/meilisearch/integration-automations/tree/main/cloud-providers))
- [ ] Open issues in the repositories that are not up-to-date with the latest version of Meilisearch (**including code samples**)

## What to implement?

### <Template: feature name>

Related issue in the engine:

Brief explanation of the feature and the impact potential impact on the integrations

TODO:
- [ ] JS: TBD
- [ ] PHP: TBD
- [ ] ... TBD
