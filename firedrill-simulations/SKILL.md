---
name: firedrill-simulations
description: Use Firedrill to explore or test an AI agent or application through simulations, controlled dependencies, and retained reports. Supports observation, demonstrations, behavioral evaluation and CI.
---

# Firedrill simulations

Inspect the actual application's task entry point, completion signal and reset
boundary. Use an existing command, HTTP endpoint or supported callable rather
than migrating its framework. The application under simulation is distinct from
you, the coding agent operating Firedrill.

Use the connected Firedrill remote MCP and the host's native OAuth sign-in.
Human consent authorizes the intended organization; do not request pasted tokens,
read environment secrets, or reuse credentials from another organization. Inspect
current project/environment context and discover the available tools and schemas.

Match the simulation to the user's question. Observation needs no grading;
evaluation may use semantic scoring for valid output variation and exact checks
for hard constraints. Propose realistic situations grounded in the application,
not thousands of renamed copies of the same input. Declare the proposed target,
cases, repetitions and dependency/reset boundaries before execution.

Remote MCP prepares and inspects work; it does not launch the user's repository.
Use an authorized customer-owned CLI/SDK runner for real target execution. If no
runner is available, provide `npx firedrill-run init` as the CLI setup command
and explain the handoff. Do not install packages, change host trust or start
target work merely because the plugin was installed. Use existing client help
and [official documentation](https://docs.firedrill.run/) for the current recipe
and invocation contract instead of inventing fields or commands.

Select only needed synthetic dependencies and explicitly authorized data.
Keep live vendor credentials and external side effects out of a simulation unless
the user deliberately authorizes them. Resetting Firedrill Tools does not reset
the application's database, process memory, external services or LLM randomness.
Never silently fall back to live production services.

Reconcile an uncertain operation using its retained recovery handle before
retrying. Queued work, setup success and manual Tool probes are not proof that
the target ran. Keep execution, observed outcome, assessment and optional CI gate
distinct; an evaluator error is not an agent failure and a score is not a
calibrated probability. Never fabricate screenshots, Tool calls, scores or runs.

Finish with the retained report link, important observations, evidence gaps and
next action. For repetitions or comparisons, show distributions and meaningful
failure/interruption/unknown counts, not a cherry-picked score. Preserve the
recipe and recovery handles for reuse or CI within the existing repository.

## Setup and example

Connect `https://mcp.firedrill.run/mcp` using the host's native remote-MCP
configuration and browser authorization. See the [coding-agent setup
guide](https://firedrill.run/agents). The service is free and closed source;
the customer's model and runner costs are separate. Installing this skill does
not install a server or grant account access.

For example: "Simulate my onboarding adviser with a missing company profile
and a restricted budget. Keep the existing application entry point, explain
the proposed cases before running, and link the retained report."

Discover the application's actual recipe and schemas before acting. The useful
result is its observed output and retained report, including any failure or
missing evidence, not a predetermined passing answer. The [public example
directory](https://docs.firedrill.run/guides/examples) contains runnable agents
with their prerequisites and observation-only boundaries.

Source: [Firedrill's thin connector skill](https://github.com/firedrill-tools/firedrill-plugin/tree/main/claude/skills/firedrill-simulations).
This skill is MIT licensed; see [LICENSE](./LICENSE). That licence does not
apply to the Firedrill service, CLI, SDKs or other source repositories.
