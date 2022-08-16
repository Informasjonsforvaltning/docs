---
title: Git workflow
weight: 5
---
There are different popular Git workflows. We consider [Gitflow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow)" too focused on scheduled releases. Since we try to deploy "all the time", we shall adhere to the [GitHub Flow](https://githubflow.github.io/):

> - Anything in the master branch is deployable
> - To work on something new, create a descriptively named branch off of master (ie: new-oauth2-scopes)
> - Commit to that branch locally and regularly push your work to the same named branch on the server
> - When you need feedback or help, or you think the branch is ready for merging, open a pull request
> - After someone else has reviewed and signed off on the feature, you can merge it into master
> - Once it is merged and pushed to 'master', you can and should deploy immediately

## Tips and tricks

- To track which state of the repo is deployed, we simply expose the currently deployed SHA through the webapp itself and curl it if we need a comparison made.
- Nice introductction to GitHub flow here: https://docs.github.com/en/get-started/quickstart/github-flow
