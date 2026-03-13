# Gemini CLI ACP Adapter Extension

This extension enables [AionUI](https://github.com/iOfficeAI/AionUi) to use Gemini CLI as an AI agent backend via the Agent Client Protocol (ACP).

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

2. Copy this extension folder into the AionUI extensions directory:
   ```bash
   cp -r . ~/.aionui/extensions/gemini-acp-extension
   ```

3. Restart AionUI. The "Gemini CLI" agent should now appear in the agent selection list.

## Protocol Verification

This extension uses the `--experimental-acp` flag to start Gemini CLI in ACP mode. You can manually verify the protocol is working by running:

```bash
echo '{"jsonrpc":"2.0","method":"initialize","params":{"protocolVersion":1,"clientInfo":{"name":"Test"}},"id":1}' | gemini --experimental-acp
```

(Note: The process will wait for further input after responding, as it is a persistent server).
