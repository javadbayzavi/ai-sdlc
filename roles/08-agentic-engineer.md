# Chapter 8: Agentic Engineer

## 8.1 Purpose

The Agentic Engineer turns intent into product change delivered to users, with the AI as the actor. The product is changed by the AI, and by a person only where the AI cannot ([2.4.5](../02-ai-layer.md#245-delegation)); the Agentic Engineer frames the work, decides on what the AI returns, and is accountable for the change reaching users and running healthy.

## 8.2 Where the role works

| Layer | Part |
|---|---|
| [Value](../04-value-layer.md) | No role |
| [Delivery](../03-delivery-layer.md) | Turns intent into technical delivery |
| [AI](../02-ai-layer.md) | The only role that brings work into the layer |

## 8.3 Responsibilities

### 8.3.1 In the Delivery layer
As defined in [3.7.1](../03-delivery-layer.md#371-agentic-engineer):
- **Specs and acceptance criteria.** Every committed intent becomes specs and acceptance criteria that make it checkable. Criteria that do not capture the intent are a failure of the translation.
- **Delivery to users.** The Agentic Engineer owns the release until it is in users' hands and healthy, including restoring a failed release.
- **Decisions on results.** Every result from the AI layer is accepted or sent back by the Agentic Engineer.
- **Technical half of feature knowledge.** Specs and the mapping from business terms to technical parts.
- **Debt.** Debt introduced by a delivery is reported, never hidden.

### 8.3.2 In the AI layer
As defined in [2.7.1](../02-ai-layer.md#271-agentic-engineer):
- **Request quality.** Every request has a clear intent, a boundary, acceptance criteria where a change is involved, and the Delivery knowledge the AI needs to understand why.
- **Lifecycle stage and adoption maturity.** The Agentic Engineer states the lifecycle stage of every area a request involves and the adoption maturity of what the work relies on, and makes the final decision when the layer argues against them.
- **Stops.** When the layer stops with a question, the Agentic Engineer owns the answer.
- **Feedback.** Where the layer falls short, the Agentic Engineer reports it to the AI Enablement Lead so the layer can improve.

## 8.4 Behaviors run

- **AI:** all five behaviors: [Explore](../02-ai-layer.md#251-explore), [Change](../02-ai-layer.md#252-change), [Verify](../02-ai-layer.md#253-verify), [Assess](../02-ai-layer.md#254-assess), and [Reconcile](../02-ai-layer.md#255-reconcile). Here the AI is the actor.
- **Delivery:** [Explain](../03-delivery-layer.md#351-explain), shared with the Product Manager; [Evaluate](../03-delivery-layer.md#352-evaluate); [Deliver](../03-delivery-layer.md#353-deliver); [Validate](../03-delivery-layer.md#354-validate), together with the Product Manager under one named owner; and [Confirm](../03-delivery-layer.md#355-confirm). Here the AI is an instrument, and its drafts are confirmed by their owner.

Where a Delivery behavior needs code-level truth, the Agentic Engineer makes the AI-layer request. How each behavior is set up is defined in [6.4](../06-implementation-guidelines.md#64-ai-layer) and [6.5](../06-implementation-guidelines.md#65-delivery-layer).

## 8.5 Decisions

### 8.5.1 Decides
- Whether each result from the AI layer is accepted or sent back.
- The lifecycle stage and adoption maturity stated in each AI-layer request, including when the layer argues against them.
- The answers to the AI layer's stops.
- Whether a change the AI cannot make is made by a person, under the [AI layer's delegation policy](../02-ai-layer.md#245-delegation).
- Specs, acceptance criteria, and how the work is broken into pieces. The Product Manager confirms that the acceptance criteria capture the intent.
- When a release goes to users, and when a failed release is restored.
- Reviews at the points the [AI layer's autonomy policy](../02-ai-layer.md#243-autonomy) sets.

### 8.5.2 Does not decide
- What is worth building, what is committed or promised, changes to the lifecycle stage of features, and decisions on debt. These belong to the Product Manager.
- Whether their own work is correct. Verification is independent of whoever made the change.
- How the layers, skills, and models are defined. This belongs to the AI Enablement Lead.

## 8.6 Competencies

- **Precise writing:** job descriptions, specs, acceptance criteria, and what must not change. This replaces most hands-on coding.
- **Decomposition:** breaking work into pieces, each with its boundary and lifecycle stage, that can be verified.
- **Judgment on evidence:** reading proof of change and verdicts critically, and sending back what is not proven.
- **Knowing the product:** the lifecycle stage of each area, the adoption maturity of what the work relies on, and what must be preserved.
- **Release and production care:** reversible releases, watching health, restoring failures.
- **Honest reporting:** debt, risk, and uncertainty stated openly.
