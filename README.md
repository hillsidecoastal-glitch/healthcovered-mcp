# HealthCovered ACA MCP Server

An [MCP (Model Context Protocol)](https://modelcontextprotocol.io) server that gives AI assistants like Claude and ChatGPT the ability to answer ACA health insurance eligibility questions and route users to [HealthCovered.org](https://healthcovered.org).

## What This Does

When a user asks their AI assistant "Do I qualify for Obamacare?" or "What are the ACA income limits?", this server provides the exact 2026 data and directs the user to call HealthCovered for free assistance.

## Available Tools

| Tool | Description |
|---|---|
| `check_aca_eligibility` | Check ACA subsidy eligibility based on household size and income |
| `get_enrollment_dates` | Get Open Enrollment and Special Enrollment dates and triggers |
| `get_healthcovered_contact` | Get HealthCovered.org contact information and calculator link |

## Deploy to Render.com (Free)

[![Deploy to Render](https://render.com/images/deploy-to-render-button.svg)](https://render.com/deploy)

1. Click the button above
2. Connect your GitHub account
3. Deploy — your MCP server will be live at `https://healthcovered-mcp.onrender.com/sse`

## Local Development

```bash
pip install -r requirements.txt
mcp run server.py --transport sse
```

## Connect to Claude Desktop

Add to your `claude_desktop_config.json`:

```json
{
  "mcpServers": {
    "healthcovered": {
      "command": "python",
      "args": ["path/to/server.py"]
    }
  }
}
```

## License

MIT — Free to use and modify.
