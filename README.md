Hello, and welcome to Asana's Developer Documentation page!
======

If you would like to contribute, we'd love to receive a PR from you! First, here's a few things to know:

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

# Building

We use Jekyll to do all the open-form blog-y stuff, and Slate to do our API reference page. Slate uses middleman, which is, just like Jekyll, a static site generator. :/

Thankfully, since these are just generating static sites, we can generate the api reference into a package, copy it for Slate, then publish it to Github pre-rendered. This means we generate an inner static site, and then upload it to Github, which generates an outer static site.

(Note: it might be possible to port Slate to Jekyll by migrating its erb template to a Fluid template, but I'm not sure if that's possible and how much scope that would take).

The next challenge is that we have our OpenAPI docs, but Slate takes Markdown. There's an open source project called [Widdershins](https://github.com/Mermade/widdershins) that will take care of that for us.

So our build process goes:

OpenAPI => Widdershins => markdown => Slate on middleman => html => Jekyll => Github Pages => html

This is pretty gnarly and lends us to some pretty out-there dependencies, but this is an area of improvement in the future. One saving grace for us is that there are a couple of industry-standard "checkpoints" in there (OpenAPI, markdown, html) that are targets that can be reverse-engineered to if we need to.

Advantages are that Widdershins and Slate are actively maintained and seem pretty fully-featured, and Jekyll is used by hundreds if not thousands of Github Pages users.
