---
parent-title: News
title: Webhooks Launch and Custom Fields
_template: dev-page
_layout: default

# Post Meta
meta-month: June
meta-date: 6th
meta-year: 2016
---
#### Launched: Webhooks!

We&rsquo;ve formally launched webhooks! Since the release, we&rsquo;ve found that many developers are already getting a lot of value out of webhooks. You can read about how Slack, Unito, tray.io, and Instagantt are using webhooks in our recent [blog post](https://blog.asana.com/2016/05/updates-slack-github-more). To learn more about webhooks, or get started using them, check out our [Developer's page](/developers/api-reference/webhooks).

If you try out webhooks, we welcome your feedback at [api-support@asana.com](mailto:api-support@asana.com). The top request so far has been for more granular event information, which we are looking to implement next.

#### In Beta: Custom Fields

We&rsquo;re excited to share that our new custom fields feature is currently in a private beta. This release of custom fields is the first step toward enabling customers to [track anything](https://vimeo.com/141968469) in Asana. With custom fields, Asana users can track and categorize information specific to their team&rsquo;s needs. Users can create their own fields like priority level, billable hours, deal stage, and much more. In the long term, custom fields will make Asana a more powerful tool for our users, integration partners, and our developer community.

We&rsquo;re looking at opening up the beta to a broader audience over the coming months. [Sign up here](https://docs.google.com/forms/d/1TWmylaS0Ft8BwsW0vWpNuqe3xFjGq-GFc5vaa5udL2M/viewform?c=0&w=1) if you&rsquo;re interested in using custom fields!

#### In Progress: Performance

A major focus right now at Asana is [performance](https://blog.asana.com/2016/03/asana-performance-what-to-expect-in-2016/), and that extends to our API. Our API team is working on dramatically reducing the latency of API requests. To do so, we&rsquo;re building a brand-new API server on top of our [LunaDb datastore](https://blog.asana.com/2015/10/asana-tech-talk-reactive-queries/).

We&rsquo;ll likely roll out these changes on an endpoint-by-endpoint basis, focusing first on GET requests before moving on to POSTs and PUTs. We intend to maintain backwards compatibility in most places, although we may fix a few bugs between versions along the way.

#### Security Update: Deprecating TLS 1.0 Support

In our continuous efforts to improve data security, we will be disabling TLS 1.0 across Asana services starting in September. This will prevent clients limited to TLS 1.0 from accessing the Asana API for inbound and outbound connections.

TLS ([Transport Layer Security](https://en.wikipedia.org/wiki/Transport_Layer_Security), the more modern version of SSL) ensures that your application is connected to authentic Asana services and prevents attackers from snooping on your connections. Asana web, mobile, API, and email delivery use TLS as a key component of their security, but TLS 1.0 is an older and more vulnerable version of the protocol.

Before TLS 1.0 is disabled, you will need to ensure that TLS 1.1 or 1.2 is enabled for your application&rsquo;s integration with Asana. You can consult Salesforce&rsquo;s thorough [compatibility overview](https://help.salesforce.com/apex/HTViewSolution?id=000221207#Inboundintegrations) to see if your integration is affected. Consider this for both inbound and outbound connections (including OAuth and webhooks).

#### API Key Update

As noted in our previous newsletter, we are deprecating the API key authentication mechanism for our API in November 2016. Any applications using API keys after this time will stop working. If you haven&rsquo;t done so already, here are ways you can replace API keys:

  * [Personal access tokens](/developers/documentation/getting-started/auth#personal-access-token): These are an alternative to API keys for command-line or script access, personal projects, or rapid prototyping of applications that will implement OAuth.
  * [API key to OAuth migration](/developers/documentation/getting-started/auth#api-key-exchange): This is an endpoint for applications currently deployed using API keys to exchange those keys for OAuth credentials.

Note that new Asana users can no longer generate API keys. If you have deployed an application that requires an API key, you will be unable to accept new users, and will need to replace API keys using one of the methods listed above.
