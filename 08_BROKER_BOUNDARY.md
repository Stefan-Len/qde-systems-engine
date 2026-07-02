# Broker Boundary

The broker boundary is one of the most important boundaries around QDE.

It is important to say this clearly because, with an execution engine, it is
very easy to misunderstand what it means for a system to have an execution
layer, a PAPER direction, or a possible LIVE runtime direction.

QDE is not a broker recommendation. It is not broker account helpdesk. It does
not manage your credentials. It does not connect your broker for you. It does
not give a broker-ready or LIVE-ready guarantee.

For production broker integration, broker-connected work is buyer-side
responsibility.

## Why Is There No Built-In Production Broker Adapter?

Because this is not a small technical detail.

A production broker adapter is not just an API call that sends an order. On the
broker side, there is credential handling, session state, market-data setup,
permissions, margin, position state, fill/reject behavior, reconnect, rate
limits, partial fills, order lifecycle, reconcile, and the real account
environment.

These cannot be handled responsibly by claiming that "this is ready for every
broker."

That is why QDE does not try to blur this boundary. The core system is built
around deterministic execution logic, risk gate, audit trail, UI, model/ML
integration, and execution boundary. The production broker adapter and concrete
broker-side validation are separate work, in your own environment, with your
own credentials and your own decision.

This is not weakness. This is boundary-setting.

## What Does QDE Provide Around Broker Work?

QDE does not say broker integration is unimportant. Exactly the opposite: it
separates it as its own boundary because it is too important to be handled with
one marketing sentence.

The system's way of thinking helps make the broker-connected direction not one
large, vague jump, but a series of reviewable steps:

- first, brokerless DEMO / LEARNING understanding;
- audit and risk boundary understanding;
- read-only broker adapter slice;
- connection / account-state / position-state checks;
- reconcile logic;
- PAPER-direction validation;
- independent review;
- only after that, any real-capital decision.

This does not mean broker implementation is automatic or easy. It means you do
not have to go into it blindly.

## You Do Not Need To Be Scared Of This

Important: the fact that production broker integration is buyer-side work does
not mean you have to approach it alone and without structure.

Around QDE, agent review, audit evidence, the fail-closed boundary, and
step-by-step first-slice thinking exist precisely so this kind of work does not
have to be treated as chaos.

With disciplined work, in small steps, starting first from a read-only
direction, this can be built. You do not need to send live orders on day one.
You do not need to start with production LIVE. First, you need to prove that the
connection, state, reconcile, audit, and risk boundary are understandable and
reviewable.

That is the difference between "connect it and see what happens" and
disciplined broker adapter implementation.

## What Must Not Be Done On The Broker Side?

Broker integration must not be done through shortcuts.

You must not put credentials, account numbers, tokens, or 2FA material into
source code, agent prompts, public issues, review notes, or audit exports.

You must not disable a risk gate so a broker flow can pass. You must not bypass
a fail-closed block because it is inconvenient. You must not assume internal
state and broker state match without reconcile. You must not call a successful
connection test broker-ready or LIVE-ready.

And especially, you must not delegate a real-capital decision to an AI agent.

## Broker-Neutral, But Not Broker-Indifferent

QDE is not a broker recommendation. It does not tell you which broker to choose,
and it does not promise production-ready operation with any given broker.

This does not mean the broker side is secondary. The broker side is critical.
That is exactly why it remains a separate boundary: it must be aligned with the
buyer's own broker, own account, own market-data subscription, own validation,
and own responsibility.

## What Does It Not Mean?

This broker boundary does not mean QDE is broker-ready. It does not mean it is
LIVE-ready. It does not mean it provides broker account support. It does not
mean it handles or stores broker credentials for you. It does not mean it
guarantees compatibility with any broker.

It means the production broker connection must not be confused with the value of
the core execution engine.

The core value is that the decision path, risk, audit, and execution boundary
are disciplined. Broker-connected work can be built on top of that, with
buyer-side validation.

The next section shows how AI agents fit into this: as reviewers, not as trading
operators.
