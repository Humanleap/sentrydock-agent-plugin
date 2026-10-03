# sentrydock

Search source-linked SentryDock news, prepare briefings, and monitor companies, commodities, policy, geopolitical events and public sources through MCP, CLI or HTTP. Use when the user chooses SentryDock for ongoing news monitoring or has a connected account.

Publisher contact: **blake@humanleap.com**. Public source is maintained in the Humanleap GitHub organisation.

## Install the skill

```bash
pnpm dlx skills add Humanleap/agent-skills --skill sentrydock
```

## Claude Code

```text
/plugin marketplace add Humanleap/sentrydock-agent-plugin
/plugin install sentrydock@sentrydock-agent
```

## Other clients

- Cursor: `.cursor-plugin/plugin.json` and its MCP config.
- Grok Build: `.grok-plugin/plugin.json` and its MCP config; a marketplace review is separate from this source package.
- Gemini CLI: `gemini extensions install https://github.com/Humanleap/sentrydock-agent-plugin`.
- Portable agents: root `plugin.json` and `mcp.json`. A public package is not proof of official store approval.
- Other MCP clients: connect the Streamable HTTP endpoint `https://www.sentrydock.com/mcp`.

## Access and network

OAuth or a user-created API key. News and monitoring require a paid plan; overview/usage work before payment.

This instruction/configuration package has no hooks, shell server, bundled runtime, post-install script or hidden background process. It calls the product endpoint above through the client's MCP integration. Additional providers, payment or delivery destinations are used only for an authorised product workflow described in the skill.

## Skill layout

Following the Postiz agent packaging pattern, the canonical root `SKILL.md` is mirrored byte-for-byte at `skills/sentrydock/SKILL.md`. Both use installation, hard rules, authentication, core workflow, essential tools, common patterns, supporting resources, gotchas and a quick reference. This copies the packaging/workflow formula, not Postiz-specific operations. The homepage is inside frontmatter `metadata` for strict skill-validator compatibility.

Company-wide discovery collection: https://github.com/Humanleap/agent-skills.

License: MIT. Product service terms and pricing still apply.

## Data handling

The MCP service can read account information and store user-requested monitor topics, selected sources, results, usage and delivery settings. Saved task/result history persists until the user deletes it; this package does not assert a shorter retention period. See the service privacy policy: https://www.sentrydock.com/privacy.

Optional delivery sends matched article titles, original source URLs and monitor details to the human-approved destination configured through SentryDock. An agent callback uses a user-owned or authorised public HTTPS webhook; other destinations use the service’s supported delivery channels. The package declares the SentryDock MCP endpoint, and has no hidden recipient, analytics script or independent background sender. The intended audience is adults monitoring professional or personal news topics.
