---
parent-title: News
title: Minor fixes, changes and additions
_template: dev-page
_layout: default

# Post Meta
meta-month: April
meta-date: 3rd
meta-year: 2012
---
- Fixed a bug where requests that should return 400 were returning 500s or unparsable content.
- Renamed `Task.schedule_status` to `assignee_status` and changed its value of `ok` to `later`
- Added `Task.due_on` so you can get and set due dates for Tasks with the API.
