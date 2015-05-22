---
layout: default
title: How to can I disable a specific rule?
---

# How to can I disable a specific rule?

You can disable a specific rule via the
[PullReview configuration file]({% post_url 2015-05-22-how-can-i-apply-custom-setup-for-a-give %})
`.pullreview.yml`:

```
rules:
  ignore:
    - add_underscores_to_large_numeric
```

You should use the public identification of the rule. You'll find all the rules
you can ignore in a [CSV file](/assets/pullreview_public_id_of_rules.csv).

See also:

* [How can I apply custom setup for a given repository?]({% post_url 2015-05-22-how-can-i-apply-custom-setup-for-a-give %})
