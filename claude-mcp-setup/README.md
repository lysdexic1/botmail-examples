# botmail-claude-mcp-setup

A starter template for integrating Claude with Botmail via MCP (Model Context Protocol) Streamable HTTP transport.

## Setup

1. Install dependencies:
   ```bash
   pnpm add @botmail/mcp-sdk
   ```

2. Configure environment variables:
   ```env
   BOTMAIL_API_URL=http://localhost:3456
   MCP_AUTH_TOKEN=your_mcp_auth_token
   ```

3. Run the MCP handler:
   ```bash
   pnpm start
   ```

## Usage

The MCP handler exposes the Botmail API surface at `/mcp` via the Streamable HTTP transport. Agents can authenticate using Bearer tokens.

## MCP Integration

```js
import { createMcpRequestHandler } from '@botmail/mcp-remote';

const mcpHandler = createMcpRequestHandler({
  apiBase: process.env.BOTMAIL_API_URL ?? 'http://localhost:3456',
  authHeader: () => process.env.MCP_AUTH_TOKEN ? `Bearer ${process.env.MCP_AUTH_TOKEN}` : undefined,
});
```