---
layout: post
title: How to get a PullRequest reviewed?
---

When you create a PullRequest, it always about a branch. The branch could be on one
of your own repos, or one from a fork.

By default, PullReview can detect when a PullRequest is associated to a branch
when you push a commit. However, it cannot detect when the PullRequest is
created. As consequence, it cannot detect a PullRequest from a fork as they do
not correspond to a branch of your repository.

In order to have  reviews on PullRequests from a fork or not, you need to enable the
PullRequest event on the PullReview webhook as following:

1. browse `https://github.com/<account>/<repo>/settings/hooks
2. edit https://www.pullreview.com/api/push/github
3. select on "Let me select individual events. "
4. enable Pull Request (Push is already enabled)
5. click on "Update Webhook"

See also:

* [How to be notified when a review is ready]({% post_url 2015-05-05-how-to-be-notified-when-a-review-is-ready %})
  to learn how to get notifications directly in your PullRequest.
