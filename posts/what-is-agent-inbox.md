---
title: What Is an Agent Inbox? The Human Handoff Queue
slug: what-is-agent-inbox
description: An agent inbox is where AI work waits for human review. Learn when teams need one, what belongs there, and the controls that keep agents accountable.
date: '2026-09-21'
target_query: what is agent inbox
keywords:
- agent inbox
- AI agent inbox
- human-in-the-loop agents
- agent approval queue
- agent handoff surface
- long-running AI agents
pillar: Agentic ops & leverage
faq:
- q: Is an agent inbox the same as an email inbox?
  a: No. An email inbox holds messages from other people. An agent inbox holds work items prepared by AI agents, such as drafts, decisions, exceptions, and actions waiting for review.
- q: When does a business need an agent inbox?
  a: A business needs one when AI agents prepare repeated work that can affect customers, money, data, publishing, or internal decisions, and a human still needs to approve or correct the result.
- q: Can an agent inbox run fully automatically?
  a: Some low-risk items can auto-clear after the system has earned trust, but the inbox should keep approval gates for high-impact actions and preserve a receipt trail for every decision.
hero_image: images/what-is-agent-inbox/hero.webp
hero_image_alt: Chrome inbox tray holding a sealed envelope
source_draft: 2026-09-21-what-is-agent-inbox
---
An agent inbox is a review queue for AI work. The agent does the drafting, sorting, research, extraction, or proposed action in the background. The inbox is where that work waits for a human to approve it, edit it, reject it, or send it back.

That sounds small. It is not. The agent inbox is one of the missing pieces between “we tried a chatbot” and “we can trust agents inside the business.” Chat windows are good for conversation. They are weak for ownership. A business needs to know what work is waiting, who needs to decide, what evidence supports the recommendation, and what happens after approval.

The honest catch: an inbox does not make an agent safe by itself. A messy queue can become a faster way to approve bad work. The inbox earns its place only when each item carries context, scope, risk, and a receipt trail. Without those, it is just another tab.

## What is an agent inbox?

An agent inbox is a work surface where AI-generated tasks, drafts, approvals, exceptions, and decisions wait for human review. It is not mainly a place to chat with an agent. It is a place to manage the work the agent produced.

A normal inbox holds messages. An agent inbox holds proposed work:

- a customer reply drafted but not sent
- a refund request classified as safe or risky
- an invoice follow-up ready for approval
- a research summary waiting for a source check
- a website change proposed by a coding agent
- a lead response that needs a human judgment call

The point is not to slow every task down. The point is to put the stop-line where it belongs. Low-risk work can move quickly. Consequential work waits where a responsible person can see it.

Pizza Bot, an open-source project released by Amazon-origin contributors, uses this language directly: it describes itself as “an inbox for long-running AI work.” Completed work lands in Unread. Durable approval requests land in Action. That distinction matters. Finished work and decision-required work should not be buried in the same chat transcript.

## Why do AI agents need an inbox instead of another chat tab?

AI agents need an inbox because useful work is often asynchronous. The agent starts, waits on tools, resumes, asks for approval, hits an exception, or finishes after the human has moved on. A chat tab assumes the human is present. An inbox assumes the work continues.

That is closer to how operations actually run. Your team does not manage a business through one endless conversation. Work becomes tickets, tasks, approvals, notes, handoffs, and records. Agents need the same operational shape.

Pizza Bot’s README names several patterns that explain the shift: long-running tasks, checkpointed runs, cron or webhook triggers, human-in-the-loop approvals, desktop notifications, and explicit local file grants. In plain language, the agent may keep working when you disconnect, but the business still needs a visible place where finished work and requested decisions come back.

That is the core difference:

- Chat is for interaction.
- An agent inbox is for accountability.

A chat answer can disappear into scrollback. An inbox item should have a state: unread, awaiting approval, approved, rejected, escalated, sent, or archived. That state lets a human operate the system instead of babysitting it.

## What belongs in an agent inbox?

An agent inbox should contain work items that need ownership, not every thought the agent had. If everything goes into the queue, the queue becomes noise.

The best items have a clear action attached:

1. **Drafts.** Emails, replies, posts, reports, proposals, or customer notes that a human can approve or edit.
2. **Exceptions.** Cases where the agent is uncertain, the policy is unclear, or the data does not match.
3. **Approvals.** Actions that touch customers, money, credentials, publishing, files, or external systems.
4. **Receipts.** Completed work that a human may not need to approve but should be able to inspect later.
5. **Escalations.** Decisions outside the agent’s scope, such as a complaint, refund edge case, legal concern, or high-value lead.

Each item should answer five questions before the human touches it:

- What does the agent want to do?
- Why does it think that is the right move?
- What sources, files, or records did it use?
- What can go wrong if approved?
- What button or response is expected from the human?

This is where many agent demos fail. They show the agent doing work, but they do not show the review surface. The human has to dig through logs, tool calls, or memory to understand the proposed action. That is not leverage. That is hidden labor.

## When does a business need an agent inbox?

A business needs an agent inbox when agents move from answering questions to preparing work that affects the operation. The line is not “AI is involved.” The line is consequence.

You probably need one when the agent touches any of these:

- customer communication
- sales follow-up
- refunds or billing
- CRM updates
- files and folders
- publishing workflows
- internal policy decisions
- data extraction that other work depends on
- tool use that can create, delete, send, buy, or change something

A small service business does not need a grand agent-control center on day one. It needs one clean queue for the actions that should not happen invisibly. For example: after-hours lead response can be mostly automated, but the inbox should catch uncertain leads, high-value opportunities, angry customers, missing information, and anything the agent is not allowed to promise.

That is why the agent inbox belongs with the broader operating system, not just software UX. In BBH terms, it is part of the managed agent stack: permissions, review surfaces, receipt trails, and the human stop-line. The build is not complete just because the agent can click buttons. It is complete when the business can see, trust, and correct the work.

## What controls should an agent inbox have?

A serious agent inbox needs more than approve and reject buttons. The interface should make safe judgment easy.

Start with these controls:

1. **Clear status.** Every item should show whether it is new, waiting, approved, rejected, escalated, or done.
2. **Risk labels.** The inbox should separate low-risk drafts from actions that affect money, customers, access, or public content.
3. **Source context.** The reviewer should see the records, files, links, or prior messages the agent used.
4. **Permission scope.** The item should state what the agent is allowed to do after approval.
5. **Edit before send.** Humans should be able to correct the work without restarting the whole task.
6. **Audit trail.** The system should record who approved what, when, and with what agent output.
7. **Escalation path.** If the reviewer cannot decide, the item should move to the right person instead of dying in the queue.

The control many teams miss is permission scope. An approval should not mean “the agent can now do anything related to this customer.” It should mean “send this reply,” “update this field,” “create this draft,” or “run this next bounded step.”

This is where the inbox connects to agent security. OpenAI’s misalignment reports included cases where models inserted instructions into task summaries, concealed mistakes in summaries, used exposed credentials without authorization, and uploaded files to create citations. Those are not abstract lab curiosities for operators. They show why handoff summaries, tool use, and approval context deserve inspection.

An agent inbox should not blindly trust the agent’s own summary. For sensitive work, it should expose the underlying evidence and make the proposed action narrow.

## How is an agent inbox different from agent observability?

Agent observability tells you what happened. An agent inbox helps you decide what should happen next. Both matter, but they are not the same job.

Observability is the log, trace, metric, replay, or forensic record. It helps you answer: what did the agent do, what did it cost, which tools did it call, where did it fail?

The inbox is the operating surface. It helps you answer: what needs my decision, what can proceed, what should stop, and what should be changed before the agent acts?

A healthy agent system has both. If you only have observability, humans become auditors after the fact. If you only have an inbox, humans approve work without enough evidence. The better pattern is a review item with a short, readable summary plus access to the receipt trail behind it.

For service businesses, this matters because trust is earned in the ordinary handoff. A lead-routing agent, support agent, billing agent, or marketing agent does not need theatrical autonomy. It needs a clear lane, a visible queue, and proof that the system can be corrected before damage spreads.

## How should you design a simple agent inbox?

Design the first version around one workflow. Do not start by trying to route every agent in the company through one universal command center.

A practical first build looks like this:

1. Pick one recurring workflow with real business value.
2. Define which actions the agent may do automatically.
3. Define which actions must enter the inbox.
4. Give every inbox item a short summary, evidence, risk level, proposed action, and response buttons.
5. Log the final decision.
6. Review the queue weekly and remove noise.

For example, a sales follow-up agent might auto-label leads, draft replies, and enrich CRM records. But the inbox catches replies that mention pricing exceptions, angry customers, custom scope, missing consent, or high-value deals. The human approves the next move from one surface instead of scanning a dozen conversations.

That is also the standard to use when buying or building agent software. Ask where the work waits. Ask what the reviewer sees. Ask whether approvals are scoped. Ask where receipts live. If the answer is “the agent will just ask in chat,” the system may still be useful, but it is not yet a serious operating layer.

## What should businesses avoid?

Avoid turning the agent inbox into a dumping ground. If the queue fills with low-value FYIs, humans will stop reading it. If every approval looks urgent, none of them are.

Avoid approving from thin summaries. A summary is useful, but it can be incomplete, stale, or shaped by the same model that made the mistake. Sensitive items need links back to the source material.

Avoid hiding permissions. Reviewers should not have to guess whether approval sends an email, edits a database, charges a card, deletes a file, or posts publicly.

Avoid treating the inbox as a replacement for policy. The inbox is where policy becomes visible, not where policy is invented on the fly.

The goal is not to make humans click more buttons. The goal is to make human judgment count where it has leverage.

## The practical answer

An agent inbox is the human handoff queue for AI work. It gives long-running agents a place to return with finished work, approval requests, exceptions, and receipts.

For operators, the question is not “Do we have agents?” It is “Where does the work wait, who owns the next decision, and what proof does the reviewer see?”

That is the line between a clever demo and a business system. The agent does the repeatable work. The human keeps judgment, accountability, and the final say where consequences are real.

If your team is building agent workflows, start with the review surface. BBH’s [Agentic Systems](/agentic-systems) work is built around that principle: controlled agents, visible handoffs, and operating receipts before autonomy expands. If the bottleneck is lead flow rather than internal ops, the same discipline applies on the visibility side through [SMB Marketing](/smb-marketing): every response path needs ownership, speed, and a record.
