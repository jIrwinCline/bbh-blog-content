---
title: What Can AI Agents Access? Build the Permission Map
slug: what-can-ai-agents-access
description: What can AI agents access? Map files, apps, browser sessions and permissions, then test what agents can read or change before delegating real work.
date: '2026-09-14'
target_query: what can AI agents access
keywords:
- AI agent permissions
- agent permission map
- agent access surface
- AI agent inventory
- AI agent governance
- 'apps: what can agents see?'
- can AI agents access the internet
- can AI agents access websites
- can AI agents get past logins
pillar: Agentic ops & leverage
faq:
- q: Can AI agents access my files?
  a: Only if the agent, app, plugin, or tool you installed has filesystem access. The safe move is to inventory those connections before giving the agent real work.
- q: Can AI agents use websites and online accounts?
  a: Yes, when you give them a browser session, API key, MCP server, extension, or connected app. That access should be scoped and logged.
- q: Can AI agents access the internet?
  a: Yes, if their environment provides a browsing, search or network tool. Internet access alone does not grant access to private accounts or permission to act in them.
- q: Can AI agents get past logins?
  a: They may use an authorized signed-in session or connected account. That is delegated access, not a reason to bypass login controls. Keep authentication and account recovery under human control.
hero_image: images/what-can-ai-agents-access/hero.webp
hero_image_alt: A cluster of reflective metal keys hanging from a keyring
source_draft: 2026-09-14-what-can-ai-agents-access
updated: '2026-11-16'
---
AI agents do not have mystical access to your business. They have the access you connect: files, browser sessions, API keys, MCP servers, plugins, extensions, email accounts, calendars, databases, and payment tools.

That is both the opportunity and the risk. An agent can move faster than a person because it can sit across many tools at once. But if nobody can answer “what can this agent touch?”, then the business has not bought leverage. It has installed an invisible permission problem.

The practical answer is simple: before autonomy, build a permission map.

## What can AI agents access?

AI agents can access anything their host app, tools, credentials, and environment allow them to access. In practice, that usually means four layers: local files, online accounts, connected tools, and automated actions.

A local coding agent might read a project folder, run commands, open a browser, and call MCP servers. MCP, the Model Context Protocol, is a standard way to connect an AI application to external tools and data. A sales agent might read a CRM, draft emails, enrich leads, and update pipeline fields. A marketing agent might inspect analytics, create assets, schedule posts, and report performance. These are possible workflow designs, not capabilities every agent includes.

None of that is automatically good or bad. The question is whether the access matches the job.

For a service business, this is the difference between a useful [agentic system](/agentic-systems) and a loose collection of clever demos. A lead-response agent needs access to form submissions, calendar availability, and approved response templates. It probably does not need payroll files, owner email, unrestricted customer exports, or the ability to change ad budgets without review.

The job defines the access. If access comes first and the job comes later, the system is backward.

## Why does the access surface keep growing?

The access surface keeps growing because agents are moving out of chat and into work surfaces: browsers, desktops, IDEs, team channels, office files, and connected apps.

That is the whole point. A chatbot that only answers questions is limited. An agent becomes useful when it can inspect a page, pull a record, fill a form, write a file, call a tool, or hand a draft to a human for approval.

[Anthropic's computer-use documentation](https://platform.claude.com/docs/en/agents-and-tools/tool-use/computer-use-tool) describes screenshot and mouse/keyboard tools that the application runs in an environment it controls. [OpenAI's MCP documentation](https://developers.openai.com/api/docs/guides/tools-connectors-mcp) describes connections to external services with configurable approvals. The environment and the connection settings matter as much as the model.

The honest catch is that convenience hides accumulation. One browser extension is manageable. One MCP server is manageable. One agent CLI is manageable. Over months, teams add tools, logins, plugins, keys, and project-specific configuration. Nobody remembers the whole map. That is when “we use AI” becomes “we do not know what can act inside the business.”

## What is an AI agent permission map?

An AI agent permission map is a plain-language inventory of what each agent can read, write, run, spend, send, and approve.

It does not need to be fancy. For each agent, list:

- **Purpose:** the job it owns.
- **Data it can read:** folders, apps, records, databases, knowledge bases, conversations.
- **Tools it can use:** browser, shell, APIs, MCP servers, plugins, extensions, automations.
- **Actions it can take:** draft, edit, create, delete, send, purchase, publish, change settings.
- **Credentials it depends on:** service accounts, API keys, browser sessions, OAuth connections.
- **Human gates:** what requires approval before execution.
- **Logs and rollback:** where actions are recorded and how mistakes are reversed.

The permission map is not bureaucracy. It is the operating manual for trust.

Without it, the owner has to choose between two bad options: keep the agent weak enough to be safe, or give it broad access and hope nothing important breaks. With it, the owner can add power one boundary at a time.

That is the work BBH cares about: not “AI everywhere,” but AI placed where it can do useful work with clear limits.

## How should a small business start?

Start with read-only inventory, then move to low-risk drafts, then add controlled actions.

The first step is not buying another agent platform. It is asking what is already installed. [Geiger's README](https://github.com/Atomburstofficial/geiger) describes a read-only inventory of supported agent tools, connections and extensions. Its premise is useful for operators, but an inventory is not proof that every permission is safe or every possible connection was found. Have a technical owner review the tool before running it; the same inventory can be made manually.

For a small business, the first pass can be a simple table:

| Agent or AI tool | Main job | Can read | Can write | Needs approval before |
|---|---|---|---|---|
| Lead triage agent | Sort new inquiries | Forms, CRM, calendar | Draft CRM notes | Sending replies, changing lead stage |
| Content assistant | Draft posts | Brand docs, draft folder | Draft files | Publishing, scheduling |
| Reporting agent | Weekly KPI summary | Analytics, ad dashboard | Report draft | Changing budgets |

This is where “AI as leverage” stays disciplined. Let the agent produce drafts, summaries, checklists, and recommendations first. Then give it narrow write access where the business can tolerate mistakes. Irreversible work stays gated: sending a customer message, deleting records, publishing publicly, spending money, changing access, or modifying production systems.

For [SMB marketing](/smb-marketing), that might mean the agent can read lead forms and draft follow-up, but a human approves any outbound message until the templates and escalation rules are proven. For internal operations, it might mean the agent can draft a weekly scorecard, but not change the source numbers. For a venture experiment, it might mean the agent can create a research memo while the human keeps the final decision. That is the same discipline BBH applies across [ventures](/ventures): move fast where the downside is small, slow down where trust is expensive.

## What should be gated before autonomy?

Gate anything that changes reality outside the draft layer.

Use this rule: if an action affects a customer, bank account, public channel, legal record, production system, credential, or source-of-truth database, it needs either human approval or a very narrow automated policy.

The first gates should cover:

1. **Customer communication.** Agents may draft. Humans approve until quality and escalation paths are proven.
2. **Money movement.** Purchasing, refunds, ad budgets, subscriptions, and payouts need explicit limits.
3. **Record mutation.** CRM status changes, deletions, merges, and bulk edits should be logged and reversible.
4. **Publishing.** Blog posts, social posts, proposals, and website edits need review unless the lane is intentionally autopublished with rollback.
5. **Credential and access changes.** Agents should not grant themselves more power.
6. **Production operations.** Deploys, database migrations, and security-sensitive commands need a separate standard.

This is not anti-agent. It is pro-agent. A trusted agent can be used more often because the owner knows where it stops.

Anthropic's computer-use documentation warns that instructions inside webpages or images can influence an agent against the user's instructions. That is prompt injection: untrusted content trying to become a command. A written instruction to behave is not a substitute for limiting the accounts, tools and actions available.

## Apps: what can agents see?

An agent can see the app data exposed through its connected account and tools, or through the browser or desktop environment you provide. Connecting an app is not the same as sharing every account in that app; inspect the actual account, permissions and operations.

Separate three questions in the permission map: whose account is connected, which records that account can reach, and which actions the agent can request. A tool named “search customers” and one named “export customers” create different exposure even if both use the same CRM login.

For example, a reporting assistant may need campaign totals but not individual customer messages. Give it the smaller reporting view where possible. Record where its report goes, too: reading private data and copying it into a shared channel is still a disclosure, even when the source connection cannot edit anything.

The catch is that read-only does not mean harmless. OpenAI explicitly notes that data sent to a third-party MCP server falls under that server's retention and residency policies. Review the destination as well as the source. Do not put passwords or secret keys into the permission map; record the credential owner and connection name instead.

## Can AI agents access websites and signed-in accounts?

Yes, when a browser or network tool makes those sites available. A signed-in browser can also expose account pages, so treat that session as delegated account access rather than ordinary public web research.

A search tool that returns public results is different from a browser logged into your inbox. For the latter, ask whether the agent can see messages, download attachments, change settings or press Send. Do not infer the answer from the word “browser.” Check the environment and available controls.

Prefer a dedicated work account or isolated browser with only the access that job needs. Keep login recovery and changes to account access with a person. This does not make browser automation risk-free: pages contain untrusted instructions, and interfaces can change. Use review gates before customer-facing or hard-to-reverse actions.

## How do you check an agent's permissions before launch?

Test one allowed task and one forbidden task in a safe environment, then inspect the actual result. A settings screenshot or an agent saying “I cannot do that” is weaker evidence than a tool or source system rejecting the operation.

Use dummy records, not live customers. For a lead assistant, check that it can retrieve a test inquiry and save a draft. Then check that sending without approval is blocked and that an unrelated customer folder cannot be opened. Ask your implementer to show the tool response and the source-system state, not just the agent's final message.

Log the test date, connected account, allowed operation, denied operation and reviewer. Repeat after changing tools, account permissions or browser profiles. If a forbidden action succeeds, reduce access before launch; do not fix it only by adding another sentence to the prompt. This is a practical acceptance check, not a complete security audit.

## What is the BBH take?

The businesses that get value from agents will not be the ones with the most tools installed. They will be the ones with the clearest boundary between draft work, approved work, and autonomous work.

A permission map makes that boundary visible. It tells the owner what the agent can touch today, what it should never touch, and what it can earn access to after the workflow proves itself.

The catch: a permission map will slow the first week down. You will spend time listing tools instead of chasing the newest demo. That is a good trade. The point is not to feel automated. The point is to build a system that still looks sane after six months of real use.

Start with one agent. Give it one job. Map its access. Add one gate. Run it for a week. Review the logs. Then decide what it has earned.

That is how AI becomes leverage instead of another untracked account with a password and a promise.
