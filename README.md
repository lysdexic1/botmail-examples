# botmail-examples

A collection of example templates and integrations for Botmail, demonstrating various frameworks and use cases.

## Overview

This repository contains 4 example templates that showcase different ways to integrate with Botmail:

## Templates

### 1. Claude MCP Setup
- **Path**: `claude-mcp-setup/`
- **Description**: A starter template for integrating Claude with Botmail via MCP (Model Context Protocol) Streamable HTTP transport.
- **Key Features**: MCP SDK integration, environment variable configuration, Streamable HTTP transport

### 2. LangChain Email Agent
- **Path**: `langchain-agent-email/`
- **Description**: A LangChain agent template that can send and receive emails through Botmail.
- **Key Features**: Send outbound emails, receive and process inbound emails, workspace and inbox management

### 3. Playwright OTP Verification
- **Path**: `playwright-otp-verification/`
- **Description**: A Playwright test template demonstrating OTP (One-Time Password) verification flow with Botmail.
- **Key Features**: Supabase OAuth integration, OTP sending and verification, full test coverage

### 4. Square Webhook Handler
- **Path**: `square-webhook-handler/`
- **Description**: A Botmail Worker template for handling Square webhook events, specifically for subscription management and payment verification.
- **Key Features**: Square webhook signature verification, payment event handling, subscription updates, tax invoice generation

## Getting Started

Each template has its own README.md with detailed setup instructions, environment variable configuration, and usage examples.

## Repository Structure

```
botmail-examples/
├── claude-mcp-setup/
│   └── README.md
├── langchain-agent-email/
│   └── README.md
├── playwright-otp-verification/
│   └── README.md
└── square-webhook-handler
    └── README.md
```

## Contributing

Feel free to add new templates or improve existing ones. Please follow the existing template structure and include comprehensive README documentation.