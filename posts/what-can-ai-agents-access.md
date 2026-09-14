---
title: What Can AI Agents Access? Build the Permission Map
slug: what-can-ai-agents-access
description: AI agents can access only what you connect. Learn how a permission map inventories tools, files, accounts, and approval gates before autonomy.
date: '2026-09-14'
target_query: what can AI agents access
keywords:
- AI agent permissions
- agent permission map
- agent access surface
- AI agent inventory
- AI agent governance
pillar: Agentic ops & leverage
faq:
- q: Can AI agents access my files?
  a: Only if the agent, app, plugin, or tool you installed has filesystem access. The safe move is to inventory those connections before giving the agent real work.
- q: Can AI agents use websites and online accounts?
  a: Yes, when you give them a browser session, API key, MCP server, extension, or connected app. That access should be scoped and logged.
- q: What is an AI agent permission map?
  a: It is a plain inventory of every file, account, tool, credential, and approval gate an agent can reach before it acts.
- q: Should a small business use AI agents without an access review?
  a: No. Start with read-only work, list the access surface, then add approval gates before letting agents change records, spend money, or contact customers.
hero_image: images/what-can-ai-agents-access/hero.webp
hero_image_alt: Metal keyring with tiny tool-shaped keys for AI agent permissions
source_draft: 2026-09-14-what-can-ai-agents-access
---
AI agents do not have mystical access to your business. They have the access you connect: files, browser sessions, API keys, MCP servers, plugins, extensions, email accounts, calendars, databases, and payment tools.

That is both the opportunity and the risk. An agent can move faster than a person because it can sit across many tools at once. But if nobody can answer “what can this agent touch?”, then the business has not bought leverage. It has installed an invisible permission problem.

The practical answer is simple: before autonomy, build a permission map.

## What can AI agents access?

AI agents can access anything their host app, tools, credentials, and environment allow them to access. In practice, that usually means four layers: local files, online accounts, connected tools, and automated actions.

A local coding agent might read a project folder, run commands, open a browser, and call MCP servers. A sales agent might read a CRM, draft emails, enrich leads, and update pipeline fields. A marketing agent might inspect analytics, create assets, schedule posts, and report performance. A customer-service agent might read support tickets, search a knowledge base, and suggest replies.

None of that is automatically good or bad. The question is whether the access matches the job.

For a service business, this is the difference between a useful [agentic system](/agentic-systems) and a loose collection of clever demos. A lead-response agent needs access to form submissions, calendar availability, and approved response templates. It probably does not need payroll files, owner email, unrestricted customer exports, or the ability to change ad budgets without review.

The job defines the access. If access comes first and the job comes later, the system is backward.

## Why does the access surface keep growing?

The access surface keeps growing because agents are moving out of chat and into work surfaces: browsers, desktops, IDEs, team channels, office files, and connected apps.

That is the whole point. A chatbot that only answers questions is limited. An agent becomes useful when it can inspect a page, pull a record, fill a form, write a file, call a tool, or hand a draft to a human for approval.

Meta’s Muse page frames personal agents around everyday tasks and getting more done. OpenBot’s README uses stronger operator language: each AI coworker can get its own browser, files, and tools, with actions decided before they happen and recorded after. Geiger, a new open-source scanner, describes itself as “a Geiger counter for AI agents” and inventories agents, MCP servers, plugins, hooks, extensions, and local AI apps on a machine.

Those are different products, but they point at the same direction: agents are becoming easier to install and harder to reason about casually.

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

The first step is not buying another agent platform. It is asking what is already installed. Geiger is developer-facing, but its premise is useful for operators: run a read-only scan, identify agent tools and extensions, and ask what each can touch. If you do not use Geiger, use the same method manually.

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

Yoshua Bengio’s warning about agents lying, cheating, and coordinating is a reminder not to treat autonomy as a personality trait. The safe frame is operational: scope, logs, approvals, rollback. You do not need panic. You need a better control surface.

## What is the BBH take?

The businesses that get value from agents will not be the ones with the most tools installed. They will be the ones with the clearest boundary between draft work, approved work, and autonomous work.

A permission map makes that boundary visible. It tells the owner what the agent can touch today, what it should never touch, and what it can earn access to after the workflow proves itself.

The catch: a permission map will slow the first week down. You will spend time listing tools instead of chasing the newest demo. That is a good trade. The point is not to feel automated. The point is to build a system that still looks sane after six months of real use.

Start with one agent. Give it one job. Map its access. Add one gate. Run it for a week. Review the logs. Then decide what it has earned.

That is how AI becomes leverage instead of another untracked account with a password and a promise.
