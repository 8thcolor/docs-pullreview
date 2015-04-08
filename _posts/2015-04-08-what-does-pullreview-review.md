---
layout: default
title: What does PullReview review?
--- 

# What does PullReview review?

It only considers a branch that you've contributed at least once. It compares
the situation between the start of the branch and its head. It then looks into
it for all the new problems, i.e. those that have been added on to the branch.

The existing problems, i.e. those existing at the start of the branch, that have
been solved, are shown as "fixed".

PullReview also looks around in the files containing the new changes made in the
branch. The actions to fix them are shown in a second list _Seize the
opportunity to make the code base better_ should you want to do some clean-up
work.

The integration branch (as defined on GitHub as the repository's "default
branch") is treated differently, as there is no starting point to compare from.
In this situation, we simply show all existing problems on that branch.

PullReview does review only Ruby, Rails, and Javascript code.

PullReview can connect to GitHub, BitBucket, GitLab, and Stash repositories.