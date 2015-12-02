---
layout: post
title: What does PullReview do and how does it work?
---

PullReview retrieves your code from your repository on GitHub. Then, for each
branch, it reviews your code modifications in order to detect defects,
vulnerabilities, and other issues such as poor readability. Your code doesn't
need to be run as for the test.

During the analyses, PullReview checks the code against a set of about 400 rules.
Each rule detects one specific kind of issue. The rules are classed
into 8 categories:

![Category Icons](/assets/category-icons.png)

, from left to right, code smell, duplication, security, complexity, design,
style, documentation, and test.

After detecting issues in your branch, PullReview sends you
a code review. The review is an ordered list of possible improvements ordered, themost critical being shown first.

![Improvement](/assets/improvement.png)

One improvement concerns detected issues of the same kind. It will tell you
where the issues have been detected, why they should be considered as issues,
and how you could fix them.

As we said earlier, PullReview will generate a code review for every branches
you have on your repository. Every time you push new commits to a branch,
PullReview will update the corresponding code review. It will
also recognize what you've fixed since the previous review.

PullReview stays very close to the feature branch development model. It
focusses on your current work, i.e. the modifications you've
made on a branch. In the case of the integration branch (also called the default
branch and usually named master), PullReview reviews the whole code base.
