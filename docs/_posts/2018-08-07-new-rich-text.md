---
layout: post
title:  "New rich text"
date:   2018-08-07 14:30:30 -0700
categories: jekyll update
---

As the Asana web product has developed over the years and acquired new formatting, the API hasn't kept up with all of the new additions owing to the fact that we needed to maintain backwards compatibility. Over time, lack of access to these additions have started to hinder app functionality. In one example, our format for representing links to other Asana objects (such as when you @-mention another user or task) didn't communicate enough of the useful information about these links. The Asana API is now happy to announce that we're addressing these issues in our "new rich text" update.

The full documentation for this new feature [has been published](/developers/documentation/getting-started/rich-text), but to summarize, there are two major changes to be aware of when using this new format:

- All text must be valid, supported XML.
  - This means that all rich text going in and out of the API will be wrapped in a root `<body>` tag.
  - This also means that unsupported XML tags will be rejected.
- Link tags will contain attributes about the object they link to.
  - For example, they will have an `data-asana-type` object that tells you whether the link points to a task, a user, a project, or another type.
  - This feature can also be used to have Asana automatically generate links for you. By adding a `data-asana-id` attribute with the ID of the object you wish to link to, the API will generate the correct `href` target.

See the [long-form documentation](/developers/documentation/getting-started/rich-text) for a list of supported tags and how to read and write to rich text fields.

The Asana API [recently launched a deprecation framework](/developers/news/deprecations-security-headers) that allows developers to safely migrate to new features or through breaking changes. This framework is now being used to roll out the new rich text. Please refer to the [deprecations documentation](/developers/documentation/getting-started/deprecations) for more information on how to get this new behavior.

Beginning today, you can send `Asana-Enable: new_rich_text` in the headers of your API requests to enable the new format and begin using this new feature.

Beginning on October 15th 2018, the default behavior will change and requests that don't explicitly choose either the old or new format will start to receive the new format. If this triggers an issue with your app, you can send the `Asana-Disable: new_rich_text` header to continue using the old format.

On December 17th 2018, the new behavior will become permanent. All responses will use the new format and enforce the new validation, and you will no longer be able to use the old behavior.
