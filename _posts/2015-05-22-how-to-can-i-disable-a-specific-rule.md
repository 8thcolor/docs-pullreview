---
layout: post
title: How to can I disable a specific rule?
---

You can disable a specific rule via the
[PullReview configuration file]({% post_url 2015-05-22-how-can-i-apply-custom-setup-for-a-give %})
`.pullreview.yml`:

```
rules:
  ignore:
    - add_underscores_to_large_numeric
```

You should use the public ID of the rule. You'll find a list of the rules
you can ignore in this [CSV file](/assets/pullreview_public_id_of_rules.csv).

See also:

* [How can I apply a custom setup for a given repository?]({% post_url 2015-05-22-how-can-i-apply-custom-setup-for-a-give %})
