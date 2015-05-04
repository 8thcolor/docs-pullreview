---
layout: default
title: How to integrate with a Continuous Integration Service?
---

# How to integrate PullReview with a CI such as Semaphore, CircleCI, TravisCI, CodeShip, Jenkins?

With the [Gem pullreview-coverage](https://github.com/8thcolor/pullreview-coverage/), you can retrieve your Ruby test coverage into PullReview.

## How it works?

The idea is to add a Gem and configure it to collect the coverage reports, and
then to submit them to PullReview just after the tests are completed. PullReview
will process them and map them to the current review, and add actions for the
uncovered methods/classes.

Depending on race condition between PullReview and your CI-Server, you will have
reviews with or without coverage related actions. If you have multiple test-
suites, running on multiple nodes, PullReview will merge the coverage reports.
If PullReview isn't available at the report submission time, note that the build
won't fail.

## Setup your project

Update Gemfile for `:test`

Add the following in `:test` group.

```Ruby
group :test do
  gem 'pullreview-coverage', require: false
end
```

Once done, run a `bundle install` and commit your modified `Gemfile` and
`Gemfile.lock`.

Note: this Gem is [open-source](https://github.com/8thcolor/pullreview-coverage) and available via [RubyGems](https://rubygems.org/gems/pullreview-coverage).

## Usage

### If you don't already use simplecov

You can simply enable the coverage report by adding the following lines in your
`{spec,test}_helper.rb`:

```Ruby
require 'pullreview/coverage_reporter'
PullReview::CoverageReporter.start
```

### If you use already simplecov

Add our formatter in your `{spec,test}_helper.rb`:

```Ruby
require 'simplecov'
require 'pullreview/coverage'
formatters = []
... # your other formatters (html ?)
formatters << PullReview::Coverage::Formatter
SimpleCov.formatter = SimpleCov::Formatter::MultiFormatter[*formatters]
```

## Setup in your CI build

Add an environment variable with your repository token

```Bash
PULLREVIEW_REPO_TOKEN=<your repo token> rake test
```

Depending on the CI you use, you can pass that token via the environment
variable `PULLREVIEW_REPO_TOKEN`, prefer the encrypted option if available:

* [Circle-CI](https://circleci.com/docs/environment-variables#setting-environment-variables-for-all-commands-without-adding-them-to-git)
* [Codeship](https://www.codeship.io/documentation/continuous-integration/set-environment-variables/)
* [Semaphore](https://semaphoreapp.com/docs/exporting-environment-variables.html)
* [Travis-CI ](http://docs.travis-ci.com/user/build-configuration/#Secure-environment-variables)

## Finally trigger a build

If the Gemfile modification is merged in your integration branch, new actions
about test coverage could be now reported in the corresponding review.

## FAQ and Miscellaneous

You'll find more information on the
[Gem homepage](https://github.com/8thcolor/pullreview-coverage).
