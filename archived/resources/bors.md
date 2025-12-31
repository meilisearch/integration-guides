# Bors: a Merge Bot for PRs

[Bors](https://github.com/bors-ng/bors-ng) is a tool that helps us manage pull requests (PR) merging.

## Motivations

One of our requirements to merge a PR is that a contributor branch has to be up-to-date with the upstream `main` branch.<br>
The only proper way to keep the Git history clear is to rebase the branch originating the PR.

It became tedious always to ask the contributors to rebase their branch when their branch was not up-to-date with `main` because:
- It forces everyone to wait again before the merge
- It is not always easy to successfully apply a rebase without any issue
- Sometimes, there are several PRs ready to be merged, which introduces complexity in coordination

### But why rebasing?

The goal of a rebase to move the commits (from the PR branch) right after the last commit on `main`.<br>
Therefore, rebasing keeps your Git history clear and consistent with the order in which you have merged your PRs. Making the PR branch up-to-date by adding merge commits does not keep this clarity.

Keeping in mind that the Git history is essential, rebasing is the only way to guarantee that the work that will be merged fits the current work in production. If the tests pass on an up-to-date branch, it ensures they will pass once merged into `main`, assuring your production branch will not break.

## How does Bors work?

Bors is a bot that automatically applies a rebase before running the tests and merging if they succeed.<br>
This allows us to _automatically maintain a repository of code that always passes all the tests_ (cf [this article](https://graydon2.dreamwidth.org/1597.html) by the creator of Bors)

### Usage

All the Bors commands have to be given through comments in the PR.

#### Simple Check

To check the PR passes all the tests when up-to-date with `main`, use:

```
bors try
```

![bors try](../assets/screenshots/bors_try.png)

**This command is only useful when the PR is not up-to-date with `main`**, but the reviewers want to be sure the changes do not break the current code in production.<br>
No merge is going to be done with this command.

#### Automatic Merge

To rebase and merge the PR, use the following:

```
bors merge
```

![bors merge](../assets/screenshots/bors_merge.png)

Bors will check that the PR passes the tests when up-to-date with `main` and then merge the rebased work.

💡 Bors is also able to manage multiple merging PRs at the same time. Each PR is added to a queue and will be checked with the last version on `main`.

### More Details

Bors does not concretely rebase the branch of the PR: it merges the commits of the PR into another branch that is already up-to-date with `main`:

- `trying` when doing a `bors try`
- `staging` when doing a `bors merge`

If the tests do not pass on one of these branches, Bors returns a failure and stops the merge of the PR (if doing a `bors merge`)

### Limitation

Bors cannot work when there are Git conflicts. Indeed, when Git conflicts with the `main` branch are present, Bors cannot decide what the contributor wants to do.

In this situation, the contributor has to rebase the branch manually. Check out this [quick tutorial](https://gist.github.com/curquiza/5f7ce615f85331f083cd467fc4e19398) to apply the rebase from a forked repository.
