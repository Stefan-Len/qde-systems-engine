# Technical Overview

This short technical overview is meant to show the system logic QDE is built
around, without publicly exposing the private details of the commercial
source-code package.

This is not source-code delivery.

Not full architecture documentation.

Not a private implementation guide.

Not a broker integration manual.

And not performance proof.

This is a public, high-level technical overview: enough to understand the
direction, but not a replacement for the later package scope, license,
applicable purchase terms, delivery manifest, or private technical
documentation.

## In Short

QDE is a deterministic execution engine for the E-mini S&P 500 futures market.

This public technical scope is intentionally framed around one instrument
direction. Not because other markets are technically uninteresting, but because
QDE's value is in the disciplined execution pipeline, risk boundary, auditable
decision path, and validation work. These are cleaner to present, inspect, and
bound first around one concrete instrument focus.

The system's core is not one "secret setup", but a more controlled execution
pipeline:

```text
market data
  -> normalization
  -> feature / model path
  -> signal or NO_SIGNAL
  -> risk gate
  -> execution boundary
  -> audit / diagnostics / operator UI
```

That order matters.

Not because it makes the market predictable. It matters because the decision
path is less likely to disappear into a black box.

If the system returns `NO_SIGNAL` instead of a signal, the reason should be
reviewable. If the risk gate blocks, it should be visible why it blocked. If a
runtime state is uncertain, the system should not assume everything is fine.

## Main Layers

Several layers are separated in the way QDE thinks.

**Market data and normalization**

The first step is controlled data preparation. The goal is not to force a
decision from any feed in any state, but for the pipeline to know what input it
is working from.

**Feature / model path**

The system works with ML/model integration, but model output by itself is not a
trading instruction. The model is only one part of the decision path. After that
comes the signal gate, then the risk gate.

**Signal gate**

The signal gate separates whether there is even a state the system may allow
forward. `NO_SIGNAL` is not an error. Often, the correct output is exactly that
the system does nothing.

**Risk gate**

The risk gate is not decoration. It is one of the most important boundaries. If
the risk side does not allow something, the execution direction must not proceed
as if only a UI warning had happened.

**Execution boundary**

The execution boundary is a separate layer. This is where it is decided whether
an operation may even begin. It is not the same as the strategy or model output.
In the system's mindset, execution must not be a blind consequence.

**Audit and diagnostics**

Audit is not log noise. Audit is the layer from which a human or AI agent can
later review what happened, in what context, and through which decision path.

**Operator UI**

The QDE native operator UI is macOS-oriented. A compatible Mac and Xcode
environment is required for the full local UI workflow; the backend is based on
Python `>=3.10`. The purpose of the UI is not to hide the system, but to make
runtime, risk, audit, and diagnostics state more visible at the operator level.

## Runtime Modes At A High Level

The runtime modes in QDE should not be mixed together.

**DEMO**

Brokerless local orientation and smoke/evaluation path. Not LIVE trading.

**LEARNING**

Controlled learning / validation direction with a brokerless mindset. Not a
profit promise and not deployable sizing proof.

**BACKTEST**

Offline / replay-style investigation. Useful for regression and setup-quality
thinking, but not a future performance guarantee.

**PAPER**

The package has a paper/simulation direction with broker-shaped thinking. This
does not automatically mean a broker-backed PAPER setup is ready or validated in
a buyer environment.

**LIVE**

LIVE mode exists as a runtime direction, but production LIVE use requires a
buyer-side broker adapter, buyer-owned credentials, market-data setup,
validation, risk review, audit review, and your own decision. This public
overview does not claim LIVE-ready or broker-ready status.

## Broker Boundary

QDE is not a broker recommendation and not broker account helpdesk.

The commercial package contains a broker-adapter-ready architecture direction,
but it does not include a built-in production broker adapter. The production
adapter is buyer-side work.

For broker-backed PAPER or LIVE direction, the buyer is responsible for:

- broker selection;
- broker account and permissions;
- market-data setup;
- handling credentials outside QDE source and agent prompts;
- implementing or providing the adapter;
- validating order submit / cancel / flatten / reconcile;
- checking broker API terms, exchange rules, and account rules.

You do not need to be scared of this, but it must not be treated as automatic
either. The correct order is read-only broker slice, evidence, review,
reconcile, understanding fail-closed behavior, and only later an order-capable
direction.

## AI Agent Workflow

The AI agent around QDE is not a trading operator.

It does not handle credentials. It does not decide real capital. It must not call
a connection test broker-ready or LIVE-ready. It must not disable risk, audit,
fail-closed behavior, or the broker boundary so something can "work".

The useful agent role is technical review:

- documentation consistency;
- source/diff reading;
- audit evidence interpretation;
- broken-reference search;
- overclaim filtering;
- broker-boundary preflight;
- review packet and uncertainty clarification.

That is why the QDE agent workflow is evidence-first. Agent output by itself is
not evidence. It needs source, diff, audit, config, test, run id, session id, or
a masked evidence summary behind it.

## What Does This Page Not Reveal?

This public overview intentionally does not reveal:

- source-code details;
- private package manifest;
- private implementation notes;
- model artifact details;
- credential, account, or runtime secret information;
- buyer-private delivery documentation;
- a detailed list of exact internal thresholds / parameters;
- broker adapter implementation detail that would count as private integration
  work.

This is not a gap. This is a boundary.

The job of the public page is to show the thinking and the architecture
direction. The commercial package, if delivered under an accepted order, is
understood according to its separate package scope, license, disclaimer,
applicable purchase terms, delivery manifest, and private technical
documentation.

## What Should You Understand From This?

QDE is not interesting because it says: "here is the trade."

It is interesting because it tries to make the decision path more controlled.

It starts from data.

Model and signal are only one part.

There is no execution without the risk gate.

In an uncertain state, the system must not pretend everything is fine.

Without audit, there is no good review.

You can work without an AI agent, but if you use an agent, it must be treated as
an evidence-first reviewer, not as an operator replacement.

That is the point of this technical overview:

> not a black box, but a reviewable execution infrastructure direction.

For the next step, see the access/contact page: form, personal review, pre-order
technical summary, terms, acceptance, payment, and only then any delivery.
