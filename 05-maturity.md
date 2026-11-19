# Chapter 5: Maturity

## 5.1 Purpose

This chapter defines adoption maturity: how far the model has been adopted in a layer of a given product. It sets the levels, what is assessed at each level, and how a layer moves from one level to the next.

Lifecycle stage, the other kind of maturity, is defined in [the Layers chapter (1.5)](01-layers.md#15-two-kinds-of-maturity) and is not covered here.

## 5.2 Unit of assessment

- Adoption maturity is assessed per layer of a product. A product can be at different levels in different layers.
- A layer's level is the lowest level reached across its dimensions. Strength in one dimension does not make up for weakness in another.
- [Principles](01-layers.md#17-principles) and [policies](01-layers.md#18-framework-policies) apply at every level. Maturity changes how much of the model is in place, never what is allowed.
- Models and changes to skills are evaluated before use at every level. Maturity changes how rigorous the evaluation is: below level 4, a model or a changed skill is tried on representative requests from the organization's own products and the result is recorded; from level 4, the evaluation is systematic.

## 5.3 Dimensions

| Dimension | Question |
|---|---|
| Knowledge | Is the layer's knowledge recorded, current, and trusted? |
| Implementation | Are the behaviors set up as the [Implementation Guidelines chapter](06-implementation-guidelines.md) requires: skills, permissions, trace, and models? |
| Roles | Do the roles run the layer as their chapters ([7](roles/07-product-manager.md), [8](roles/08-agentic-engineer.md), [9](roles/09-ai-enablement-lead.md)) describe? |
| Outcomes | Are the layer's outcomes measured and used to improve it? |

## 5.4 Levels

| Level | Knowledge | Implementation | Roles | Outcomes |
|---|---|---|---|---|
| 0 Incomplete | Scattered or absent | Personal chats | Not assigned | Not known |
| 1 Performed | Exists, not trusted | Behaviors carried out, setup varies by person | Assigned | Visible case by case |
| 2 Managed | Recorded where the layer says | Skills, permissions, and trace in place | Confirm and decide as required | Recorded |
| 3 Established | Current, checked regularly | Shared skills and conventions, used by everyone | Run the layer consistently | Reviewed |
| 4 Predictable | Survives checks; few contradictions | Systematic evaluation of models and skills | Decisions based on outcomes | Measured against targets |
| 5 Innovating | Improves from gaps found | Outcomes and evaluation results drive changes to the setup | Feed improvement back | Drive change to the layer |

A level is reached only when its criteria and those of every level below it are met.

### 5.4.1 Level 0: Incomplete
The layer's work is done ad hoc, if at all. This is where an existing product often starts. It is a starting point, not an acceptable way of working.

### 5.4.2 Level 1: Performed
- The behaviors of the layer are carried out and produce the outputs defined in the [AI](02-ai-layer.md#25-behavior), [Delivery](03-delivery-layer.md#35-behavior), and [Value](04-value-layer.md#45-behavior) layer chapters.
- The roles that run the layer are assigned.
- The layer's knowledge exists in some form, but is not trusted without checking.
- Outcomes are visible only case by case.

### 5.4.3 Level 2: Managed
- Every behavior is run through its skill, with the tools and permissions the [Implementation Guidelines](06-implementation-guidelines.md) set, and leaves its trace with the output.
- Every request carries its adaptation parameters.
- Every draft is confirmed by its owner, and every decision is taken by the role it belongs to.
- Knowledge is recorded where the layer says it lives.
- Outcomes are recorded.

### 5.4.4 Level 3: Established
- Skills and conventions are shared and used the same way by everyone who runs the layer.
- Makers and judges are separate in practice.
- Knowledge is kept current and checked regularly against its source of truth.
- Roles run the layer consistently across requests.
- Outcomes are reviewed regularly.

### 5.4.5 Level 4: Predictable
- Models and skills are evaluated systematically: a fixed set of scenarios from the organization's own products, run before every change, with results compared over time.
- Knowledge survives its checks; contradictions are rare.
- Outcomes are measured against targets, and results are consistent from request to request.
- Roles base their decisions on outcomes.

### 5.4.6 Level 5: Innovating
- The layer changes based on its outcomes: skills, conventions, and setup are improved from what the outcomes show.
- Gaps found in knowledge lead to improvements in how knowledge is kept, not only to corrections.
- Evaluation results drive changes to the layer, not only approve them.

## 5.5 Low and high

The behaviors of each layer ([AI](02-ai-layer.md#25-behavior), [Delivery](03-delivery-layer.md#35-behavior), [Value](04-value-layer.md#45-behavior)) adapt to two bands of adoption maturity:

- **Low:** levels 0 to 2.
- **High:** levels 3 to 5.

The line lies at level 3, the first level at which the layer works the same way whoever runs it.

## 5.6 Assessment

- A layer is assessed against the criteria of each level, dimension by dimension.
- Every criterion met is backed by evidence: traces, recorded knowledge, records of outcomes, and decisions.
- A layer is not assessed only by the people who run it.
- The result states the level reached, and for each dimension, what is missing for the next level.

## 5.7 Moving up

- A layer moves up one level at a time. What is missing for the next level is the layer's improvement plan.
- Not every layer has to reach level 5. The level a layer aims for depends on the product and its lifecycle stage.
- While a layer is at a low level, the behaviors of that layer work at low adoption maturity, and autonomy is stricter as the [framework](01-layers.md#182-autonomy) and [AI layer](02-ai-layer.md#243-autonomy) autonomy policies say.

## 5.8 Relation to standards

The levels follow the process capability levels of ISO/IEC 33020, as set out in [Appendix A.3](appendix-a-alignment.md#a3-isoiec-33020).
