---
layout: default
title: What does PullReview do and how does it work?
--- 

# What does PullReview do and how does it work?

PullReview retrieves your code from your repository at GitHub. Then, for each
branch, it reviews your code modifications in order to detect defects,
vulnerabilities, and other issues such as poor readability. Your code doesn't
need to be run as for the test.

During the analyses, PullReview checks the code according to about 400 rules.
Each rule allows detecting one specific kind of issue. The rules are classed
into 8 categories:

![Category Icons](/assets/category-icons.png)

, from left to right, code smell, duplication, security, complexity, design,
style, documentation, and test.

After having detected issues in your branch, PullReview reports them to you into
a code review. It mainly consists in an ordered list of possible improvements.
They are ordered by criticity. The most important improvements are on the top of
the list.

![Improvement](/assets/improvement.png)

One improvement concerns detected issues of the same kind. It will tell you
where the issues have been detected, why they should be considered as issues,
and how you could fix them.

As we said earlier, PullReview will generate a code review for every branches
you have on your repository. Each time you'll push new commits on a branch,
PullReview will update the corresponding code review. When it does that it will
also detect what you've fixed since the previous review.

PullReview is then very close to the feature branch development model. It
reports you only what concerns your current work, i.e. the modifications you've
made on a branch. In the case of the integration branch (also called the default
branch and usually named master), PullReview reviews the whole code base.
