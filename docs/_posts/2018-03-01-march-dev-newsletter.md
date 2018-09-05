---
parent-title: News
title: Start Dates & Other Changes - March 2018 API Updates
_template: dev-page
_layout: default

# Post Meta
meta-month: March
meta-date: 02
meta-year: 2018
---

### Start Dates Launch

Late last year, Asana launched [Start Dates][start_date_blog] as a feature for
Asana Premium. We're happy to announce that start dates are now
available via the API! As one of the [fields you can set on a
Task](/developers/api-reference/tasks), the `start_on` field works exactly like
the `due_on` field, where the date is specified in `YYYY-MM-DD` format.

For more on how start dates work in Asana, be sure to look at our
[documentation in the Asana Guide][start_dates].

For more on tasks in the API, including the `start_on` field, see our [API
reference on Tasks][tasks-api].

[tasks-api]: /developers/api-reference/tasks

[start_date_blog]: https://blog.asana.com/2017/10/add-start-dates-tasks-projects/
[start_dates]: /guide/help/premium/start-dates

### Concurrent Requests Rate Limiter

In order to provide transparency on how we rate-limit incoming requests, we
recently wrote [documentation on how our rate-limiting works][rate_limiting].

Of note is that recently, in addition to standard rate-limiting, we've also
added in [rate limits for concurrent requests][concurrent_limits].
This will be particularly important for an upcoming release, so stay tuned!

[rate_limiting]: /developers/documentation/getting-started/rate-limits
[concurrent_limits]: /developers/documentation/getting-started/rate-limits#concurrent

### Premium-Only Errors

Finally, we made changes to how we handle premium-only errors from our API. In
summary, our API will return `402 Payment Required` responses for requests that
that originate from non-premium workspaces that attempt to access premium
features.

We wrote about this extensively [in another
post](/developers/feed/premium-only-errors), including our
apologies for shipping this without communicating the change properly, as well
as our migration strategy (and our recommended migration path for
developers).

You can read more information about this in [our errors
documentation](/developers/documentation/getting-started/errors) under `402
Payment Required`.

### Coming Soon

We have some features that we're excited to launch in the next few weeks, so
stay tuned! For keeping up with our latest updates, be sure to subscribe to our
developer newsletter via the form in the sidebar.
