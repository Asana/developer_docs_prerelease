---
parent-title: News
title: First API Update
_template: dev-page
_layout: default

# Post Meta
meta-month: February
meta-date: 28th
meta-year: 2012
---
- Discarded `opt_include/opt_exclude` in favor of just `opt_fields` which explicitly names all fields desired. Any unnamed fields will not be included in the output (we think this is the right way to expose this functionality, so you don&rsquo;t have to guess what will be included by default.) The ID of objects are _always_ included.
- Added a (read-only) &ldquo;workspace&rdquo; property to Tasks.
- `target` and `source` of a Story are no longer part of their compact representation.
