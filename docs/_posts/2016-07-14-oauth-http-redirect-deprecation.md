---
parent-title: News
title: Deprecation of OAuth 2.0 'http' Redirects
_template: dev-page
_layout: default

# Post Meta
meta-month: July
meta-date: 14
meta-year: 2016
---
#### Deprecated: OAuth redirects to `http` servers

At Asana, we take the security of our users seriously. Last fall, we deprecated connecting with Asana via an API key in favor of OAuth 2.0, which is a reliable method for providing safe authentication to apps which connect with Asana. We will make a additional change soon to make our OAuth workflow even more secure by requiring that applications which connect to Asana via OAuth use an encrypted connection for the entire authentication workflow.


##### Background:

The OAuth workflow, which you can read up on at [our developers documentation website](/developers/documentation/getting-started/auth#oauth), involves users temporarily visiting a location on Asana's servers to authorize access to third party applications. Once the user has verified the permission of the app to access their data, Asana's servers redirect the user back to the third party app with information that can be used by the application to make API calls to Asana's servers. This redirect is the step that we are making more secure.

If an Asana integration app is using an unencrypted redirect address (where the url begins with `http`) as their callback location, it's possible for a third party to catch the plaintext information that Asana is returning and use it to impersonate the application. Rather than redirecting to a server that is expecting an unencrypted connection, we are making the entire workflow happen with SSL/TLS encryption. This means that all redirect URLs for integrating apps must redirect to a secure server which uses `https` as its scheme.

Asana will soon disallow new application registrations which use unencrypted connections for redirect URLs. In addition:

**In mid-August, we will begin refusing redirects to existing applications which use `http`.**

#### How to make the change in Asana

Asana will soon disallow new application registrations which use unencrypted connections for redirect URLs. In mid August, we will enforce the new redirect behavior If you have an existing application that may be using an unencrypted redirect, please check your application settings to ensure you are returning to an `https` address during the OAuth authentication process. You can check your settings on the Developer App Management page. Follow this link to your [Account Settings dialog](https://app.asana.com/-/account_api) or click your picture in the Asana application and navigate to the "My Profile Settings" link, where you can find the "Apps" tab. At the bottom of this tab there is a link to "Manage Developer Apps" Click on the name of your application under the "Apps You Own" heading to double check its settings.

![Manage Developer Apps link](https://luna1.co/a90b10.png "Manage Developer Apps")

The field that will require checking is "Redirect URL". If this field begins with "http", you will have to implement the changeover to https.

![Redirect URL field](https://luna1.co/53d38d.png "Redirect URL")

#### How to make the change on your server

For non-production or personal use, you may wish to check out [stunnel](https://www.stunnel.org/index.html), which can act as a proxy to receive an encrypted connection, decrypt it, and forward it on to your application. For development work, you may wish to create a self-signed SSL/TLS certificate for use with your web server; for production work you should secure your server by purchasing a certificate from a [certificate authority](https://en.wikipedia.org/wiki/Certificate_authority). A short summary of the steps for each of these processes can be read [here](https://www.digitalocean.com/community/tutorials/openssl-essentials-working-with-ssl-certificates-private-keys-and-csrs).

Your application will need to be configured to accept SSL/TLS connections, but for many apps, this will simply require a configuration update of your application server. Instructions for [Apache](https://httpd.apache.org/docs/2.4/ssl/ssl_howto.html) and [Nginx](http://nginx.org/en/docs/http/configuring_https_servers.html) can be found on their respective websites, and most popular application servers will contain documentation on how to proceed.

This change will ensure that all of our users can continue to use Asana and our partner integrations securely. We appreciate your support and help! If you have any questions or feedback, you can contact the api team at [api-support@asana.com](mailto:api-support@asana.com) for assistance.

Thanks,

Matt Bramlage, Asana Developer Advocate
