---
name: interview-first
description: Routes to the right pre-work interview (a requirements interview for a vague ask, or a plan grilling for a concrete plan) and runs it, so the user's perspective is clear before any AI-assisted work begins.
---

# Interview First

Most AI work goes wrong before the first draft exists. A thin prompt with no real point behind it gets structure and confidence built around nothing. Interview First is the step taken before engaging any serious project with AI: an interview that gets the user's perspective clear before the work goes forward. It routes between two modes, because the right interview depends on what the user brought: interview-me by Addy Osmani for extracting intent, and grill-me by Matt Pocock for stress-testing a plan.

## When to Use This Skill

- Starting a serious piece of work with an AI assistant and the ask is not yet precise
- A request is missing who it is for, why it matters, what success looks like, or the binding constraint
- A concrete plan, decision, or design exists and should be stress-tested before work starts
- The user says "interview me", "grill me", "help me think through this", or "are we sure?"

## What This Skill Does

1. **Routes by shape**: Decides whether what the user brought is a vague ask, a concrete plan, or a raw idea, and picks the interview that fits without announcing the choice
2. **Runs a requirements interview**: For a vague ask, one question at a time, each with the agent's best guess and reasoning attached, until the intent can be restated in the user's own words at about 95 percent confidence
3. **Runs a plan grilling**: For a concrete plan, maps the decision as a tree and asks the whole frontier of open questions per round, each with a recommended answer, recomputing the frontier until nothing is left silently assumed
4. **Switches modes as the shape changes**: An interview that produces a plan earns a grilling round; a grilling that exposes missing intent goes back to the interview
5. **Ends at shared understanding**: Stops when the agent can predict the user's reaction to the next three questions, states the confirmed intent or conclusions plainly, and waits for an explicit yes before any work starts

## How to Use

### Basic Usage

```
Interview me before we start. I want to write a launch post for a new tool, but I have not figured out the angle yet.
```

### Advanced Usage

```
Grill me on this plan before we build anything: [paste the plan]. Work the decision tree round by round, attach your recommended answer to every question, and do not let anything stay silently assumed.
```

## Example

**User**: "I want to add a dashboard to our analytics tool."

**Output**:

```
Before we talk about the dashboard itself, one question at a time. My best guess is that the dashboard is not the goal; the goal is that someone specific stops asking your team for a weekly numbers pull. First question: who is the person who would open this every week, and what decision do they make with it? My guess: your ops lead, deciding where to send the field team. Correct me where that is wrong.
```

The interview continues until the intent (outcome, who benefits, why now, what success looks like, the binding constraint, what is out of scope) can be restated and confirmed.

**Inspired by:** Matt Pocock's grill-me and grilling method (https://github.com/mattpocock/skills) and Addy Osmani's interview-me (https://github.com/addyosmani/agent-skills). This skill is a routing layer over those two; install them from their repos for full strength. Canonical home of this skill, with the routing rules in full: https://github.com/nateprich/ai-workbench/tree/main/interview

## Tips

- Give the interviewing agent your own context to work from first: your email, your messages, your files. Questions about your material produce clarity; generic questions produce generic answers.
- React to the agent's guesses honestly. Correcting a concrete proposal is faster and sharper than answering in a vacuum, and the correction itself is information.
- Do not let the interview end in a summary you have not confirmed. Only an explicit yes counts.

## Common Use Cases

- Prepping a work item or analysis request so the AI builds on your actual perspective instead of a thin prompt
- Stress-testing a project plan, a design, or a career or purchase decision before committing
- Starting a long writing project by getting your own angle clear before the first draft
