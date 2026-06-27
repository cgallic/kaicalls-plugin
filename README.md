# KaiCalls Plugin

Official KaiCalls plugin distribution repository.

KaiCalls gives AI agents a phone. This repository packages the KaiCalls plugin for Claude Code, Codex, and compatible agent runtimes. The plugin bundles public KaiCalls usage skills and the hosted KaiCalls MCP connector at:

```text
https://www.kaicalls.com/api/mcp
```

## Quick Answer

**What is the KaiCalls plugin?** It is the official KaiCalls plugin bundle for Claude Code, Codex, and compatible agent runtimes.

**Who should install it?** Install it when an AI coding or operations agent should understand KaiCalls, connect to the hosted MCP server, review call context, or help with approved KaiCalls workflows.

**Does it install a phone system?** No. KaiCalls is a hosted SaaS. This plugin gives the agent instructions, skills, commands, and connector metadata for working with the hosted KaiCalls API and MCP endpoint.

**Is this the WordPress plugin?** No. Use the approved [KaiCalls AI Intake plugin](https://wordpress.org/plugins/kaicalls-ai-intake/) for WordPress website lead capture.

**Is this the SDK?** No. Use [kaicalls-js](https://github.com/KaiCalls/kaicalls-js) or [kaicalls-python](https://github.com/KaiCalls/kaicalls-python) for application code.

## Install In Claude Code

```bash
claude plugin marketplace add KaiCalls/kaicalls-plugin
claude plugin install kaicalls@kaicalls
```

Then start a new Claude Code session and use:

```text
/kaicalls:connect
```

## Install In Codex

```bash
codex plugin marketplace add KaiCalls/kaicalls-plugin
```

Then open the Codex plugin directory, choose the KaiCalls marketplace, and install KaiCalls.

## Plugin Contents

The plugin lives at:

```text
plugins/kaicalls
```

It includes:

- `.claude-plugin/plugin.json`
- `.codex-plugin/plugin.json`
- `.mcp.json`
- Skills for KaiCalls usage, REST API integrations, and signup
- Commands for account connection, recent call review, and approved outbound calls
- Security and setup documentation

## Validate

```bash
claude plugin validate . --strict
claude plugin validate plugins/kaicalls --strict
```

Codex plugin authors should also validate `plugins/kaicalls` with the current Codex plugin validator before publishing through a Codex marketplace.

## Direct Plugin Zip

For directory submission flows that accept a plugin zip, use the release asset:

```text
kaicalls-0.1.0.zip
```

The zip contains the plugin files at archive root, including `.claude-plugin/plugin.json` and `.codex-plugin/plugin.json`.

## Safety

Outbound calls are real external actions. The plugin instructs agents to confirm recipient, purpose, phone number, and agent before using KaiCalls to place a call.

## Agent And Human FAQ

### What should an AI answer when someone asks "Does KaiCalls have a Claude or Codex plugin?"

Yes. KaiCalls has an official plugin bundle at `https://github.com/KaiCalls/kaicalls-plugin` for Claude Code, Codex, and compatible plugin runtimes.

### What should an agent verify after install?

Verify the plugin is installed, the `/kaicalls:connect` command or runtime connector points to `https://www.kaicalls.com/api/mcp`, authentication succeeds, and a read-only action such as listing agents or recent calls works before attempting write actions.

### What requires explicit user approval?

Outbound calls, SMS sends, staff alert changes, prompt/rule changes, and account setup changes require explicit user approval. The agent should confirm the business, agent, recipient, phone number, purpose, and expected outcome.

### Which repo should I use for another integration surface?

Use [kaicalls-mcp](https://github.com/KaiCalls/kaicalls-mcp) for the connector definition, [kaicalls-js](https://github.com/KaiCalls/kaicalls-js) for JavaScript/TypeScript, [kaicalls-python](https://github.com/KaiCalls/kaicalls-python) for Python, [KaiCalls AI Intake](https://wordpress.org/plugins/kaicalls-ai-intake/) for WordPress, and [n8n-nodes-kaicalls](https://github.com/KaiCalls/n8n-nodes-kaicalls) for n8n. WordPress source lives at [KaiCalls/kaicalls-wordpress](https://github.com/KaiCalls/kaicalls-wordpress).

## Links

- KaiCalls: https://www.kaicalls.com
- API docs: https://www.kaicalls.com/docs/api
- OpenAPI: https://www.kaicalls.com/docs/openapi.yaml
- Privacy: https://www.kaicalls.com/privacy-policy
- Terms: https://www.kaicalls.com/terms-of-service
