# MCP Atlassian Resources

This document provides an overview of MCP (Model Context Protocol) Atlassian resources and their capabilities.

## Overview

The MCP Atlassian interface provides programmatic access to Atlassian products and services through a standardized protocol. This enables seamless integration with Confluence, Jira, and other Atlassian tools.

## Available Resources

### Confluence Resources

#### Pages
- **List Pages**: Access and list Confluence pages within a space
- **Get Page Content**: Retrieve full content of specific pages including body, metadata, and attachments
- **Search Pages**: Search across Confluence spaces using CQL (Confluence Query Language)
- **Page Hierarchy**: Navigate parent-child relationships between pages

#### Spaces
- **List Spaces**: Enumerate available Confluence spaces
- **Space Details**: Get metadata about specific spaces including permissions and settings
- **Space Content**: Access all content within a particular space

#### Comments and Attachments
- **Page Comments**: Retrieve and manage comments on Confluence pages
- **Attachments**: Access files attached to pages
- **Inline Comments**: Get inline comments and annotations

### Jira Resources

#### Issues
- **Search Issues**: Query Jira issues using JQL (Jira Query Language)
- **Issue Details**: Get comprehensive information about specific issues
- **Issue Comments**: Access comment threads on issues
- **Issue History**: View change history and audit logs
- **Issue Transitions**: Get available status transitions

#### Projects
- **List Projects**: Enumerate accessible Jira projects
- **Project Metadata**: Get project details, components, and versions
- **Project Permissions**: Query project-level access controls

#### Boards and Sprints
- **Agile Boards**: Access Scrum and Kanban board data
- **Sprint Information**: Get sprint details, including start/end dates and goals
- **Backlog Items**: Query backlog and sprint assignments

### User and Permission Resources

#### Users
- **User Profiles**: Access user information and profiles
- **User Activity**: Get user activity streams and recent changes
- **User Mentions**: Find mentions of specific users

#### Groups and Permissions
- **Group Membership**: Query group structures and memberships
- **Permission Schemes**: Access permission configurations
- **Access Controls**: Verify user permissions for specific resources

## Usage Examples

### Example 1: Accessing Confluence Pages

```
Resource Type: confluence.page
Action: list
Parameters:
  - space: TECH
  - limit: 10
```

### Example 2: Searching Jira Issues

```
Resource Type: jira.issue
Action: search
Parameters:
  - jql: "project = DEV AND status = Open"
  - fields: summary, status, assignee
  - maxResults: 50
```

### Example 3: Getting Page Content

```
Resource Type: confluence.page
Action: get
Parameters:
  - pageId: 12345678
  - expand: body.storage,version,space
```

## Resource Query Syntax

### Confluence Query Language (CQL)
- Text search: `text ~ "search term"`
- Space filter: `space = "SPACE_KEY"`
- Type filter: `type = page`
- Date range: `lastModified >= "2024-01-01"`

### Jira Query Language (JQL)
- Project filter: `project = "PROJECT_KEY"`
- Status filter: `status = "In Progress"`
- Assignee filter: `assignee = currentUser()`
- Date range: `created >= -7d`

## Authentication and Access

MCP Atlassian resources require proper authentication:
- API tokens for service accounts
- OAuth 2.0 for user-based access
- Personal Access Tokens (PAT) for individual users

Access is controlled by:
- Atlassian Cloud permissions
- Space and project-level permissions
- Content restrictions and page permissions

## Response Format

All MCP Atlassian resources return data in a standardized format:

```json
{
  "resource_type": "confluence.page",
  "id": "12345678",
  "metadata": {
    "title": "Page Title",
    "space": "SPACE_KEY",
    "version": 5,
    "lastModified": "2024-01-15T10:30:00Z"
  },
  "content": {
    "body": "...",
    "format": "storage"
  }
}
```

## Best Practices

1. **Use Specific Queries**: Narrow down searches with appropriate filters to improve performance
2. **Limit Results**: Use pagination and result limits to avoid overwhelming responses
3. **Cache When Possible**: Store frequently accessed resources locally
4. **Respect Rate Limits**: Be mindful of API rate limits for Atlassian Cloud
5. **Expand Strategically**: Only expand fields that are needed to reduce payload size

## Integration Patterns

### Documentation Lookup
Use MCP Atlassian to quickly find and reference documentation:
- Search Confluence spaces for technical documentation
- Retrieve specific pages for context
- Access related pages through page hierarchy

### Issue Tracking
Integrate with Jira for development workflows:
- Query issues related to current work
- Access issue details and comments
- Track sprint progress and backlog items

### Knowledge Management
Leverage Confluence for team knowledge:
- Search for solutions to common problems
- Access team runbooks and procedures
- Find meeting notes and decisions

## Resource Types Reference

| Resource Type | Description | Primary Actions |
|--------------|-------------|-----------------|
| `confluence.page` | Confluence wiki pages | list, get, search |
| `confluence.space` | Confluence spaces | list, get |
| `confluence.comment` | Page comments | list, get |
| `confluence.attachment` | File attachments | list, get, download |
| `jira.issue` | Jira issues | search, get |
| `jira.project` | Jira projects | list, get |
| `jira.board` | Agile boards | list, get |
| `jira.sprint` | Sprint information | list, get |
| `jira.user` | User profiles | get, search |

## Error Handling

Common error scenarios:
- **404 Not Found**: Resource doesn't exist or user lacks permissions
- **401 Unauthorized**: Authentication failure or expired credentials
- **403 Forbidden**: Insufficient permissions for requested resource
- **429 Rate Limited**: Too many requests, retry with backoff
- **500 Server Error**: Atlassian service issues, retry later

## Limitations

- Rate limits apply based on Atlassian Cloud tier
- Some resources may require specific license types
- Large responses may be paginated
- Real-time updates require webhooks or polling
- Historical data retention varies by product and plan

## Further Reading

- [Atlassian REST API Documentation](https://developer.atlassian.com/cloud/)
- [Confluence Cloud REST API](https://developer.atlassian.com/cloud/confluence/rest/)
- [Jira Cloud REST API](https://developer.atlassian.com/cloud/jira/platform/rest/)
- [Model Context Protocol Specification](https://modelcontextprotocol.io/)

---

*This document provides a reference for MCP Atlassian resource capabilities. Actual implementation and available resources may vary based on your Atlassian configuration and MCP server setup.*
