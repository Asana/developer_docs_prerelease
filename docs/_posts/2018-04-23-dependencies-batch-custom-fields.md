---
parent-title: News
title: Dependent on API - April 2018 API Updates
_template: dev-page
_layout: default

# Post Meta
meta-month: April
meta-date: 23
meta-year: 2018
---

### Dependencies make Timeline available to integrations

In late March, Asana launched our newest feature: [Timeline](https://blog.asana.com/2018/03/new-asana-timeline-view/), a tool to enable project planners and contributors organize the sequencing and timing of their work. To support integrations that would like to use Timeline, we shipped a long-standing Asana feature to our API users: [dependencies](/developers/api-reference/tasks#dependencies).

While dependencies existed in Asana before Timeline, they became more useful with this new way to view project progress. Timeline uses dependencies to draw the lines between tasks, so setting and adjusting dependencies and start/end dates enables integrations to set up workflows that are useable in the Timeline view. This means that integrations can now take advantage of new use cases with Timeline to connect to other apps or to build custom workflows with Asana's API.

### Batch API calls for faster processing

Making API calls sequentially one after another can lead to slow-feeling integrations. Attempting to improve performance through making parallel requests is complex and requires careful engineering. To provide a middle ground, Asana has launched a [batch API](/developers/documentation/getting-started/batch-api) to make bulk operations easy. This has several benefits, including making parallelization feasible for browser integrations (which are currently limited by the browser to a small number of parallel requests). It also reduces the round-trip latency costs to only occur once per batch instead of once per action. Check out [our documentation](/developers/documentation/getting-started/batch-api) for more details.

### Integration-created custom fields

Previously, it was not possible for integrations to create or edit custom fields in a workspace, they could only associate *existing* custom fields with projects. This was cumbersome, because setting up a custom field for your integration would require having a user set up the custom field for the integration, followed by telling the integration what custom field they just made.

We've now shipped endpoints to [create and edit custom fields in our API](/developers/api-reference/custom_fields#create) to enable integrations to set up their own custom fields. Note that integration-defined custom fields exist in the workspace. Like any other custom field, users can change the definition of these fields. We recommend you use caution, avoid assumptions about the state of custom fields, and program defensively.

### Project Memberships

Last year Asana added the ability to have team members in a project in [comment-only mode](/guide/help/permissions/user-permissions) to help keep tasks organized and less likely to be accidentally changed. We've released a new API resource called [`project_memberships`](/developers/api-reference/project_memberships) to display this information. Now it's possible to query directly if a user (or an integration authorized on the user's behalf) has the ability to make changes to the tasks in a project according to access rules in Asana.

We'll keep you updated as Asana's API gets new features and modifications! To stay up to date with the latest news, be sure to subscribe to our developer newsletter via the form in the sidebar.
