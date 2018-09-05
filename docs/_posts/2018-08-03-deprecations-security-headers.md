---
parent-title: News
title: Breaking Changes in the API
_template: dev-page
_layout: default

# Post Meta
meta-month: August
meta-date: 3
meta-year: 2018
---

### Deprecation Process

There are unfortunately some circumstances where we cannot roll out changes in a backwards compatible way. To help users of the Asana API get over these hurdles, we have created a formalized [deprecation process](/developers/documentation/getting-started/deprecations) that we'll be using to release these breaking changes.

In short, we will provide deprecation periods during which you'll be able to select between old and new behavior on a per-request level, allowing you to observe the differences and test them in a controlled manner. This is done by sending `Asana-Enable` and `Asana-Disable` headers in your requests with the names of the features you want to turn on or off. We strongly encourage you to read the [full documentation](/developers/documentation/getting-started/deprecations) for this process.

### Security Headers

Right now, the responses from the API will include two security-related headers: [`Content-Security-Policy-Report-Only`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy-Report-Only) and [`Strict-Transport-Security`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Strict-Transport-Security). We would like to send additional security headers in our responses, but these additional headers may cause problems with some improperly configured browser clients. Because of this, we will be using the deprecations process mentioned above to roll out the following additional headers:

- [`X-Frame-Options`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-Frame-Options)
- [`X-Content-Type-Options`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-Content-Type-Options)
- [`X-XSS-Protection`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-XSS-Protection)
- [`Content-Security-Policy`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy) (this will replace `Content-Security-Policy-Report-Only`)

Starting now, you can send `Asana-Enable: security_headers` in the headers of your API requests to enable the new behavior and begin receiving these additional headers.

Beginning on September 28th 2018, the default behavior will change and requests that don't explicitly choose to enable or disable these headers will start to receive the new security headers in the responses. If this triggers an issue with your app, you can send the `Asana-Disable: security_headers` header to disable them.

On November 15th 2018, the new behavior will become permanent. All responses will contain the new security headers, and you will no longer be able to disable them.

Keep an eye on our blog and [community forum](https://community.asana.com/c/developersAPI) for the latest information about upcoming API changes.
