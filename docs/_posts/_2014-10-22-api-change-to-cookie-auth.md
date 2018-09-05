---
parent-title: News
title: API Change to Cookie Auth
_template: dev-page
_layout: default

# Post Meta
meta-month: October
meta-date: 22nd
meta-year: 2014
---
Keeping users&rsquo; data in Asana secure is our top priority. We learned of a potential security threat when apps piggyback on a user&rsquo;s cookie for authentication, so we are disallowing that authentication method.

We don&rsquo;t make this decision lightly and understand how important it is to keep our API stable. We apologize for the difficulties this may cause you.

If you have been relying on the user&rsquo;s asana.com cookies for authentication, please update your apps to use OAuth or API keys, as described in <a href="/developers/documentation/getting-started/auth">/developers/documentation/getting-started/auth</a>
