# Claude Benchling Integration Skill

A Claude skill for working with the Benchling life sciences R&D platform through its Python SDK and REST API. It helps with registry entities, inventory, electronic lab notebooks, workflow automation, events, and Data Warehouse analytics.

## What It Covers

- **Authentication and setup:** API key and OAuth client-credentials configuration, secure credential handling, and SDK installation.
- **Registry management:** Create, read, update, list, and register DNA, RNA, amino-acid sequences, custom entities, and mixtures.
- **Inventory operations:** Work with containers, boxes, locations, plates, and item transfers.
- **Electronic lab notebooks:** Create and manage entries, templates, and links between notebook records and registry entities.
- **Workflow automation:** Create and update workflow tasks, monitor asynchronous operations, and automate routine laboratory processes.
- **Events and integrations:** Design event-driven integrations, including AWS EventBridge patterns.
- **Analytics:** Use the Benchling Data Warehouse for SQL-based reporting and historical analysis.

## Repository Structure

```text
.
├── SKILL.md
└── references/
    ├── api_endpoints.md
    ├── authentication.md
    └── sdk_reference.md
```

- `SKILL.md` contains the main instructions and task workflows.
- `references/authentication.md` provides deeper authentication and credential guidance.
- `references/sdk_reference.md` contains additional Python SDK patterns.
- `references/api_endpoints.md` documents REST API endpoint usage.

## Installation

Clone the repository into your personal Claude skills directory:

```bash
git clone https://github.com/Brajesh31/claude-benchling-integration-skill.git ~/.claude/skills/benchling-integration
```

If the directory already exists, update it with:

```bash
cd ~/.claude/skills/benchling-integration
git pull
```

## Configuration

Install the official Benchling Python SDK in the environment used for your integration:

```bash
python -m pip install benchling-sdk
```

Configure your Benchling tenant URL and credentials using environment variables or a secure secret manager. Do not place API keys, client secrets, or other credentials in prompts, source files, or version control.

Typical configuration values include:

- Benchling tenant URL
- API key, or OAuth client ID and client secret
- The minimum permissions required for the intended operations

The skill provides example setup patterns. Actual access is determined by the Benchling account, tenant configuration, and granted permissions.

## Using the Skill

Ask Claude to perform a Benchling-related task, for example:

```text
Use the benchling-integration skill to explain how to create a DNA sequence
with the Benchling Python SDK.
```

Other suitable tasks include:

- Registering a set of DNA sequences.
- Finding inventory containers and their storage locations.
- Creating an ELN entry and linking registry entities.
- Automating workflow task updates.
- Designing a secure event-driven integration.
- Preparing a Data Warehouse query for an operational report.

Provide the relevant tenant context, entity identifiers, schema requirements, and desired outcome. Never share live credentials in the conversation.

## Recommended Workflow

1. Identify the Benchling resource and operation.
2. Confirm the tenant, schema, folder, and permission requirements.
3. Select the Python SDK or REST API approach.
4. Validate inputs and handle pagination or asynchronous tasks.
5. Apply the smallest required change.
6. Verify the resulting resource and report any errors clearly.

## Security Notes

- Keep credentials outside the repository.
- Use environment variables or a secret manager.
- Apply least-privilege access.
- Use HTTPS for API requests.
- Avoid logging tokens or sensitive laboratory data.
- Confirm destructive or irreversible operations before executing them.

## License

This repository is licensed under the MIT License. See [LICENSE](LICENSE).
