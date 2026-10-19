# Action Logging Rule

## Purpose
Agents must maintain a structured history of all interactions and changes made in this repository.

## Instructions
1. **Locate or Create Log File**:
   - Always check for the existence of `log.yaml` (or create it at the workspace root `/home/tito/repos/LDD-demo-game/log.yaml` if it does not already exist).
   - If initializing `log.yaml`, initialize it with an empty entries list:
     ```yaml
     entries: []
     ```

2. **Log Each Action / Turn**:
   - For every completed user request/turn, append a new entry to the `entries` list in `log.yaml`.
   - Always follow the schema below.

## Schema
Each log entry must follow this structure:

```yaml
- timestamp: "<ISO 8601 timestamp, e.g., 2026-10-19T18:52:12-05:00>"
  user_prompt: |
    <exact or summarized user prompt>
  files_changed:
    - "<path to file 1 relative to workspace root>"
    - "<path to file 2 relative to workspace root>"
  brief_description: |
    <concise summary of actions taken and changes made>
```

### Field Definitions
- **`timestamp`** *(string)*: ISO 8601 formatted timestamp of when the action occurred.
- **`user_prompt`** *(string)*: The prompt provided by the user.
- **`files_changed`** *(list of strings)*: List of file paths modified, added, or removed. If no files were modified, provide an empty list `[]`.
- **`brief_description`** *(string)*: Brief description detailing the actions taken, decisions made, and rationale.
