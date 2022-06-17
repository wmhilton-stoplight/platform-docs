---
stoplight-id: a13c113eb9988
---

# Common Git Tasks

Projects using Git as the source of truth have extra functionality enabled, as Stoplight Studio supports common Git tasks like **pushing**, **pulling**, **creating/switching branches**, **comparing differences**, etc.

If you are new to [Git](https://git-scm.com/), it's a version control system that can help developers collaborate projects without getting in the way of each others work, or it can help just one developer keep track of various in-progress changes. [GitHub](https://github.com/) is one popular Git repository hosting provider of many. They have written a nice [introduction to Git](https://guides.github.com/introduction/git-handbook/) which you might want to check out if you're new to Git entirely.

You don't need to know too much about the complexities of Git in order to get things done in Stoplight, but the following actions are worth knowing about.

## Committing Changes

When working on files, you want to save them to persist the changes to your computer (or "local storage" in the browser if you're using Studio Web). This will not update those changes in the Git repository, because that would cause a lot of issues and lost work every time somebody hit save.

Git has two concepts known as **Commit** and **Push**.

- **Commit** is the act of grouping changes to a file, or files, together, along with a commit message.
- Commits can then be **pushed** to the repository, and so long as there are no conflicts the commit will be pushed successfully.

After you make changes to files, Studio will always ask you to commit and push at the same time when you select **Commit & Publish**, because non-pushed commits can sit around on your computer, unshared with others, and that can lead to confusion and lost work.

When a commit has been pushed, people who are switched to the same branch can "pull" your changes down.

## Pulling Changes

If somebody else has pushed and you'd like to get their changes, select your branch at the top, and then select **Git pull**. This will update your local files, so you can continue working from where they left off.

Updates can also be automatically pulled by selecting the hamburger menu on the top-left, and then selecting **Git** -> **Auto-pull**.

## Switching Branches

Git is a very open-ended technology which can be used in a lot of different ways. Everyone can commit to the same branch (usually called `main`, or `master`), or people can work in different branches to be merged later. To switch branches, select the branch name at the top of the page, then select **Switch branches**.

A modal will appear in the middle of the screen, allowing you to search through existing branches. To make a new one, type in a name for a branch which does not exist.

Select enter/return on the keyboard or select the "(+)" icon and you've switched (a.k.a "checked out") the new branch.

## Using Other Clients

If you already have a favorite Git client like the [Git CLI](https://git-scm.com/docs/gitcli), [Github Desktop](https://desktop.github.com/), [Sourcetree](https://www.sourcetreeapp.com), or similar, then you can also continue using them. 

If you're using Stoplight Studio Desktop, you'll need to give Stoplight app a reload (CMD + R / Ctrl + R) after you make changes to your project outside of Stoplight, then Stoplight Studio will notice the changes and you're all set. 
