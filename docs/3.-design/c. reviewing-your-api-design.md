# Reviewing API Design

When you're a solo developer working on an API design, the process is pretty simple:

1. Make some changes
2. They're great
3. Ship it

When multiple developers are working on the API, and when multiple teams are all making multiple APIs, quality control can suddenly feel more important.

## What to Look Out For

**Are there breaking changes?**

API reviewers will want to look out for changes that: remove endpoints, rename a properties, change the data type of existing properties, remove enum values, or any other sort of breaking change.

**Does the terminology make sense?**

Is the term "account" being introduced to describe users, when other parts of the API ecosystem at your organization use it for "companies" or maybe even financial reasons? Is there maybe a better term that could be used?

**Is this consistent?**

API consumers generally don't enjoy guessing subtle differences between various APIs from the same organization, and they shouldn't need to. 

- If one API uses JSON:API and another uses Siren, maybe that's something to call out. 
- If one uses camelCase for properties and another uses snake_case, maybe that could be mentioned.

Spectral can help with a lot of this, allowing you to [create style guides for workspaces](TODO Spectral linting). This will catch a lot of trouble sooner, but humans can still check the results after for anything which doesn't have a Spectral rule.

## How does Design Review Work?

Most developers are used to changing to source code in version control systems via "pull requests", at which point various teammates or other folks will review the code. Seeing as Stoplight lets you continue to use your Git repository as a source of truth, this same process can be used for OpenAPI and JSON Schema reviews too.

## 1. Open a Project in Studio

Whether you're [creating a new project](../1.-setting-up-workspaces/a. creating-a-workspace.md) or changing an existing one, pick a project to open in Studio.

## 2. Create a new Branch

A lot of Git repositories (especially those on GitHub) are configured to use [protected branches](https://help.github.com/en/github/administering-a-repository/about-protected-branches), which means pushing to master is not possible. Maybe you can push to master, maybe not, but if you'd like other people to review your work, it is best to create a branch to keep the changes out of master until they've been reviewed.

<!-- ![Typing a new branch name into the drawer in Studio.](../../assets/images/create-branch.png) -->

Read more about [creating and switching branches](TODO 04-common-git-tasks.md#switching-branches).

## 3. Make Changes, Commit, & Push

When you're done making changes, [commit them, then push](TODO 04-common-git-tasks.md#committing-changes) the branch to the remote repository. 

## 4. Open a Pull Request

How you create a pull request depends on where the project's repository is hosted:

- **BitBucket:** [Create a Pull Request](https://www.atlassian.com/git/tutorials/making-a-pull-request)
- **Gitea:** [Create a Pull Request](https://docs.gitea.io/en-us/pull-request/)
- **GitHub:** [Create a Pull Request](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/creating-a-pull-request)
- **GitLab:** [Create a Merge Request](https://docs.gitlab.com/ee/user/project/merge_requests/)

## 5. Link to Branch Documentation

You can publish from any branch, so click "Publish" and once the docs are published you will see a "View Docs". This will give you a link like this:

```
https://{workspace}.stoplight.io/p/docs/your-project?group=your-branch
```

Put that link into the pull request you've just made so people can eyeball the documents instead of reading a bunch of YAML, making the review process much easier.

## 6. Review & Merge

Reviewers can then give feedback on the pull request, you go back to step 3 to make changes, then push, and when the changes are approved you're done! Merge that pull request.
