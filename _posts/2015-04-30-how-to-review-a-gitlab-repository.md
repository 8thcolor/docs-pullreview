---
layout: post
title: How to review a GitLab repository?
---

Here are the steps to follow to add a GitLab repository:

* Browse to the [repositories page](https://www.pullreview.com/settings/repositories)
* Click on "Add a repository" (button on top right of the list)
* Select GitLab as forge
* Check private if it's a private repo
* Add the hostname of where your GitLab repo is hosted
* Add the repository name
* Click on "Add this repository"
* Once added to the list,
  * If it's a private repo:
    * Click on "Add a deploy key to review"
    * Follow the instructions to add the deploy key and the webhook
  * If it's a public repo:
    * Click on "Review"
    * Follow the instructions to add the webhook
