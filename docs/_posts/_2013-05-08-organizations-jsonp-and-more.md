---
parent-title: News
title: Organizations, JSON-P, and more!
_template: dev-page
_layout: default

# Post Meta
meta-month: May
meta-date: 8th
meta-year: 2013
---
We just wanted to call your attention to a few changes to the API that you may or may not have noticed if you&rsquo;ve been developing with us for some time. Some changes we rolled out just recently, others a little while ago:

- **Organizations.** With the introduction of <a href="https://blog.asana.com/2013/05/organizations-in-asana/" target="_blank" rel="noopener noreferrer">Organizations</a>, we&rsquo;ve updated the API to handle the changes to how your data is organized. These changes are very minor, but could impact you if you&rsquo;ve upgraded. The main change is that in Workspaces that have been upgraded to Organizations, when you create a new Project via the API you must specify a team to put the Project in.
- **JSON-P support.** If you authenticate using <a href="https://blog.asana.com/2013/04/introducing-asana-connect/" target="_blank" rel="noopener noreferrer">Asana Connect</a>, you can now make requests to the API and receive a response in JSON-P format. Simply add the URL parameter `opt_jsonp=CALLBACK`, filling in the name of the function you want in place of `CALLBACK`, and that function will be called with the result. Update: JSON-P support has been deprecated.
- **Task ordering.** You can use the `insert_before` and `insert_after` parameters on the `addProject` Task endpoint in order to insert or move a Task to a specific place within the Project.
- **Subtask re-homing.** You can set the `parent` field on a Task to change which Task it is a subtask of.
- **Followers.** The `addFollowers` and `removeFollowers` Task endpoints allow you to add or remove followers on a Task.

We hope these changes are helpful, and as usual give us feedback at <a href="mailto:api-support@asana.com">api-support@asana.com</a>!
