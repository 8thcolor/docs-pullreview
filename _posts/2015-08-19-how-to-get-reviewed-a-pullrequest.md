---
layout: post
title: How to get reviewed a PullRequest?
---

When you create a PullRequest, it always about a branch. The branch could be one
of your repo, or one from a fork.

By default, PullReview can detect when a PullRequest is associated to a branch
when you push a commit. However, it cannot detect when the PullRequest is
created. As consequence, it cannot detect a PullRequest from a fork as they do
not correspond to a branch of your repository.

In order to get reviewed any PullRequest from a fork or not, you need to enable
PullRequest event on the PullReview webhook as following:

1. browse `https://github.com/<account>/<repo>/settings/hooks
2. edit https://www.pullreview.com/api/push/github
3. select on "Let me select individual events. "
4. enable Pull Request (Push is already enabled)
5. click on "Update Webhook"

See also:

* [How to be notified when a review is ready]({% post_url 2015-05-05-how-to-be-notified-when-a-review-is-ready %})
  to learn how to get notification directly in your PullRequest.
