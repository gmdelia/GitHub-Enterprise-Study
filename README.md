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

Each team has a dedicated page within the organization. On a team's page, it is possibile to access information about team members, child teams, and the team's associated repositories. Owners and maintainers have the ability to modify team settings, update the team's description, and change the team's profile picture from this page.

### Nested Teams

GitHub Enterprise allows you to replicate your group or company's hierarchy with multiple levels of nested teams. A parent team can have several child teams, while each child team is associated with a single parent team. Please note that nesting is not supported for secret teams.

- **Inherited Access Permissions:** Child teams inherit access permissions from their parent, making it easier to manage permissions for large groups.
- **Simplified Notifications:** Members of child teams receive notifications when the parent team is mentioned, facilitating communication across various groups.

For instance, if your team structure is organized as Employees > Engineering > Application Engineering > Identity, granting Engineering write access to a repository also provides this access to Application Engineering and Identity. When you mention the Identity Team or any bottom-tier team, only they receive the notification.

To identify members who share a parent team's permissions and mentions, it is possibile to find them under the "Members" tab on the parent team's page. Members of a child team are not direct members of the parent team.

### Preparing to Nest Teams

Before nesting teams, you should perform the following steps:

1. **Audit Existing Teams:** Review the repository access permissions of each existing team.
2. **Choose Parent Teams:** Determine which teams will serve as parent teams in the hierarchy.
3. **Access Permissions:** Assign parent teams repository access permissions that are suitable for all their members and child teams.
4. **Granular Access:** For child teams, provide additional, more granular access to sensitive repositories.

[Reference](https://docs.github.com/en/organizations/organizing-members-into-teams/about-teams)

# Roles in Organization

Roles play a pivotal role in controlling access and permissions within your GitHub Enterprise organization. This section provides a concise overview of the different roles available and how they can be assigned to individuals and teams.

### About Roles

To carry out actions on GitHub, individuals must have the necessary permissions for specific accounts or resources. Permissions grant the ability to perform specific actions, such as creating a pull request or modifying billing settings. Roles, on the other hand, encompass a collection of permissions that can be allocated to individuals or teams.

- **Repository-Level Roles:** These roles grant varying levels of access to repositories for organization members, external collaborators, and teams. Refer to "Repository roles for an organization" for detailed information.

- **Team-Level Roles:** Team-level roles are designed to provide permissions for managing a team. For instance, the team maintainer role grants administrative permissions over a team member. Learn more about "Assigning the team maintainer role to a team member."

- **Organization-Level Roles:** Organization-level roles encompass sets of permissions that can be assigned to individuals or teams for overseeing the organization, its repositories, teams, and settings. For an extensive list of organization-level roles, explore "About organization roles."

### Understanding Organization Roles

A variety of organization-level roles are available to help manage access and resources within your organization. Each role is associated with specific permissions. Detailed information about the individual permissions included in each role can be found in "Permissions for organization roles."

For organizations owned by enterprise accounts, enterprise owners have the flexibility to join your organization with any role. Learn more in "Managing your role in an organization owned by your enterprise."

- **Organization Owners:** Organization owners possess complete administrative access to the organization and its resources. It is advisable to limit the number of organization owners, but there should be at least two individuals with this role to ensure ownership continuity. For insights, visit "Maintaining ownership continuity for your organization."

- **Organization Members:** The default role for individuals in an organization is an organization member. Members have various permissions, including the ability to create repositories and project boards.

- **Organization Moderators:** Moderators, in addition to their member permissions, have the authority to block and unblock non-member contributors, set interaction limits, and hide comments in public repositories owned by the organization. Discover more about "Managing moderators in your organization."

- **Billing Managers:** Billing managers have the ability to manage the billing settings for the organization, such as payment information. This role is particularly useful when regular organization members do not typically have access to billing resources. Learn how to "Add a billing manager to your organization."

- **Security Managers:** Please note that the security manager role is in public beta and subject to change. Security managers can be assigned by organization owners to any team. This role provides team members with permissions to manage security alerts and settings across the organization, along with read permissions for all repositories. This is a valuable option for organizations with security teams. "Managing security managers in your organization" provides more details.

- **GitHub App Managers:** By default, only organization owners can manage GitHub App registrations owned by the organization. GitHub App managers are designated by owners to oversee the settings of these registrations. "Adding and removing GitHub App managers in your organization" explains the process.

- **Outside Collaborators:** To maintain data security while granting access to repositories, outside collaborators can be added. These individuals have access to one or more organization repositories but are not official members of the organization. They may include consultants or temporary employees.

Understanding these roles and their respective permissions is essential for effective management of your GitHub Enterprise organization.

[Reference](https://docs.github.com/en/enterprise-cloud@latest/organizations/managing-peoples-access-to-your-organization-with-roles/roles-in-an-organization)

## Adding Outside Collaborators to Organization's Repositories

This section outlines the process of allowing individuals who are not members of your organization to access repositories owned by your organization.

### Who Can Use This Feature

Individuals with administrative access to a repository can add outside collaborators to that repository.

### Understanding Outside Collaborators

An outside collaborator refers to an individual who is not a member of your organization but has access to one or more repositories owned by your organization. The level of access granted to each outside collaborator can be customized to suit your needs. When adding an outside collaborator to a repository, you'll also need to include them in any forks of the repository that you want them to access. If you're adding an outside collaborator to a private or internal fork of a repository, please note that the collaborator must be a member of the enterprise or a collaborator on the upstream repository.

It's important to be aware that adding an outside collaborator to a private or internal repository consumes one of your paid licenses. To learn more about this, consult "About per-user pricing."

### Special Considerations

- **Invitation Restrictions:** Organization owners have the ability to control who can invite collaborators. For a deeper understanding, explore "Setting permissions for adding outside collaborators."

- **Two-Factor Authentication:** If your organization mandates two-factor authentication, all outside collaborators must enable this feature before accepting invitations to collaborate on a repository. For further insights, read "Requiring two-factor authentication in your organization."

### Adding Outside Collaborators to a Repository

To provide outside collaborators with access to a repository, navigate to your repository settings. This is where it is possibile to configure and manage outside collaborator permissions for the repository.

By understanding this process, it is possibile efficiently collaborate with individuals who aren't official members of your organization while maintaining the necessary access control.

[Reference](https://docs.github.com/en/enterprise-cloud@latest/organizations/managing-user-access-to-your-organizations-repositories/managing-outside-collaborators/adding-outside-collaborators-to-repositories-in-your-organization)


## Repository Roles for Organizations

This section outlines the different repository roles available for organizations, allowing you to fine-tune access to each repository by assigning granular roles. These roles provide individuals and teams with specific access levels, aligning with their responsibilities and requirements.

### Repository Roles for Organizations

You can allocate varying levels of access to repositories owned by your organization by assigning roles to organization members, outside collaborators, and teams. Select the role that best suits the responsibilities of each individual or team in your project, providing them with the necessary access without granting excessive privileges.

The roles for an organization repository, ranked from least access to most access, are as follows:

1. **Read:** This role is recommended for non-code contributors who primarily want to view or discuss your project.

2. **Triage:** Suitable for contributors who need to proactively manage issues, discussions, and pull requests without the ability to make direct changes.

3. **Write:** Designed for contributors who actively push changes to your project.

4. **Maintain:** This role is ideal for project managers who require the ability to manage the repository without access to sensitive or destructive actions.

5. **Admin:** This role is recommended for individuals who need full access to the project, including permissions for sensitive and potentially destructive actions such as managing security or deleting a repository.

You also have the flexibility to create custom repository roles tailored to your organization's needs. For more details, refer to "Managing custom repository roles for an organization."

Organization owners have the authority to set base permissions that apply uniformly to all organization members when accessing any of the organization's repositories. For additional information, see "Setting base permissions for an organization."

Furthermore, organization owners can make decisions about further restricting access to specific settings and actions throughout the organization. To explore various options for specific settings, consult "Managing organization settings."

In addition to overseeing organization-level settings, organization owners possess administrative access to every repository owned by the organization. For more insights, check out "Roles in an organization."

**Warning:** When someone adds a deploy key to a repository, any user possessing the private key can read from or write to the repository (depending on the key's settings), even if they are subsequently removed from the organization.

[Reference](https://docs.github.com/en/enterprise-cloud@latest/organizations/managing-user-access-to-your-organizations-repositories/managing-repository-roles/repository-roles-for-an-organization)
