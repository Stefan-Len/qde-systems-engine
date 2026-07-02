# Why Fail-Closed Matters

In an execution system, one of the most dangerous sentences is: "it is probably
fine."

In trading, uncertainty is not a neutral state. If you do not know for sure what
happened, what is open, what state the system is in, what the broker side
accepted, or which risk condition was violated, the disciplined reaction is not
to continue as if everything were clear.

The disciplined reaction is that the system blocks, stops, requests reconcile,
requests review, or does not allow continuation until an owner decision.

That is what fail-closed thinking means to me.

## What Does Fail-Closed Mean?

By fail-closed, I do not mean the system never makes mistakes.

It means that in an uncertain, damaged, incomplete, or unproven state, the
system does not assume it is safe to continue. It does not try to hide the
problem. It does not silently switch into "it will probably be fine" mode. It
does not allow continuation just because continuation would be more convenient.

If there is not enough data, stop. If the state is not clear, request reconcile.
If the risk gate result is not proven, block. If the broker-side state does not
match the internal state, do not start another execution attempt. If audit is
incomplete, do not pretend the decision is reviewable.

This is not slowness. This is control.

## Why Does This Matter In Trading?

In trading, errors often do not begin with a large, spectacular collapse.

They often begin with small uncertainties: an unclear position state, a
misunderstood fill, a missing market-data check, a manually touched config, a
silenced warning, or a "just this once, let it continue" decision.

If the system assumes these are safe, the error can easily amplify. Not because
the market is unpredictable, but because the system is not telling the truth
about its own state.

With fail-closed behavior, the system says no until there is enough evidence.
That can be inconvenient. It can stop a process. It can request review. It can
request reconcile. It can require a human decision.

But that is better than a system that continues confidently even in an uncertain
state.

## What Should You Do Then?

In a fail-closed state, the task is not to quickly route around the block.

The first question is not how to allow it through anyway. The first question is
why it stopped.

The correct order is:

- stop;
- inspect the audit evidence;
- check the input, config, and runtime state;
- reconcile if broker or position state is involved;
- separate code-proven fact, assumption, and uncertainty;
- continue only after human review or an owner decision.

This order matters not because every block is a severe defect. It matters
because uncertainty must not be treated as normal operation.

## Why Does This Matter With An AI Agent?

Working with an AI agent would be especially dangerous without a fail-closed
boundary.

An agent can easily suggest how to "resolve" an obstacle. But if the obstacle is
actually a risk, audit, broker-state, or execution-boundary problem, it should
not be bypassed. It should be understood.

So the agent's role in a fail-closed state is not to turn the system back on. It
is not to disable control. It is not to allow a real-capital direction forward
from its own decision.

The agent's role is to help clarify:

- what stopped;
- what evidence exists;
- what is proven fact;
- what is assumption;
- which boundary may have been violated;
- whether an owner decision, broker-side review, or further validation is
  needed.

## What Does It Not Mean?

Fail-closed does not guarantee there will be no loss, technical error, slippage,
bad model output, or broker-side problem.

It is not a compliance certificate. It does not mean broker-ready or LIVE-ready
status. It does not replace testing, validation, audit review, broker-side
checks, or your own responsibility.

It means that in uncertainty, the system does not leave the door open. It stops
the process until there is enough evidence to continue.

The next section clarifies where the broker boundary is, and why
broker-connected work remains buyer-side responsibility.
