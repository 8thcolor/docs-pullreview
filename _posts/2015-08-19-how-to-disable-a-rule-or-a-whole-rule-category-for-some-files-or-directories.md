---
layout: post
title: How to disable a rule or a whole rule category for some files or directories?
---

In the [PullReview configuration file]({% post_url 2015-05-22-how-can-i-apply-custom-setup-for-a-give %}),
add the following:

```
rules:
  <category_id|rule_id>:
    except:
      - <pattern>
```

where:

* `<category_id>` is one of the possible rule categories: `code_smell`,
  `copy_paste`, `complexity`, `design`, `style`, ` documentation`,
  `test_infection`,
* `<rule_id>` is one of the possible rule listed in that
  [CSV file](/assets/pullreview_public_id_of_rules.csv),
* `<pattern>` follows rules similar to shell filename globbing.

Be sure your YAML file is still valid.
