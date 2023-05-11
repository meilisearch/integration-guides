# Issues

## Create a new issue

Here is the process when opening issues for the integration repositories:
- If your issue concerns all the integration repositories or many of them (all the DevOps tools, for example): open an issue in [integration-guides](https://github.com/meilisearch/integration-guides/issues/new).
- If your issue concerns a specific repository: open it directly in the concerned repository.

## Issue labeling in integration-guides

This paragraph describes the labels used for the issues in this repository (integration-guides).

The five following labels make us track the current state of an issue, from the beginning of the idea until the implementation:
- `need discussion`: for every idea that needs to be discussed or clarified before any clear suggestion.
- `need vote`: an issue is opened, and several suggestions are available. The opinion of the different team members is required.
- `need approval`: an idea is submitted and is waiting for approval. Of course, the other team members can discuss it and suggest another possibility.
- `ready to implement`: a consensus has been found, and the solution is ready to be implemented.
- `wip`: the issue is being implemented (this is the last label before the issue is closed)

The following labels help us categorize the issues:
- `Meilisearch bump`: tracking issue related to a bump of Meilisearch. It describes the impacts to the integration repositories leads by a new Meilisearch release.
- `new integration`: the issue concerns a new integration.
- `JS integrations`: the issue concerns some or all the JS repositories (ex: meilisearch-js, instant-meilisearch, docs-search.js...)
- `DevOps tools`: the issue concerns the DevOps repository (ex: cloud-providers)
- `SDKs`: the issue concerns some or all the SDKs (ex: meilisearch-js, meilisearch-ruby...)

## Issue assignation policy

We prefer not assigning external people to our issues.<br />
Because people often ask to be assigned and never return, which discourages other potential contributions. <br />
We will accept and merge the first PR that fixes correctly and implements the issue. <br />

## Message templates (to be used by the Integrations Team members)

**When the contributor asks to be assigned into the issue**

Hi \@username, we prefer not assigning external people to our issues.

Why? People often ask to be assigned and never return, discouraging the volunteer contributors from opening a PR to fix the issue.

We will accept and merge the first PR that fixes correctly and implements the issue following the contribution guidelines of the corresponding repository.

We are looking forward to your contributions. No need to wait for an assignment to start! :+1:

**When the contributor suggests an improvement in a low level tier.**

Hey \@username.
I agree with implementing this!

We might not have enough time to work on it in the following weeks. Also, I will add some details to this issue to make the implementation easier.
If someone wants to contribute and implement it, it will be released faster! PRs are always welcome!
