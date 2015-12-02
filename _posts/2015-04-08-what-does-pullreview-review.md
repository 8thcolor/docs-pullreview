---
layout: post
title: What does PullReview review?
---

It only considers a branch that you've contributed at least once. It compares
the situation between the start of the branch and its head. It then reviews
it for any new problems, i.e. those that have been added on to the branch.

Existing problems, i.e. those existing at the start of the branch, that have
been solved, are shown as "fixed".

PullReview also examines files containing new changes made in the
branch. The actions to fix them are shown in a second list _Seize the
opportunity to make the code base better_ should you want to do some clean-up
work.

The integration branch (as defined on GitHub as the repository's
[default branch](https://help.github.com/articles/setting-the-default-branch/))
is treated differently, as there is no starting point to compare with. In this
case, we simply show all existing problems on that branch.

See also:

* [Which forge can PullReview connect to?]({% post_url 2015-04-29-which-forge-can-pullreview-connect-to %})
* [Which programming language can be reviewed?]({% post_url 2015-04-29-which-programming-language-can-be-reviewed %})
