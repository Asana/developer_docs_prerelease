---
parent-title: News
title: You're Invited! Asana's new, faster platform
_template: dev-page
_layout: default

# Post Meta
meta-month: October
meta-date: 24
meta-year: 2016
---
Asana has been investing in a faster infrastructure to make work tracking even more effortless, and this includes accessing information from our API. We have been focusing on the performance of our platform for months, and we're now ready to show the world what we've accomplished! We'd love for you to check it out!

This new platform represents a completely rewritten server that provides data up to 5 times faster than before. We have been running tools to verify that the new platform behaves like our old one, so you should be able to migrate to our new API with minimal friction.

To make requests to our new API, all you have to do is add a HTTP header to your requests: `Asana-Fast-Api: true`. This will enable us to route your requests, if possible, to the new API. (The few requests that we are finishing up implementing in the API will be routed automatically to our existing API to provide the most seamless experience possible.) You can tell the difference between which version is handling your request by examining the headers of the response: if you receive the header `X-Asana-Api-Version: 1.1`, your request was handled through the new platform!

Here's a cURL example, just to be clear:

    curl -v --request GET -H "Authorization: Bearer $ASANA_PERSONAL_ACCESS_TOKEN" \
      -H 'Asana-Fast-Api: true' \
      "https://app.asana.com/api/1.0/tasks/$TASKID"

It's as easy as that!

While it would be nice to be able to speed up everything in life by adding some "please make this fast" metadata, it wasn't quite that simple for our team to get to where we are with the new platform. After a complete rewrite, including new tools and infrastructure to make sure we created a quality platform, we think this will be a great step forward, particularly for integrations which would like to use Asana in a more interactive way. This speed gain is intended to be more or less transparent to users of our platform, so there's no reason not to try it out!

Of course, like all beta software, you may hit the occasional unintended hiccup. We've taken pains to try to faithfully replicate the behavior in our existing API with the new platform, but there are some slight differences: for instance, some error codes may have changed from 404 to 403, some authentication edge cases have been fixed, and so on. If you run into any major problems, feel free to join the conversations on our Slack organization [Asana App Developers](https://asanaappdevelopers.slack.com), channel #api_1_1_beta, or visit the [Asana Community](https://community.asana.com/) to get some help or give us your thoughts.

Thanks,

Matt Bramlage, Asana Developer Advocate
