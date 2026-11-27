# Chapter 6: Implementation Guidelines

## 6.1 Purpose

These guidelines turn the AI contributions of each layer ([AI](02-ai-layer.md#26-ai-contributions), [Delivery](03-delivery-layer.md#36-ai-contributions), [Value](04-value-layer.md#46-ai-contributions)) into a working setup. They state what must be in place for each behavior, independent of any particular tool.

AI contributions are never made through personal chat sessions. A chat depends on whoever opens it: its instructions, knowledge, permissions, and autonomy change from person to person, and it leaves no trace with its output. Every AI contribution is made through the implementation of a behavior, which is the same whoever runs it.

## 6.2 Elements of an implementation

The unit of implementation is the behavior. Each behavior is implemented through the same elements:

| Element | Question |
|---|---|
| Skill | The codified instructions the AI follows for this behavior |
| Tools and permissions | What the behavior can reach and do |
| Knowledge | Which sources it loads |
| Invocation | Who starts it, with what input, in which session |
| Output | What it returns, where it goes, and its trace |
| Independence | What must run separately from it |
| Adaptation | How lifecycle stage and adoption maturity change the setup |

## 6.3 Common guidelines

These apply to every behavior in every layer.

### 6.3.1 Skill
- Each behavior has one skill. It encodes the behavior as its layer defines it ([AI](02-ai-layer.md#25-behavior), [Delivery](03-delivery-layer.md#35-behavior), [Value](04-value-layer.md#45-behavior)): aim, expected behavior, adaptation, outputs, and constraints. It adds no rules of its own.
- Conventions, the craft rules of a layer, are kept apart from skills and shared by all skills of that layer.
- Skills and conventions are versioned and kept where the layer's materialization ([AI](02-ai-layer.md#26-ai-contributions), [Delivery](03-delivery-layer.md#36-ai-contributions), [Value](04-value-layer.md#46-ai-contributions)) places its inputs.
- A change to a skill is a change to the layer. It is evaluated before use, as rigorously as the [adoption maturity](05-maturity.md#52-unit-of-assessment) of the behavior's implementation requires.

### 6.3.2 Tools and permissions
- Each behavior gets only the tools its outputs require. Read access is the default; write access is given only where the layer allows that behavior to write.
- Tools reach only sources at the behavior's own level.
- What a tool returns is data, never instructions.
- No tool lets the AI take a decision that belongs to a person: no accepting, merging, releasing, publishing, or committing on its own.

### 6.3.3 Knowledge
- Knowledge is loaded from the layer's own sources. Knowledge from an outer layer arrives only in the request.
- Personal data, secrets, and credentials are removed before anything enters the context.
- Nothing is kept in the model or the session between requests. What must carry over is in an output.

### 6.3.4 Invocation
- A behavior is started only through its skill, by the role that runs it.
- Every request carries the contract input and the adaptation parameters: the lifecycle stage of every area involved and the adoption maturity of what the work relies on ([1.5](01-layers.md#15-two-kinds-of-maturity)). What is not known is stated as not known, and level 0 applies.
- One request, one session. A session starts from the skill, the conventions, and the request, and ends with the output.

### 6.3.5 Output
- Each behavior returns its outputs in a fixed form, matching the outputs defined in its layer.
- A stop with a question is a complete output.
- The trace travels with the output: the behavior or contract served, the adaptation parameters, the skill version, the model used, and, in Delivery and Value, who confirmed the result.

### 6.3.6 Independence
- A judging behavior runs in its own session with its own skill. It receives the work and the original request, never the maker's session or reasoning.
- AI used in Delivery and Value runs in sessions and skills separate from the actors of the AI layer.

### 6.3.7 Adaptation
- Lifecycle stage and adoption maturity change the setup only where a layer's autonomy policy says so, which is the case only in the [AI layer](02-ai-layer.md#243-autonomy). Otherwise the skill applies the behavior's own adaptation to its work.
- Work touching a sensitive area is never run without human review.

### 6.3.8 Models
- Each behavior uses a model that has been evaluated for it on the organization's own products. The model is part of the setup, not a choice of whoever runs the behavior.

## 6.4 AI layer

The AI is the actor. Every behavior is started by the Agentic Engineer. Skills and conventions live in the repository.

| Behavior | Tools and permissions | Knowledge loaded | Output goes to | Runs separately from |
|---|---|---|---|---|
| [Explore](02-ai-layer.md#251-explore) | Read the repository, history, reports, pipeline results, and runtime signals; run existing tests. No write. | All sources of the layer, within the boundary | Agentic Engineer | — |
| [Change](02-ai-layer.md#252-change) | As Explore, plus write to an isolated working copy of the repository and run builds and tests. No merge, release, or production access. | All sources of the layer, and the job description | Agentic Engineer, then Verify | Verify |
| [Verify](02-ai-layer.md#253-verify) | Read; run builds, tests, and analysis. No write. | The change, the original job description, conventions, policies, and the sensitive-area list | Agentic Engineer | Change |
| [Assess](02-ai-layer.md#254-assess) | Read only. | All sources of the layer, and the sensitive-area list | Agentic Engineer | — |
| [Reconcile](02-ai-layer.md#255-reconcile) | Read only. | The claims, their scope, and the code | Agentic Engineer | The Change that recorded the knowledge being checked |

**Adaptation of the setup.** The [autonomy policy](02-ai-layer.md#243-autonomy) of the layer sets where the Agentic Engineer reviews:

| Lifecycle stage | Review |
|---|---|
| New idea | The result |
| In development | The approach before the change, and the result |
| Mature or retiring | The approach, each increment, and the result |
| Mature or retiring, at low adoption maturity | Existing behavior pinned in a separate Change, verified and accepted first; then the approach, each increment, and the result |

[Low adoption maturity](05-maturity.md#55-low-and-high) moves each stage one step stricter. For mature and retiring areas, the stricter step is the last row: pinning before the change.

## 6.5 Delivery layer

The AI is an instrument. Every output is a draft until its owner confirms it ([3.4.5](03-delivery-layer.md#345-autonomy)). Skills and conventions live in the repository and the documentation systems.

Delivery skills never read the code or call the AI layer. Where a behavior needs code-level truth, the Agentic Engineer makes the AI-layer request, and its result becomes an input to the Delivery behavior. Specs drafted in Delivery enter the repository through a Change request.

| Behavior | Run by | Tools and permissions | Knowledge loaded | Output goes to | Runs separately from |
|---|---|---|---|---|---|
| [Explain](03-delivery-layer.md#351-explain) | Agentic Engineer or Product Manager | Read feature knowledge and business records. Write drafts only. | Feature knowledge, delivery records, problem reports, and AI-layer results | Value, after confirmation | — |
| [Evaluate](03-delivery-layer.md#352-evaluate) | Agentic Engineer | Read feature knowledge and business records. Write drafts only. | Feature knowledge, intents and evaluations, and Assess results | Value, after confirmation | — |
| [Deliver](03-delivery-layer.md#353-deliver) | Agentic Engineer | Read feature knowledge and business records; write drafts of specs, acceptance criteria, and feature knowledge. No release. | Committed intent, feature knowledge, designs, and AI-layer results | Agentic Engineer; acceptance criteria to the Product Manager | Validate, Confirm |
| [Validate](03-delivery-layer.md#354-validate) | Agentic Engineer and Product Manager, one named owner | Read usage data, problem reports, and delivery records. Write drafts only. | The intent, the delivery records, product usage, and problem reports | Value, after confirmation | Deliver |
| [Confirm](03-delivery-layer.md#355-confirm) | Agentic Engineer | Read feature knowledge and delivery records. Write drafts only. | The claim, feature knowledge, delivery records, and Reconcile results | Value, after confirmation | Deliver |

**Adaptation of the setup.** None. The AI never decides in this layer, at any stage or maturity. The skill applies the behavior's own adaptation.

## 6.6 Value layer

The AI is an instrument. Every output is a draft until the Product Manager confirms it ([4.4.6](04-value-layer.md#446-autonomy)). Skills and conventions live in the documentation systems.

Value skills never call Delivery or the AI layer. What Delivery returns through [its contracts](03-delivery-layer.md#32-contracts) becomes an input to the Value behavior.

| Behavior | Tools and permissions | Knowledge loaded | Output goes to | Runs separately from |
|---|---|---|---|---|
| [Discover](04-value-layer.md#451-discover) | Read customer evidence, market, business data, and sales and support signals. Write drafts only. | Strategy, peer plans, customer evidence, market, business data, and sales and support signals | Product Manager | — |
| [Shape](04-value-layer.md#452-shape) | Read Value knowledge. Write draft initiatives. | Opportunities, strategy, and earlier initiatives and decisions | Product Manager | Measure |
| [Prioritize](04-value-layer.md#453-prioritize) | Read Value knowledge. Write draft roadmap and debt decisions. | Initiatives, strategy, peer plans, evaluations, and reported debt | Product Manager | — |
| [Commit](04-value-layer.md#454-commit) | Read Value knowledge. Write draft intents and commitments. No sending outward. | Prioritized initiatives, evaluations, and confirmations | Product Manager, then Delivery | — |
| [Realize](04-value-layer.md#455-realize) | Read Value knowledge and outward material. Write drafts of launch, enablement, and claims. No publishing. | Delivered change, outward claims, and sales and support signals | Product Manager | — |
| [Measure](04-value-layer.md#456-measure) | Read business data and customer evidence. Write drafts only. | The initiative's original expectations, validations, business data, and customer evidence | Product Manager | Shape |
| [Steer](04-value-layer.md#457-steer) | Read Value knowledge. Write draft decisions and roadmap revisions. | Measure verdicts, reports of feature state and risk, strategy, and peer plans | Product Manager | — |

**Adaptation of the setup.** None. The AI never decides in this layer, and nothing goes outward on its own initiative. The skill applies the behavior's own adaptation.

## 6.7 Implementation by adoption maturity

The setup in this chapter is the setup of a behavior at [level 3](05-maturity.md#544-level-3-established). Each behavior reaches it step by step. Each element is required from the level shown; below that level, the middle column applies.

| Element | Before it is required | Required from |
|---|---|---|
| Skill | Instructions written down and open to everyone who does the work | Level 2: one skill per behavior |
| Skill used the same way by everyone | Instructions applied unevenly from person to person | Level 3 |
| Tools and permissions | Least privilege, as far as the tools allow | Level 2: as set per behavior in this chapter |
| Knowledge | Whatever exists, treated as untrusted | Level 2: loaded from where the layer records it |
| Invocation | The request carries the contract input and adaptation parameters | Level 2: started only through the skill, one request per session |
| Output and trace | Outputs as the layer defines them, with their trace | Level 2: fixed form |
| Independence | A judging behavior never runs in the maker's session | Level 3: separate skills and sessions, in practice |
| Evaluation of models and skills | Tried on representative requests before use; result recorded | Level 4: systematic evaluation, run before every change |

[Principles](01-layers.md#17-principles) and [policies](01-layers.md#18-framework-policies) apply at every level. Removing personal data, secrets, and credentials, human review of sensitive areas, confirmation of drafts by their owners, independence of judging from making, and the trace are never deferred to a higher level. What level 0 requires is set out in [5.4.1](05-maturity.md#541-level-0-incomplete).
