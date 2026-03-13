# Gemini CLI ACP Adapter Extension

This extension enables [AionUI](https://github.com/iOfficeAI/AionUi) to use Gemini CLI as an AI agent backend via the Agent Client Protocol (ACP).
Based off of the extension examples in https://github.com/iOfficeAI/AionUi/tree/main/examples.

## Features

- **Standardized Integration:** Plugs Gemini CLI directly into AionUI's multi-agent interface.
- **Full Capabilities:** Supports Gemini CLI's tool-use, MCP server integration, and workspace context.
- **Streaming Support:** Real-time response streaming for a smooth chat experience.

## Prerequisites

- [Gemini CLI](https://geminicli.com) must be installed and available in your PATH.
- Verify installation by running:
  ```bash
  gemini --version
  ```

## Installation

1. Create an extensions directory for AionUI if it doesn't exist:
   - **macOS/Linux:** `~/.aionui/extensions/`
   - **Windows:** `%USERPROFILE%\.aionui\extensions\`

2. Clone this extension folder into the AionUI extensions directory:
   ```bash
   cd ~/.aionui/extensions
   git clone https://github.com/chen-ye/aion-gemini-acp-extension.git
   ```

3. Restart AionUI. The "Gemini CLI" agent should now appear in the agent selection list.
