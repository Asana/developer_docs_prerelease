---
parent-title: News
title: Premium Only Error Changes in Asana's API
_template: dev-page
_layout: default

# Post Meta
meta-month: February
meta-date: 27
meta-year: 2018
---
**Breaking Change**: We've changed how we handle errors for premium-only
features in the API, moving from HTTP 403 (Forbidden) to HTTP 402 (Payment
Required).  We are now using the new 402 error code for read requests and will
be adding 402s to write requests on **March 13th, 2018**.

### Apologies

First, we want to apologize. A few weeks ago, we changed how we handle errors
for requests that attempt to access premium-only features in a non-premium
workspace. At the time we felt the change would be simple and for the
betterment of our developers and our platform team, without being fully
cognizant of how it would affect our developer community. We didn't communicate
broadly before the change went out, and many apps suffered failures as a
result.

Furthermore, the change was meant to be propagated to both our read and write
actions for our API, but due to a deployment issue, it only reached our API for
read actions, whereas writes maintained the old behavior. We weren't reactive
enough to rollback immediately, and once several of our major developers
started reacting and adjusting to the change, we decided to not cause
further disruption.

We're sorry for the pain and inconvenience this has caused, and [after some
soul-searching](https://wavelength.asana.com/workstyle-ask-5-whys-to-get-to-the-root-of-any-problem/),
we're actively working on process changes to ensure that we:

* Communicate breaking changes clearly, with plenty of time leading up to the
  change.
* Add deprecation notices in our API responses, and communicate this process
  widely in our documentation.
* Update our documentation accordingly throughout the entire process.

When we've finalized our deprecation process in the near future, we'll be sure
to write about it here, as well as extensively document our process in our
developer documentation.

### Premium-Only Error Change Announcement

As more features have been developed for Asana with a focus on Asana Premium,
we've had to reconsider how we handle when an application in a
non-premium workspace attempts to access a premium-only feature, such as [Custom
Fields](/developers/documentation/getting-started/custom-fields).

Previously, the Asana API would return a 403 (Forbidden) response code, with a
message containing "not available for free" in one of its errors in the JSON
response body. **Recently, we decided to change this behavior to return a 402
(Payment Required) instead of a 403 (Forbidden)**. We believe that by making
this behavior consistent for our API endpoints in the future, it will be easier
for developers to discern if the error is due to attempting to access a
premium-only feature in a non-premium workspace, or if their application is
unable to access an object due to permissions within Asana.

### Preparing For The Change

**On March 13th, 2018, we plan to make this change permanent for writes in the
API; it is already in effect for reads. To prepare for this change, we suggest
the following**:

* Add code to handle 402 error codes distinctly from 403 error codes.
* To smoothly transition when we make the final change, in code that handles
  403 errors, check the error message for the string `"not available for
  free"`, and process these errors as you would a 402 error. This will ensure
  your code correctly handles write requests that return a 403 when payment is
  required *(this will no longer be necessary as of March 13th)*.
  * See [our documentation on
    errors](/developers/documentation/getting-started/errors) for information
    on the format of the JSON response.

All of the latest [client
libraries](/developers/documentation/getting-started/client-libraries) support
handling the new 402 error code, both before and after the migration of our
write endpoints to the new error code.

If you have any questions, feel free to reach out to us at
[api-support@asana.com](mailto:api-support@asana.com). We'll also have more
announcements to make soon, so if you aren't on it already, please join our
developer newsletter via the form on the right side of this page!
