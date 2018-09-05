---
parent-title: News
title: Asana's API gets more powerful with support for boards and sections.
_template: dev-page
_layout: default

# Post Meta
meta-month: February
meta-date: 24
meta-year: 2017
---
Late last year, Asana released a new way to view tasks: [Boards](https://blog.asana.com/2016/11/introducing-boards/). When using a Board view in Asana, tasks show up in columns, with attractive displays of task cards and images that are easy to arrange in a visually pleasing way, and we've loved hearing the positive response for Boards!

We try to launch API features at the same time as their corresponding product features,  but sometimes this isn't possible, especially when the needs of integrations are slightly different and require different considerations than the needs of Asana users. We've been hard at work in Asana's platform measuring how people use boards and characterizing some of the common ways that people might want to interact with them in our API, and we're happy to announce that we've released the first version of our Boards API!

For people familiar with Asana, we've brought a idiom to our platform which can be used with both board and list views: [Sections](https://asana.com/developers/api-reference/sections) are a long-awaited, brand-new API resource which represent the section headers in a list view and the columns in a board view. In this way, code that does not need to know whether a project is a list or board view can use the "sections" property across both views of a project. For those integrations that do need to know if a project is a board or list view, the property "layout" has been added to our [Projects](https://asana.com/developers/api-reference/projects) resource to indicate board versus list views. Finally, we've added the capability to add and move tasks to a particular boards column by specifying it in [addProject](https://asana.com/developers/api-reference/tasks#projects) on tasks and to move sections to [a particular place within a project](https://asana.com/developers/api-reference/sections#reorder). This lets integrations reorder individual tasks or whole columns in board views.

We hope you love it, and can't wait to see what you build with Sections! For support issues, bug reports, or just to share your feedback, feel free to reach out to us at [api-support@asana.com](mailto:api-support@asana.com) and let us know what you think!
