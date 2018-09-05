---
parent-title: News
title: Hearts, recent tasks, and more!
_template: dev-page
_layout: default

# Post Meta
meta-month: August
meta-date: 5th
meta-year: 2014
---
We are happy to announce a few changes to the API that you may or may not have noticed:

- **Hearts** are now included by default in both tasks and stories. Hearts can be queried using the new parameters: `hearted`, `hearts`, and `num_hearts`. You can read more about this in our documentation on <a href="">tasks</a> and <a href="">stories</a>.
- **Recent** tasks. You can now query for recently completed or modified tasks using the new `completed_since` and `modified_since` parameters. You can read more in our documentation.
- **User** avatars can now be queried with or without specifying a specific photo size. For example, `?opt_fields=photo` returns all possible photo sizes, and `?opt_fields=photo.image_128x128` returns one specific photo size.
- **Email** visibility. We&rsquo;ve fixed a small bug where we threw an error when querying for a user&rsquo;s email that was hidden due to insufficient permissions. Instead, we now return the results and use `null` for the user&rsquo;s email.s
