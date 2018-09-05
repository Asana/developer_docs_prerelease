---
parent-title: News
title: Subtasks, Stories, and Start Dates - July 2018 API Updates
_template: dev-page
_layout: default

# Post Meta
meta-month: June
meta-date: 26
meta-year: 2018
---

### Subtask Ordering

Some of you have long been asking for the ability to insert subtasks in a particular order, or to reorder subtasks within a parent task. Well, the API team has finally cleared out a five-year-old `TODO` in our codebase and has implemented this feature! Just like when adding tasks to or reordering tasks in a project, you can now specify `insert_before` or `insert_after` when calling the `setParent` endpoint. The new parameters are detailed in our [documentation for subtasks](/developers/api-reference/tasks#subtasks).

### Editing and Pinning Stories

Since March, the web app has been letting users [edit their comments in tasks](https://blog.asana.com/2018/03/new-features-asana-tasks/), and now you can edit them in the API. Comment stories also now have an `is_edited` field to reflect whether they've been edited since creation. We've also exposed an `is_pinned` field for comment and attachment stories that can be set through the API to pin a story to the top of the task. Read more about these fields in our [documentation for stories](/developers/api-reference/stories).

### Project Start Dates

Another recent addition to the web app is [start dates for projects](https://asana.com/guide/help/premium/start-dates#gl-project-start-dates), which have also made it to the API. You can read and write to the [`start_on` field on projects](/developers/api-reference/projects) for this new data. Note: project start dates are a premium-only feature.

### Cost Limiter

We've added a new kind of rate limiting to the API based on the "cost" of your requests. Developers have always been able to choose exactly the data they need using our [`opt_fields` parameter](/developers/documentation/getting-started/input-output-options), but the amount of data selected directly affects the amount of resources required to construct the response. We're now allotting a per-minute quota based on these costs, and a series of extremely expensive requests will result in `429 Too Many Requests` responses. **Very** few developers (about 0.0002%) should actually encounter this, but if you happen to be one of the few, these responses will contain the usual `Retry-After` header that indicates how long you should wait before trying again. You can read more about this new limiter in our [rate limiting documentation](/developers/documentation/getting-started/rate-limits).

We've got more to show you in the coming months, so be sure to subscribe to our developer newsletter using the form in the sidebar.
