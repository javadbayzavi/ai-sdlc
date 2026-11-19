# Chapter 9: AI Enablement Lead

## 9.1 Purpose

The AI Enablement Lead keeps the framework fit for the products: the definition of every layer and its implementation. They own the framework and do not use it for product work. The AI Enablement Lead is measured by the outcomes of the layers, not by what they build directly.

## 9.2 Where the role works

| Layer | Part |
|---|---|
| [Value](../04-value-layer.md) | Owns the layer's definition and implementation |
| [Delivery](../03-delivery-layer.md) | Owns the layer's definition and implementation |
| [AI](../02-ai-layer.md) | Owns the layer's definition and implementation |

## 9.3 Responsibilities

### 9.3.1 In every layer
As defined in [2.7.2](../02-ai-layer.md#272-ai-enablement-lead), [3.7.3](../03-delivery-layer.md#373-ai-enablement-lead), and [4.7.3](../04-value-layer.md#473-ai-enablement-lead):
- **Definition of the layer.** Contracts, behaviors, policies, and shared skills and conventions. Changes to them are deliberate and known to the people who rely on them.
- **Independence.** What makes and what judges stay separate, in practice and not only on paper: Change and Verify in the AI layer, preparing a delivery and validating or confirming it in Delivery, shaping an initiative and measuring it in Value.
- **Models.** Which model serves which contract or behavior is decided from evaluations on the organization's own products.
- **Alignment with the products.** The layer's adaptation reflects the real lifecycle stage of each area and the real adoption maturity of each element.
- **Outcomes and change.** The layer changes based on its outcomes, not on opinion. Where its use is disputed, the AI Enablement Lead's interpretation applies.

### 9.3.2 In the AI layer
- **Sensitive areas.** The list the layer uses to declare sensitive areas is maintained and current.

### 9.3.3 In the implementation
As set out in the [Implementation Guidelines](../06-implementation-guidelines.md):
- **Skills and conventions.** One skill per behavior, versioned, encoding the behavior as its layer defines it.
- **Tools and permissions.** Each behavior gets only what its outputs require.
- **Trace.** Every contribution leaves its trace with its output.
- **Evaluation.** Models and changes to skills are evaluated before use, as rigorously as the [adoption maturity](../05-maturity.md#52-unit-of-assessment) of the behavior's implementation requires.
- **Moving up.** What each element lacks for its next level of [adoption maturity](../05-maturity.md#57-moving-up) directs how the implementation is improved.

## 9.4 Behaviors run

None. The AI Enablement Lead defines and maintains the behaviors; the Product Manager and the Agentic Engineer run them.

## 9.5 Decisions

### 9.5.1 Decides
- Changes to contracts, behaviors, layer policies, skills, and conventions.
- Which model serves each contract or behavior, based on evaluation.
- The tools and permissions of each behavior.
- The list of sensitive areas.
- The interpretation of the framework where its use is disputed.

### 9.5.2 Does not decide
- What is worth building, or anything else that belongs to the Product Manager.
- Whether a result is accepted, or anything else that belongs to the Agentic Engineer.
- Any change to a [principle](../01-layers.md#17-principles), or anything that loosens a [framework policy](../01-layers.md#18-framework-policies). A layer may make a framework policy stricter, never looser.

## 9.6 Independence

No one judges their own work, including the AI Enablement Lead:
- Every change to a skill, model, or permission is evaluated before use.
- Every change is known to the people who rely on it before it applies.

## 9.7 Competencies

- **Systems thinking:** seeing how a change to one layer affects the others.
- **Codifying behavior:** turning the definition of a behavior into a skill that acts the same way whoever runs it.
- **Evaluation:** judging models and skills against the organization's own products.
- **Security judgment:** least privilege, sensitive areas, and keeping personal data out of every AI context.
- **Measuring outcomes:** recognizing from the outcomes where a layer has become slow, unsafe, or untrusted.
- **Developing people:** helping the Product Manager and the Agentic Engineer grow into their roles.
