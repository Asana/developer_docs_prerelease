---
parent-title: News
title: Using custom fields with Asana's API
_template: dev-page
_layout: default

# Post Meta
meta-month: September
meta-date: 15
meta-year: 2016
---
Now you can track anything in Asana with our newest feature, custom fields. With custom fields, users and integration developers can associate structured data with projects and tasks in Asana. The addition of custom fields enables new workflows in the Asana app and API. Most significantly, applications that previously had more limited data storage options can now store this data using custom fields.

Custom fields offer several advantages over the current ways of adding workflow-specific information to Asana tasks:

* No special knowledge is required on the part of users.
* Fields are visible to both integrations and users.
* Fields specify structure with field type, and semantics are specified by the field&rsquo;s name.
* They provide an ideal interface between Asana and other applications.

Custom fields open new opportunities to use Asana with scripts and integrations, and we&rsquo;re excited to see the many ways integrations can connect with Asana like never before!

### No special knowledge is required on the part of users

Custom fields allow users of the Asana application to access and manipulate data in a way that is much more user-friendly and generalized. Previously, adding additional information to tasks that are outside the core set of fields that Asana provides would require users to know and honor rules about how the information was stored in the task. Now the user experience is much better. Rather than making users store information in a way that integrations can use, custom fields allow users to access customized information in a natural way.

### Fields are visible to both integrations and users

Custom fields are visible and editable by both users and integrations, so it is possible for both to coexist and operate on the same data. Previously, to store arbitrary machine-parseable information in Asana without risking users breaking the integration required the &ldquo;external&rdquo; property on tasks. Of course, the downside is that this is not visible to users. This was more restrictive for enabling full interaction between users and integrations; these restrictions are now opened with custom fields.

### Fields specify structure with field type, and semantics are specified by the field's name

When managing data, it&rsquo;s best to be able to infer both the shape or schema of the data and its purpose. The shape of the data allows programs to be able to bring information into a structure that they can work with, and the semantic purpose of the data helps define what that information represents and the actions that can be performed with it.

Imagine trying to store information about a referral in a candidate tracking project. It&rsquo;s possible to store this information in the task description, but this is underspecified: there&rsquo;s some information somewhere in a sea of text and integrations have to be built with parsers to extract this information before they can use it. A custom text field named &ldquo;Primary Phone&rdquo;, however, places a specified shape of data (a string) with a meaning (a phone number) in a place that makes the information both meaningful and manageable. It&rsquo;s much easier for users and integrations to know what this information means and how it should be used.

### Custom fields provide an ideal interface between Asana and other applications

We&rsquo;re making Asana the best place to track and coordinate your workflows, and these flows can come from co-workers, other users, or other applications. Without custom fields, Asana didn&rsquo;t always map to the information from external apps: when integrating with version control systems, for instance, where does the revision number go? The reviewer of a pull request can be assigned, but where does the author of the pull request go? What about classification of the pull request as a new feature or bug-fix?

With custom fields, there are many more possibilities for shaping Asana to fit the information from external sources than ever before. When writing an integration between a version control system, now it&rsquo;s possible to have a dedicated text field for the revision number and author, an enum to classify the type of pull request, and other pieces of information.

In fact, this is exactly what our integration partner, Unito, has been developing with custom fields.

## Unito and Asana/GitHub sync

Unito is an application that integrates and syncs information from various sources to smooth workflows and connect project management tools so that no-one is left out of the loop. Managing tasks in Asana and commenting on an issue in GitHub duplicates the information about the issue and creates more work to keep the information in both locations current. There&rsquo;s much better efficiency when comments in Asana get applied to the GitHub issue, or GitHub commits and pull requests automatically show up in Asana.

Unito has built a connector to bridge Asana and GitHub to make this much easier. This connector uses custom fields in Asana for a variety of mappings from GitHub. For example, GitHub milestones can be mapped to a custom field named &ldquo;Milestone,&rdquo; so it&rsquo;s clear inside of Asana what the context for tasks are. Mark a task as a duplicate, or as a bug or feature, and both Asana and GitHub will stay in sync as Unito manages the mapping and syncing between the two. We encourage you to sign up for [Unito](/apps/unito) and try the integration to check it out for yourself!

## Asana2sql
A common request we receive is for an example that imports and exports data from Asana to an external database for later processing. So we built [asana2sql](https://github.com/Asana/asana2sql), a tool which pulls information from Asana and stashes it in any sql-compatible database. This allows for offline access to Asana data for reporting, analysis, and offline processing.

Asana2sql was built to utilize custom fields. As a user of the Asana API, reviewing this project is a great way to see an example of how custom fields can be accessed. This is also a great way to contribute to open source projects that Asana provides to our community! If you&rsquo;re interested in furthering Asana&rsquo;s integrations and assisting other developers in getting started with Asana and custom fields, feel free to clone this project and submit pull requests for our team!

Custom fields are now available in Asana&rsquo;s API. Go check out the [Getting Started guide](/developers/documentation/getting-started/custom-fields) on custom fields to see how you can add more power and flexibility to your integration!
