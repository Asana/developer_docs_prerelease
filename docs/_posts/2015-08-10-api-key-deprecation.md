---
parent-title: News
title: API Key Deprecation
_template: dev-page
_layout: default

# Post Meta
meta-month: August
meta-date: 10th
meta-year: 2015
---
#### API Key Deprecation

The Asana API key has served as a low barrier to entry means of authenticating against the API. We created it for
personal scripts or for rapid prototyping of applications. Applications intended for large scale deployment should
implement [Asana Connect (OAuth 2.0)](/developers/documentation/getting-started/auth) for authentication.

While easier to get started with, the API key poses security risks and provides a degraded user experience overall.
Because we care deeply about user experience and security of the platform, we are rolling out a deprecation plan for
API keys. This means that in the future, these keys will no longer be an acceptable means of authentication and
developers will need to migrate to using one of the options below. We understand this will generate work for some
developers and we'll do our best to ease the transition to what we strongly believe is a more secure and robust
developer ecosystem.

#### API Deprecation Timeline

 - **Today** - Asana will launch personal access tokens (an alternative to API keys for command line access, personal
projects or rapid prototyping of applications that will implement OAuth).

 - **Today** -  Asana will launch a migration mechanism for applications currently deployed using API keys to exchange
those keys for OAuth credentials.

 - **January, 2016** - Users will no longer be able to generate new API keys.

 - **January, 2017** - Asana will no longer accept API keys as a means of authenticating to the API without an amnesty header.

 - **February, 2017** - Asana will no longer accept API key amnesty.

#### Amnesty Headers: A temporary workaround

When we make a breaking change to the API, we strive to use various channels to inform developers and also provide sufficient time for them to make the necessary changes.  Despite our best efforts, we understand that some developers will miss or ignore deprecations until something breaks.  To help these developers quickly get unblocked while they migrate to OAuth or PATs, we will provide temporary amnesty.

To request amnesty, set the API key amnesty header to true: `Asana-Amnesty-Api-Key: true`.  Setting this header to true will enable requests to be served on a temporary basis without the 434 error code.  We will stop accepting Amnesty headers in February, 2017.

#### OAuth Migration

In preparation for deprecating the API key, we're providing a
[migration mechanism from API keys to OAuth authorizations](/developers/documentation/getting-started/auth#api-key-exchange)
for applications that have previously relied on API keys. If you have a service that operates for multiple different
users, it should leverage Asana Connect (Oauth 2.0) for authentication of those users instead of individuals' API keys
or personal access tokens.

This migration mechanism is actually quite simple&mdash;head over to
[the documentation](/developers/documentation/getting-started/auth#api-key-exchange) to learn more and
if you have any questions please send us a note to
[api-support@asana.com](mailto:api-support@asana.com?subject=OAuth%20Migration).

#### Personal Access Tokens

With deprecating the API key we still want to provide a low-friction way to access the Asana API for writing scripts,
prototyping an application or working on the command line. Personal access tokens do just that and more! You can create
a personal access token for yourself on the ["apps" tab of your profile settings](https://app.asana.com/-/account_api).

Be careful&mdash;these tokens should be treated like passwords. The advantage to personal access tokens over API keys is that
you can create many and revoke them on an individual basis when they're no longer needed. You'll need to enter a
description for each token you create to help you remember its purpose if you ever decide that you want to revoke it.
