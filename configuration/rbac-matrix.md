# Role-Based Access Control (RBAC) Matrix

Access to downstream applications is entirely automated using Okta Group Rules based on Active Directory memberships. No manual assignments are made.

| AD Security Group | Okta Routing Group | Granted Application Access |
| :--- | :--- | :--- |
| `sg-executive` | `app-gitlab-maintainers` | GitLab (Maintainer) |
| `sg-executive` | `app-servicenow-approvers` | ServiceNow (Change Approver) |
| `sg-engineering-java` | `app-gitlab-developers` | GitLab (Developer) |
| `sg-engineering-java` | `app-servicenow-standard` | ServiceNow (ITIL Standard) |
| `sg-sales-standard` | `app-salesforce-standard` | Salesforce (Chatter Free User) |
| `sg-sales-leadership` | `app-salesforce-moderators` | Salesforce (Chatter Moderator User) |
