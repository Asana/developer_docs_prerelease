---
parent-title: News
title: File attachments, colors, CORS and more!
_template: dev-page
_layout: default

# Post Meta
meta-month: November
meta-date: 7th
meta-year: 2013
---
We have a few new (and in some cases, old-but-we-didn&rsquo;t-mention-yet) features to draw your attention to:

- **File attachments.** You can both fetch and upload file attachments to tasks, see the <a href="">documentation on Attachments</a> for more details.
- **User avatars** are now included in the user object, see the <a href="">documentation on Users</a> for the new photo property, which maps different sizes to URLs.
- **Delete projects and tasks.** Using the `DELETE` verb, you can now delete projects and tasks. Pretty straightforward.
- **Fetch archived tasks. By including `?include_archived=true` in a request for tasks in a project, you will now also receive the archived tasks in addition to the unarchived ones.
- **Colors!** You can now both request and set the colors for projects and tags, through a new attribute creatively dubbed color, which can be `null` or a string encoding a color. Valid colors are:
  - `light-yellow`
  - `dark-brown`
  - `(light|dark)-(pink|green|blue|red|teal|orange|purple|warm-gray)`

**Note:** colors are specific to the user, rather than global, so if you set the color as one user you won&rsquo;t see it reflected as another.

- **CORS support.** For those of you building in-browser apps, this will be a nice addition: you can now make requests to the Asana API, including `POST/PUT/DELETE`, from other domains (as long as it&rsquo;s a reasonably modern browser). See <a href="">this gist</a> for an example of how to use this feature.
