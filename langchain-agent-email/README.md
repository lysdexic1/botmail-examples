# botmail-langchain-agent-email

A LangChain agent template that can send and receive emails through Botmail.

## Overview

This agent demonstrates how LangChain agents can integrate with Botmail to:
- Send outbound emails
- Receive and process inbound emails
- Manage workspaces and inboxes

## Setup

1. Install dependencies:
   ```bash
   pnpm add langchain_openai botmail-sdk
   ```

2. Configure environment variables:
   ```env
   ANTHROPIC_API_KEY=your_anthropic_key
   BOTMAIL_API_URL=http://localhost:3456
   MCP_AUTH_TOKEN=your_mcp_auth_token
   ```

3. Run the agent:
   ```bash
   pnpm run agent
   ```

## Agent Capabilities

The LangChain agent can perform:
- `send_email`: Send an email to a recipient
- `list_inboxes`: List available inboxes for the workspace
- `read_email`: Read an email from an inbox
- `search_emails`: Search emails by criteria

## Example Agent

```python
from langchain.agents import initialize_agent, AgentType
from botmail_sdk import BotmailClient

client = BotmailClient(
  api_base="http://localhost:3456",
  auth_token="your_mcp_auth_token"
)

agent = initialize_agent(
  tools=[client.send_email, client.list_inboxes, client.read_email],
  llm="anthropic",
  agent_type=AgentType.OPENAI_FUNCTIONS,
)

# Example: List inboxes
inboxes = agent("List my inboxes")
print(inboxes)
```