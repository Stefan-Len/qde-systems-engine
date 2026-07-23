# AI Agent Workflow

For me, AI agents are not trading operators.

They are not around QDE so they can trade for you, connect to a broker, disable
risk control, or make real-capital decisions. The agent is not a financial
advisor, not a signal provider, not a compliance approver, and not a broker
operator.

The AI agent's role here is much more specific:

> a structured reviewer around source code, documentation, audit evidence,
> config, change discipline, and broker-boundary work.

That is a big difference.

## Why Do Agents Have A Place In QDE?

QDE is a source-code-based system. That means many things can be reviewed later:
code, diff, config, documentation, audit trail, helper script, test, gate,
runtime state, and review note.

A well-directed AI agent can help with this. Not by magically telling us what
will happen in the market, but by helping us review what happened inside the
system with more discipline.

An agent can ask:

- which file proves this;
- what is a code-proven fact;
- what is only an assumption;
- where there is uncertainty;
- which boundary the change touches;
- whether a test, audit review, or independent review is needed;
- what remains open before commit + merge.

That is why the agent is not an authority for me. The agent is a review tool
that needs discipline.

## Evidence-First, Not Agent Opinion

In QDE, the agent's output is not evidence by itself.

Evidence is something reviewable: source file, diff, git status, audit record,
config, test output, script output, documentation reference, run id, session id,
or a concrete masked evidence summary.

If an agent says "this is good", that is not enough.

The better questions are:

- where is this visible in the code;
- which diff shows it;
- what audit or log supports it;
- which test ran;
- what did we not check;
- where uncertainty remains.

That is why the QDE workflow is not about collecting agent opinions. It is about
collecting repo-grounded evidence.

## Primary Agent And Review Agent

For more serious work, two roles are separated.

The primary agent works: reads, plans, edits, runs tests, prepares the diff, and
writes the review packet.

The independent review agent does not edit. It checks the change in read-only
mode: files, diff, references, boundaries, and then gives a verdict.

This may look slower, but that is the point. In QDE, the goal is not for one
agent to close something quickly. The goal is for the work to be traceable, and
for the review not to be trapped inside the same reasoning that produced the
change.

A good review packet includes:

- what the task was;
- which files changed;
- what changed;
- which boundary was touched;
- what verification ran;
- what was not checked;
- what the known uncertainty is;
- whether it is commit + merge ready.

That is why I often provide a copy-paste review message. Not as a formality, but
so the review agent does not work from a vague summary.

## What Can An Agent Do Well?

An agent can be useful for:

- checking documentation consistency;
- finding broken links or stale references;
- reviewing overclaim, AI-smell, or buyer-facing wording;
- reading code paths;
- finding root cause;
- triaging test failures;
- comparing config and runtime state;
- interpreting audit evidence;
- broker-boundary preflight;
- reviewing a read-only adapter slice;
- checking release/package readiness checklists.

In these kinds of work, the agent is useful when it works from sources, not from
memory.

## What Must It Not Do?

The agent must not handle secrets, API keys, broker credentials, 2FA data,
account passwords, or raw account data.

It must not disable a risk gate, audit trail, fail-closed behavior, idempotency,
reconcile, or broker boundary so something can "work".

It must not start a broker-connected, order-capable, broker-backed PAPER, or
LIVE path without explicit owner decision, documented validation, and
independent review.

It must not decide real-capital use.

It must not call a successful connection test broker-ready or LIVE-ready.

It must not rewrite buyer-facing documentation so plans, assumptions, or future
work are presented as finished facts.

And it must not commit, merge, or publish without owner approval.

## Broker Work With An Agent

For broker adapter work, the agent can be especially useful, but only inside a
strict frame.

The starting prompt should not be "connect the broker."

A good first step is:

- read the broker boundary;
- inspect the adapter port and contract;
- identify the first read-only slice;
- reason without credentials;
- first look at connection / account equity / positions / reconcile;
- order-capable operations may come only later, with separate validation.

This is one of the most important patterns in the QDE agent workflow: first
read-only evidence, then review, then decision. Not the other way around.

## Owner Decision

The agent can help make things clearer, but it does not replace the owner
decision.

The owner decides:

- whether file edits may proceed;
- whether a branch or worktree is needed;
- whether independent review is needed;
- whether a test or gate may be run;
- whether commit + merge may proceed;
- whether a broker-connected or real-capital direction may even be considered.

This is not bureaucracy. This is a control point.

If an agent were to close work from its own decision when that work touches
risk, audit, fail-closed behavior, broker boundary, license/policy text, or a
buyer-facing claim, that would not be a good agent workflow.

## What Is The Point?

The AI agent is valuable around QDE when it helps us work with more discipline.

It does not think for you. It does not take responsibility for you. It does not
validate the broker for you. It does not decide the market for you.

It helps make source-code, documentation, audit, config, test, and review work
less opaque, less memory-based, and more traceable.

In short:

> We do not want an AI trading operator.
>
> We want an evidence-first technical reviewer.

The next section moves from the agent workflow to the author and project
boundary.
