# Fix Extension Loading (No Symlinks)

## Objective
Enable AionUI to detect the Gemini CLI ACP extension by moving it from a project directory (linked via symlink) to a direct physical directory, as the AionUI `ExtensionLoader` currently does not support symbolic links.

## Root Cause Analysis
- **AionUI Scanning Logic**: The `ExtensionLoader` in AionUI uses `fs.readdir` with `withFileTypes: true` and then filters for `entry.isDirectory()`. In Node.js, this returns `false` for symbolic links, causing them to be skipped even if they point to valid directories.

## Implementation Steps

### Step 1: Replace Symlink with Actual Directory
Move the project contents directly into the AionUI extensions folder.
- Remove the existing symbolic link: `rm ~/.aionui/extensions/gemini-acp-adapter`
- Create a real directory: `mkdir -p ~/.aionui/extensions/gemini-acp-adapter`
- Copy (or move) all files from `/home/cye/Projects/aion-gemini-acp-extension` into `~/.aionui/extensions/gemini-acp-adapter/`.

### Step 2: Verification
- Restart AionUI.
- Check AionUI logs for any potential validation errors (e.g., `[Extensions] Failed to load manifest...`).
- Verify that `Registry initialized` now reports at least 1 extension.
