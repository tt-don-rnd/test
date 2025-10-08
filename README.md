# test
Test Repository for MCP Atlassian Integration

## MCP Atlassian Resources

This repository contains tools and documentation for querying MCP (Model Context Protocol) Atlassian resources.

### Files

- `query_mcp_atlassian.py` - Python script to query and list all available MCP Atlassian resources
- `mcp-atlassian-resources.md` - Comprehensive documentation of available MCP Atlassian resources
- `mcp-atlassian-resources.json` - JSON output of queried resources
- `mermaidtest.mmd` - Workflow diagram showing integration flow

### Usage

Run the query tool to extract all available MCP Atlassian resources:

```bash
python3 query_mcp_atlassian.py
```

This will:
1. Query all available Confluence spaces and pages
2. Query all available Jira projects and issues
3. Display results in JSON format
4. Save results to `mcp-atlassian-resources.json`

### Output

The tool provides structured access to:
- **Confluence**: Spaces, Pages, Attachments, Comments
- **Jira**: Projects, Issues, Boards, Sprints

See `mcp-atlassian-resources.md` for detailed documentation.
