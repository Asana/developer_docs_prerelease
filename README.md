Hello, and welcome to Asana's Developer Documentation page!
======

If you would like to contribute, we'd love to receive a PR from you! First, here are a few things to know:

Asana's docs are published on Github Pages. You can go directly to the documents by going to https://asana.github.io/<reponame>.

The master branch is protected and can only be committed to by an Asana team member. If you'd like to create a change, please do it in a topic branch and create a PR for us in github.

Certain parts of our documentation are generated from our OpenAPI spec, and so any changes to the docs need to be made upstream there.

Contributing
------

As with many other Github Pages sites, our page is run on [Jekyll](https://jekyllrb.com/). The getting started pages there are a great resource, but here is a turbo-start to develop these pages the way we do at Asana.

Here are the prerequisite things you'll need:
- Ruby (we use Ruby with [Jekyll](https://jekyllrb.com/) and [Slate](https://github.com/lord/slate))
  - Bundler to manage the dependencies
Node.js for (widdershins)


We use [rbenv](https://github.com/rbenv/rbenv) to maintain our Ruby installations and create a nice clean sandbox for documentation development. There are several ways to install rbenv listed in that link; you'll know you're ready to go on to the next step when `rbenv -v` prints out the version of your current rbenv command.

We use Ruby version 2.5.0 for this repository; although it may be possible to use a different version, it's recommended to use this version as well. To set this up, run

`rbenv install 2.5.0`

There is a .ruby-version file in this directory that should set you on this version of Ruby whenever you're here or in as subdirectory.

You then need to have Bundler installed

`gem install bundler`

And all of our ruby gems. The root of our site (including the bundler Gemfile) is `/docs`, so

`cd docs`
`bundle install`

**TODO: There is a message about sass being deprecated. Investigate alternatives.**

API reference
======

The technical reference for our API is at [https://asana.github.io/developer_docs_prerelease/api_reference/](https://asana.github.io/developer_docs_prerelease/api_reference/). It is a simple themed [ReDoc](https://github.com/Rebilly/ReDoc) React app that loads the OpenAPI spec from the same directory and presents it in a pretty view.
