# Fix AionUi i18n Structure

## Objective
Update the internationalization (i18n) configuration to correctly match the structural mapping format used by AionUi, removing the incompatible VS Code-style `%key%` string placeholders.

## Key Files & Context
1. `aion-extension.json`
2. `i18n/en-US/extension.json`

## Implementation Steps

### Step 1: Update `aion-extension.json`
Replace the `%key%` placeholders with their default English strings so the extension functions correctly without relying purely on placeholder replacement.
- Change `displayName` to `"Gemini CLI ACP Adapter"`
- Change `description` to `"An ACP adapter for Gemini CLI, enabling advanced agentic capabilities."`
- In `acpAdapters[0]`, change `name` to `"Gemini CLI"`
- In `acpAdapters[0]`, change `description` to `"Gemini CLI agent with full tool-use and MCP server integration."`

### Step 2: Update `i18n/en-US/extension.json`
Restructure the JSON to use AionUi's object path-based mapping. The new structure will define top-level strings directly and map contributes items by their array identifier (`id`).

```json
{
  "displayName": "Gemini CLI ACP Adapter",
  "description": "An ACP adapter for Gemini CLI, enabling advanced agentic capabilities.",
  "acpAdapters": {
    "gemini-cli-agent": {
      "name": "Gemini CLI",
      "description": "Gemini CLI agent with full tool-use and MCP server integration."
    }
  }
}
```

## Verification & Testing
- Inspect `aion-extension.json` to ensure there are no remaining `%...%` strings.
- Verify that `i18n/en-US/extension.json` correctly matches the ID `gemini-cli-agent` to the nested translation fields.
