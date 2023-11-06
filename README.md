# GitHub-Enterprise-Study

- Team Organization
- Groups/Roles/Users rules (GitHub Repository Roles & Member privileges)
- Repositories Rules: how to create repositories (Repository rulesets)
  - Branch Strategy
- GitHub Actions:
  - scaling Runners
  - how to expose Web-hook endpoints (for Runners and ArgoCD)
- Workflow Check: 1 Workflow for each Programming Language (it's important to understand if they can be used for .NET as well)
  - Using of Sharing Workflows
 

# Teams in GitHub Enterprise

Teams in GitHub Enterprise are an essential component for managing access, organizing members, and streamlining collaboration. This guide will provide a concise overview of how teams work and how they can be utilized effectively within your organization.

### Team Essentials

Teams are groups within your organization that serve several key functions:

- **Access Control:** Teams help manage access permissions to repositories. Owners and maintainers can grant teams different levels of access - admin, read, or write - to organization repositories.
- **Notifications:** Mentioning a team's name allows organization members to send notifications to the entire team.

### Team Visibility

Teams in GitHub Enterprise can be categorized into two types:

- **Visible Teams:** These teams are viewable and mentionable by all organization members.
- **Secret Teams:** Secret teams are only visible to their members and individuals with owner permissions. They are ideal for concealing teams with sensitive information or members, such as those collaborating with external partners or clients. Secret teams cannot be nested or have child teams. External individuals who are not organization members cannot view any teams.

### Exploring Teams

Each team has a dedicated page within the organization. On a team's page, you can access information about team members, child teams, and the team's associated repositories. Owners and maintainers have the ability to modify team settings, update the team's description, and change the team's profile picture from this page.

### Nested Teams

GitHub Enterprise allows you to replicate your group or company's hierarchy with multiple levels of nested teams. A parent team can have several child teams, while each child team is associated with a single parent team. Please note that nesting is not supported for secret teams.

- **Inherited Access Permissions:** Child teams inherit access permissions from their parent, making it easier to manage permissions for large groups.
- **Simplified Notifications:** Members of child teams receive notifications when the parent team is mentioned, facilitating communication across various groups.

For instance, if your team structure is organized as Employees > Engineering > Application Engineering > Identity, granting Engineering write access to a repository also provides this access to Application Engineering and Identity. When you mention the Identity Team or any bottom-tier team, only they receive the notification.

To identify members who share a parent team's permissions and mentions, you can find them under the "Members" tab on the parent team's page. Members of a child team are not direct members of the parent team.

### Preparing to Nest Teams

Before nesting teams, you should perform the following steps:

1. **Audit Existing Teams:** Review the repository access permissions of each existing team.
2. **Choose Parent Teams:** Determine which teams will serve as parent teams in the hierarchy.
3. **Access Permissions:** Assign parent teams repository access permissions that are suitable for all their members and child teams.
4. **Granular Access:** For child teams, provide additional, more granular access to sensitive repositories.

