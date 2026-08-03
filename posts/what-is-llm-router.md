---
title: What Is an LLM Router? Use It With Receipts
slug: what-is-llm-router
description: What is an LLM router? Learn when model routing saves AI costs, when it adds reliability risk, and the receipts to measure before you use one.
date: '2026-08-03'
target_query: what is llm router
keywords:
- llm router
- model routing
- ai model router
- llm cost control
- agent reliability
pillar: Agentic ops & leverage
faq:
- q: What is an LLM router?
  a: An LLM router is a layer that sends each AI request to a chosen model based on cost, speed, complexity, or quality rules.
- q: Do LLM routers always save money?
  a: No. They can save money on repetitive, low-risk tasks, but they can also add testing, debugging, and reliability costs.
- q: When should a business use model routing?
  a: Use model routing only after you have logs, evals, and cost data showing which tasks cheaper models can handle safely.
- q: What should replace confidence scores for routing?
  a: 'Use receipts: test results, source checks, human review outcomes, cost per task, retries, and observed failure rates.'
hero_image: images/what-is-llm-router/hero.webp
hero_image_alt: Chrome railroad switch lever representing model-routing choices
source_draft: 2026-08-03-what-is-llm-router
---
An LLM router is a traffic controller for AI models. Instead of sending every prompt to one model, the router decides which model should answer this request: a cheaper one, a faster one, a stronger one, or a fallback model if the first path fails.

That sounds useful because AI spend is no longer a rounding error for teams that run agents every day. But the useful question is not, “Should we have a router?” The useful question is, “What proof tells us routing is making the system cheaper or better?”

The answer: use an LLM router only when you have receipts. Logs. Task categories. Evaluation results. Cost per successful job. Failure rates. Human review outcomes. Without those, routing is just another invisible layer between your business and the work.

For a small business or service team, this matters because agents are not demos anymore. They answer leads, draft reports, inspect files, move data between tools, and prepare client-facing work. If model routing makes those workflows cheaper while keeping quality steady, it earns a place. If it makes failures harder to understand, it is operational debt with a clever name.

## What is an LLM router?

An LLM router is software that chooses which large language model should handle a request. The choice can be based on rules, classification, benchmarks, cost targets, latency, context length, model availability, or a learned prediction about task difficulty.

A simple router might say: send short classification tasks to a cheap model, send legal-style analysis to a stronger model, and retry failures through a backup provider. A more aggressive router might inspect the prompt, estimate difficulty, fan out to multiple models, then keep the answer from the model that appears to be on track.

The promise is sensible. Not every AI task needs the most expensive model. A lead-intake agent that extracts name, email, service type, and urgency from a form submission should not always require a frontier model. A research agent summarizing conflicting primary sources probably should not default to the cheapest model either.

The router exists to match the tool to the job.

The catch is that the match is not free. Once you add a routing layer, you also add a new thing to test, observe, tune, and explain when the output changes.

## Why are teams using LLM routers?

Teams use LLM routers for three reasons: cost control, reliability, and provider flexibility.

Cost is the obvious one. Tokenless describes itself as a router and drop-in replacement for OpenAI and Anthropic-compatible API calls, with the claim that many requests do not need a frontier model and can be routed to reduce the bill. The commercial pull is clear: if a cheaper model can do the task without lowering quality, the savings compound.

Reliability is the second reason. A router can retry through a backup model if one provider is down or rate-limited. It can send structured extraction to the model that handles JSON reliably and send long-form synthesis somewhere else. In a real agent system, reliability is not just uptime. It is whether the job finished in a form the business can use.

Provider flexibility is the third reason. Teams do not want every workflow tied to one vendor’s pricing, limits, or outages. A router can become a switching layer between models.

That sounds like control. Sometimes it is. But control requires measurement. If the router hides model choice, changes behavior across similar tasks, or makes debugging harder, the business has not gained control. It has outsourced the decision to a black box.

## When does model routing actually save money?

Model routing saves money when the work is frequent, measurable, and safe to split by difficulty.

A good candidate is a task with thousands of similar runs: classify inbound leads, clean CRM fields, draft first-pass summaries, tag support tickets, rewrite internal notes, or extract values from documents. You can sample the work, test cheaper models, measure the failure rate, and decide where a lower-cost path is safe.

A weak candidate is a small, high-variance workflow with messy judgment calls. If every request is different and the cost of a bad answer is high, routing may cost more than it saves. You will spend the savings on evals, prompt variants, incident review, and human cleanup.

Manifest’s post on deprecating its LLM router is useful because it argues from experience, not fashion. Manifest says it launched a router in March, deprecated it in June, and planned to shut it down on September 1. Their router classified requests into complexity tiers. After months of usage, they argued that cache behavior, consistency, and the extra uncertainty made routing less attractive for their use case.

That is the honest lesson. A router can be the right answer in one system and the wrong answer in another.

For BBH’s audience, the rule is simple: route only where the receipt survives review. If the monthly report says routing saved 38 percent but the team lost trust in the agent’s outputs, the system did not get better. It just moved cost from the API bill into human attention.

## What can go wrong with an LLM router?

Three things usually go wrong: inconsistent behavior, hidden failure modes, and false savings.

Inconsistent behavior happens when similar tasks go to different models and return slightly different standards. One model follows the formatting contract. Another invents a field. One writes short. Another writes around the answer. The human experiences this as “the agent is moody,” even though the real issue is an unstable tool path.

Hidden failure modes appear when the router’s decision is not logged clearly. If a client report is wrong, you need to know which model handled the task, what prompt it saw, what tools it called, whether it retried, and what evidence it used. Without that, the system cannot be improved. It can only be blamed.

False savings happen when the API line goes down but operational load goes up. Manifest’s critique points to this directly: the extra layer can make evals, prompts, observability, and maintenance harder. That is not a reason to reject routing forever. It is a reason to count the whole cost.

The sober view is this: model routing is not a feature. It is an operating decision. Operating decisions need logs and thresholds.

## How should a small business decide whether to use one?

Start with the workflow, not the router.

List the jobs your AI system runs every week. For each job, write down the business consequence of a bad output. Then sort the jobs into three buckets.

First: low-risk, high-volume tasks. These are routing candidates. Examples include tagging, deduping, reformatting, first-pass extraction, and internal summaries that a human or downstream check can catch.

Second: medium-risk tasks. These can use routing only with guardrails. Examples include client email drafts, proposal first drafts, lead qualification notes, and research briefs. The router can help, but the system needs review states, source links, and rollback paths.

Third: high-risk tasks. These should not be routed casually. Examples include legal claims, financial advice, security changes, medical guidance, or irreversible customer actions. If routing is used here, it needs formal evaluation and explicit approval gates.

For most service businesses, the first win is not buying a router. The first win is building a clear task ledger: what the agent did, what it cost, what model ran, what failed, and what the human approved. Once that exists, routing decisions become obvious.

This is the same pattern behind good agent operations generally. You do not improve what you cannot see.

## What should you measure before routing AI tasks?

Measure cost per successful job, not cost per token.

A cheap model that fails twice and needs human repair is expensive. A stronger model that finishes cleanly may be cheaper in practice. The unit that matters is not the model call. It is the completed business task.

Track at least seven fields:

- Task type
- Model used
- Input size or rough complexity
- Output accepted, edited, or rejected
- Retry count
- Human review time
- Total cost per completed task

Add source checks where the task depends on facts. Add evaluation cases where the format matters. Add escalation rules where a bad output can harm a customer relationship.

This is where “AI confidence scores” are a trap. A model saying it is 86 percent confident does not prove the work is good. Confidence must come from outside the model: tests, sources, checks, user acceptance, and observed history.

The router should respond to evidence. It should not replace evidence.

## The BBH operating rule: route with receipts or do not route

If you run AI inside a business, you are not trying to win a model-routing debate. You are trying to make work happen reliably.

So use the boring rule: route with receipts or do not route.

A router earns its place when it can answer these questions:

- Which task category is being routed?
- Why is this model safe for that task?
- What failure rate is acceptable?
- What happens when the cheap path fails?
- How much money is saved per successful job?
- Can a human inspect the decision after the fact?

If those answers are missing, keep the system simpler. Pick one reliable model for the workflow, log the work, build your evaluation set, and revisit routing after the evidence exists.

AI should make the operator more capable, not more dependent on hidden machinery. The goal is not a clever model stack. The goal is a business system that keeps working when the novelty wears off.

For many teams, an LLM router will eventually be useful. But the first router is not software. It is judgment: knowing which work is safe to cheapen, which work deserves the strongest model, and which work should still wait for human approval.

That judgment is the part worth building first.
