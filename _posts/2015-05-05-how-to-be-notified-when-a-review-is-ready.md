---
layout: post
title: How to be notified when a review is ready?
---

There are several ways to receive notifications :

* email,
* GitHub Status,
* a message into a chat room (Slack, Hipchat, or Flowdock),
* a badge on a PullRequest, or
* comments on a PullRequest.

All except for the two last, are set up on your
[account page](https://www.pullreview.com/settings/accounts#notification).

## Email

If you set up email notifications, you will receive emails from the address
notifications@pullreview.com. Be sure to
[whitelist this email address](http://sonomanewcomers.org/Images/Whitelist_Instructions.htm)
to prevent those notification emails to be marked as spam.

By default, PullReview will send emails to your primary GitHub email address.
You can change this on your
[account page](https://www.pullreview.com/settings/accounts#notification).

## PullRequest

To use the GitHub API to comment the PullRequest, you have to first grant us
access to these repositories.

Second, change the settings of the PullReview webhook as follows:

* browse the webhook settings of your repository
  `https://github.com/<account>/<repo>/settings/hooks`,
* edit the webhook URI `https://www.pullreview.com/api/push/github`,
* in the section *Which events would you like to trigger this webhook?*, click on
  *Let me select individual events*,
* check the Pull Request box (Pull Request opened, closed, assigned, labeled, or synchronized.),
* click on *Update* webhook button.

Finally, enable the PullRequest notification via the
[PullReview configuration]({% post_url 2015-05-22-how-can-i-apply-custom-setup-for-a-give %})
file `.pullreview.yml`:

```
---
notifications:
  pullrequest:
    comment: verbose
```

With the option `verbose`, each time there is a new code review, PullReview will
update the PullRequest as follows:

* comment with a badge (if it was already commented, the badge is just updated),
* comment with an excerpt of the review mentioning the number of fixed and added
  issues, and
* comment the code with the most critical issues.

When clicking on the badge or the links, you'll browse the full code review.

If you just want the badge, use the option `enabled`.

See also:

* [How can I apply custom setup for a given repository?]({% post_url 2015-05-22-how-can-i-apply-custom-setup-for-a-give %})
