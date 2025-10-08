# MCP Atlassian Resources

This document describes the available MCP (Model Context Protocol) Atlassian resources and how to access them.

## Overview

The MCP Atlassian integration provides access to various Atlassian products and their resources through the Model Context Protocol.

## Available Resource Types

### 1. Confluence Resources
- **Pages**: Access and read Confluence pages
- **Spaces**: List and navigate Confluence spaces
- **Attachments**: Access files attached to Confluence pages
- **Comments**: Read comments on Confluence pages
- **Labels**: Query pages by labels

### 2. Jira Resources
- **Issues**: Query and read Jira issues
- **Projects**: List available Jira projects
- **Boards**: Access Scrum and Kanban boards
- **Sprints**: Query sprint information
- **Filters**: Access saved Jira filters

### 3. Bitbucket Resources (if available)
- **Repositories**: Access Bitbucket repositories
- **Pull Requests**: Query pull request information
- **Branches**: List repository branches

## Resource URI Format

MCP Atlassian resources typically use the following URI format:

```
atlassian://<product>/<resource-type>/<identifier>
```

### Examples:
- `atlassian://confluence/page/123456` - A specific Confluence page
- `atlassian://confluence/space/MYSPACE` - A Confluence space
- `atlassian://jira/issue/PROJ-123` - A specific Jira issue
- `atlassian://jira/project/MYPROJ` - A Jira project

## Usage

To query MCP Atlassian resources, you would typically:

1. Connect to the MCP server with Atlassian integration
2. List available resources using the appropriate MCP protocol methods
3. Access specific resources using their URI
4. Process the returned data

## Authentication

MCP Atlassian resources require authentication through:
- Atlassian API tokens
- OAuth 2.0 (for cloud instances)
- Personal Access Tokens (for server/data center instances)

## Example Query Results

When querying available resources, you might receive:

```json
{
  "confluence": {
    "spaces": [
      {
        "key": "TEAM",
        "name": "Team Space",
        "type": "global"
      }
    ],
    "recentPages": [
      {
        "id": "123456",
        "title": "Project Documentation",
        "space": "TEAM"
      }
    ]
  },
  "jira": {
    "projects": [
      {
        "key": "PROJ",
        "name": "My Project",
        "type": "software"
      }
    ],
    "recentIssues": [
      {
        "key": "PROJ-123",
        "summary": "Example Issue",
        "status": "In Progress"
      }
    ]
  }
}
```

## Integration Points

Based on the workflow diagram (see `mermaidtest.mmd`), the integration flow is:
1. GitHub → Raw Content Link
2. Processing/Decision Logic
3. Output to:
   - Confluence
   - Viewport (for display)
   - Scroll Sites (if applicable)

## Next Steps

To implement full MCP Atlassian integration:
1. Set up MCP server with Atlassian plugin/integration
2. Configure authentication credentials
3. Define resource access patterns
4. Implement resource querying logic
5. Create output handlers for different Atlassian services
