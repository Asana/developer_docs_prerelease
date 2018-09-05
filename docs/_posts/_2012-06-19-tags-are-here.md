---
parent-title: News
title: Tags are here!
_template: dev-page
_layout: default

# Post Meta
meta-month: June
meta-date: 19th
meta-year: 2012
---
Thanks to all those that requested it, the API now supports <a href="/developers/api-reference/tags">tags</a>! Here are the changes we recently rolled out:

- Projects now have a `stories` endpoint similar to tasks, for querying comments/updates on the project object itself.
- There is a new `/tags` endpoint for manipulating tags.
- Full records for tasks now include a `tags` field.
- The task endpoint now has `addTag` and `removeTag` methods.
