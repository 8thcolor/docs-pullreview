---
layout: post
title: How to exclude a file or a whole directory from analysis?
---

It could be very useful to completely exclude a file or a whole directory from the
review process. It avoids PullReview reviewing generated files
or files making the review analysis crash.

In the [PullReview configuration file]({% post_url 2015-05-22-how-can-i-apply-custom-setup-for-a-give %}),
add the following:

```
excludes:
  - <pattern>
```

where `<pattern>` follows rules similar to shell filename globbing. Be sure your
YAML file is still valid.
