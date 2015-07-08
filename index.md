---
layout: default
title: Welcome
---

# PullReview Documentation

Welcome to the documentation of PullReview, an automated code review service.
There's a good chance your question about using it will be answered here. If you
have any questions or meet any issues, you can get help by clicking on
[<i class="icon-envelope-alt"></i>](https://www.pullreview.com/site/contact) or
by sending an email to [the support address](support@pullreview.com).

We welcome any issues or PullRequests on the
[website project](https://github.com/8thcolor/docs-pullreview).

## Check out the docs!

<div id="search">
  <form action="/search" method="get">
    <input type="text" id="search-query" name="q" placeholder="Search" autocomplete="off">
  </form>
</div>

<section id="search-results" style="display: none;">
  <header><h3>Results</h3></header>
  <div class="entries">
  </div>
</section>

{% raw %}
<script id="search-results-template" type="text/mustache">
  {{#entries}}
    <article>
      <h3>
        <a href="{{url}}">{{title}}</a>
      </h3>
    </article>
  {{/entries}}
</script>
{% endraw %}

## Table of Content

{% for post in site.posts %}
* [{{ post.title }}]({{ post.url }})
{% endfor %}

<script src="/js/search.min.js" type="text/javascript" charset="utf-8"></script>
<script type="text/javascript">
  $(function() {
    $('#search-query').lunrSearch({
      indexUrl: '/js/index.json',   // Url for the .json file containing search index data
      results : '#search-results',  // selector for containing search results element
      entries : '.entries',         // selector for search entries containing element (contained within results above)
      template: '#search-results-template'  // selector for Mustache.js template
    });
  });
</script>
