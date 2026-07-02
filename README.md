<p align="center">
  <img src="assets/qde-systems-banner.png" alt="QDE-Systems banner" width="100%">
</p>

# QDE-Systems Engine

<p align="center">
  <img alt="Repository: public positioning" src="https://img.shields.io/badge/repository-public%20positioning-2f6fef">
  <img alt="Focus: S&P 500 futures" src="https://img.shields.io/badge/focus-S%26P%20500%20futures-555555">
  <img alt="Execution: deterministic" src="https://img.shields.io/badge/execution-deterministic-0f766e">
  <img alt="Risk: fail-closed" src="https://img.shields.io/badge/risk-fail--closed-d97706">
  <img alt="Audit: evidence first" src="https://img.shields.io/badge/audit-evidence%20first-2563eb">
  <img alt="Agents: AI agent workflow" src="https://img.shields.io/badge/agents-AI%20agent%20workflow-7c3aed">
  <img alt="ML: model integration" src="https://img.shields.io/badge/ML-model%20integration-059669">
  <img alt="Broker: no built-in production adapter" src="https://img.shields.io/badge/broker-no%20built--in%20production%20adapter-8b5cf6">
  <img alt="Platform: macOS UI" src="https://img.shields.io/badge/platform-macOS%20UI-111111">
  <img alt="Python 3.10+" src="https://img.shields.io/badge/python-3.10%2B-3776ab">
  <img alt="Boundary: not financial advice" src="https://img.shields.io/badge/boundary-not%20financial%20advice-b91c1c">
  <img alt="License: public content terms" src="https://img.shields.io/badge/license-public%20content%20terms-6b7280">
</p>

QDE-Systems is deterministic execution infrastructure for people who take
trading seriously, but do not think only in setups and indicators.

I am interested in trading and execution systems where the decision path, risk
control, execution boundary, and audit evidence do not disappear into a black
box. The goal is to make it clearer what the system is doing, why it allows or
blocks a decision, how its behavior can be reviewed later, and how a
trading/execution workflow can be validated with more discipline.

This repository is the public GitHub presentation page for QDE. It is not the
commercial source-code package itself, not private buyer documentation, and not a
signal page. Its purpose is to show, briefly, what kind of system I am thinking
in, and why it may be interesting to someone who wants to treat a trading system
as reviewable, auditable infrastructure instead of a black box.

Public technical reference:
[Stefan-Len/qde-systems-infrastructure](https://github.com/Stefan-Len/qde-systems-infrastructure)

That public reference is not the commercial QDE source package. It exists so the
deterministic execution infrastructure direction can be inspected from the
outside: risk-gated decision path, audit trail, fail-closed boundary, and more
controlled execution thinking.

Short technical prerequisite: the QDE native operator UI is macOS-oriented. A
compatible Mac and Xcode environment is required for the full local UI workflow;
the backend is Python `>=3.10`. The detailed minimum environment is always
defined by the current package/setup documentation.

In short:

> Not a signal. Not managed trading. Not financial advice.
>
> Deterministic execution infrastructure for your own validation, your own
> responsibility, and auditable operation.

## The Core

QDE is not another "buy here, sell there" signal. It is not a course, not a
secret setup, and not a bot from which anyone should expect results without
work.

QDE is execution infrastructure thinking: market data, feature pipeline, model
output, signal gate, risk gate, execution boundary, and audit trail inside a
disciplined process.

From a quant or systematic point of view, the interesting part is not whether a
setup sounds good. The interesting part is what input a decision came from, what
configuration it used, what runtime state it was in, which risk controls it
passed through, and why something happened, or why nothing happened.

More simply: if the system allows something, it should be visible why it allowed
it. If it blocks something, it should be visible what blocked it. If a human or
an AI agent reviews it later, there should be evidence, not just memory or
opinion.

## How The Thinking Works

In QDE, a decision is not one magic point. I think in pipelines.

First comes data and context. On top of that sits the feature and model path.
After that, there may be a signal or `NO_SIGNAL`. A decision can move forward
only after the risk gate. The execution boundary is a separate layer that decides
whether an action may even begin. Along the way, the audit trail records what
happened and why.

This does not make the market predictable. That is not the goal.

The goal is for the system behavior to be less impulse, less post-hoc
explanation, and less black box. The goal is for the system state, decision, and
blocking behavior to be reviewable.

## What This Is Not

This is not financial advice, investment advice, trading advice, a signal
service, or managed trading.

It does not promise profit, win rate, funded-account pass, drawdown-free
operation, broker-ready status, or LIVE-ready trading.

It is not broker/account helpdesk. It does not recommend a broker. It does not
manage your credentials. Broker-backed PAPER or LIVE direction requires
buyer-side integration, buyer-owned credentials, market-data setup, risk review,
audit review, and your own decision.

If you are looking for a fast result promise, this is not it. If you are
interested in how a trading/execution system can be operated and validated in a
more disciplined, deterministic, auditable, and agent-reviewable way, it is worth
reading further.

## AI Agents

An AI agent is not a trading operator in my workflow.

It must not disable risk control, handle broker credentials, bypass audit or
fail-closed boundaries, or decide real-capital use instead of a human.

The agent role is structured review: documentation, code changes, audit
evidence, consistency, broken links, overclaims, drift, uncertainty, and review
packets. In plain terms: it does not trade for you. It helps make clearer what
needs to be checked, fixed, or decided.

## Community

If community access is part of a given launch or package, it is technical
peer-to-peer access. It is not the main product, not a support SLA, not a signal
room, not an investment club, and not a managed account service.

The principle:

> We do not trade together. Everyone operates, validates, and improves their own
> system, evidence-first.

## If You Want To Read Further

This README is only the short entry point. The more detailed public material is
split into numbered sections so it can be read in order.

Start here and read through the pages one by one:

1. [Opening Note](01_OPENING_NOTE.md) - the human entry point before the technical details.
2. [Why QDE Exists](02_WHY_QDE_EXISTS.md) - why QDE was built and what problem it started from.
3. [What QDE Is](03_WHAT_QDE_IS.md) - the short, precise product definition.
4. [What QDE Is Not](04_WHAT_QDE_IS_NOT.md) - boundaries and non-promises.
5. [Why Determinism Matters](05_WHY_DETERMINISM_MATTERS.md) - why deterministic behavior matters.
6. [Why Audit Matters](06_WHY_AUDIT_MATTERS.md) - why evidence, audit, and reviewable decision paths matter.
7. [Why Fail-Closed Matters](07_WHY_FAIL_CLOSED_MATTERS.md) - why uncertain states should block instead of proceeding blindly.
8. [Broker Boundary](08_BROKER_BOUNDARY.md) - where the broker boundary is, and why production broker integration is buyer-side work.
9. [AI Agent Workflow](09_AI_AGENT_WORKFLOW.md) - how I use AI agents as reviewers, not trading operators.
10. [Community](10_COMMUNITY.md) - what the optional technical community layer means, and what it does not mean.
11. [About the Author](11_ABOUT_THE_AUTHOR.md) - who is behind the project, without hype or performance marketing.
12. [Author Note](12_AUTHOR_NOTE.md) - how to read the project and its boundaries.
13. [Access and Contact](13_ACCESS_AND_CONTACT.md) - how to request a next step or access review.
14. [Technical Overview](14_TECHNICAL_OVERVIEW.md) - a high-level technical overview without private source-code details.

If, after that reading path, QDE seems aligned with how you think about trading
systems, the next step is the [Access and Contact](13_ACCESS_AND_CONTACT.md)
page. That page contains the access request path. Submitting the form is not an
order, not checkout, not a license grant, and not a guarantee of acceptance; I
review requests personally and decide whether it makes sense to continue.

See [Notice](NOTICE.md) for attribution, third-party, and public boundary notes.

See [License](LICENSE.md) for the public repository content license.

## Repository Name

This repository is published as `qde-systems-engine`. It is the public
presentation and access/contact repository for QDE-Systems Engine.

Brand and product identity notice: see [NOTICE](NOTICE.md).

## Official Links

- GitHub: [Stefan-Len](https://github.com/Stefan-Len)
- LinkedIn: [Stefan Len](https://www.linkedin.com/in/stefan-len-963813362/)
- X: [@StefanLenQDE](https://x.com/StefanLenQDE)
- Email: stefanlen@qde-systems.com

## Author

Štefan Lengyel, trading as Stefan Len / QDE-Systems
