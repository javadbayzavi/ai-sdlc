# Chapter 5: Maturity

## 5.1 Purpose

This chapter defines adoption maturity: how far the model is in place in the development of a product. It sets the levels, what is assessed at each level, and how an element moves from one level to the next.

Lifecycle stage, the other kind of maturity, is defined in [the Layers chapter (1.5)](01-layers.md#15-two-kinds-of-maturity) and is not covered here.

## 5.2 Unit of assessment

- Adoption maturity is assessed for each element on its own: the knowledge of each area at each layer, the implementation of each behavior, each role, and each outcome. There is no level for a layer or for a product as a whole.
- An element that does not exist yet is at level 0.
- Work adapts to the lowest level among the elements it relies on, as set out in [the Layers chapter (1.5)](01-layers.md#15-two-kinds-of-maturity).
- [Principles](01-layers.md#17-principles) and [policies](01-layers.md#18-framework-policies) hold at every level, including level 0. Maturity changes how much of the model is in place, never what is allowed. Work that breaks a principle is not at a low level; it is outside this framework.
- Models and changes to skills are evaluated before use at every level. Maturity changes how rigorous the evaluation is: below level 4, a model or a changed skill is tried on representative requests from the organization's own products and the result is recorded; from level 4, the evaluation is systematic.

## 5.3 Dimensions

The elements are of four kinds, the dimensions of adoption maturity. Each is assessed at its own grain.

| Dimension | Assessed for | Question |
|---|---|---|
| Knowledge | Each area, at each layer | Is the knowledge of the area recorded, current, and trusted? |
| Implementation | Each behavior | Is the behavior set up as the [Implementation Guidelines chapter](06-implementation-guidelines.md) requires: skills, permissions, trace, and models? |
| Roles | Each role | Is the role run as its chapter ([7](roles/07-product-manager.md), [8](roles/08-agentic-engineer.md), [9](roles/09-ai-enablement-lead.md)) describes? |
| Outcomes | Each outcome of a layer | Is the outcome measured and used to improve the layer? |

## 5.4 Levels

| Level | Knowledge | Implementation | Roles | Outcomes |
|---|---|---|---|---|
| 0 Incomplete | Absent or scattered | Not set up | Not assigned | Not known |
| 1 Performed | Exists, not trusted | Carried out; instructions applied unevenly | Assigned | Visible case by case |
| 2 Managed | Recorded where the layer says | Skill and permissions in place; output in a fixed form | Decisions taken by the role they belong to | Recorded |
| 3 Established | Current, checked regularly | Shared skill and conventions, used the same way by everyone | Run consistently | Reviewed |
| 4 Predictable | Survives checks; few contradictions | Systematic evaluation of models and skills | Decisions based on outcomes | Measured against targets |
| 5 Innovating | Improves from gaps found | Outcomes and evaluation results drive changes to the setup | Feed improvement back | Drive change to the layer |

A level is reached only when its criteria and those of every level below it are met.

### 5.4.1 Level 0: Incomplete
The element does not exist yet, or exists only ad hoc. Much of a real development starts here: code before a business case, decisions before roles are assigned. The work goes ahead, and the principles already hold:
- **[Accountability](01-layers.md#171-accountability):** every decision has a named person, and every draft is confirmed by its owner, even before roles are assigned.
- **[Independence](01-layers.md#172-independence):** no one judges their own work, even before a judging behavior is set up.
- **[Honesty](01-layers.md#173-honesty):** what is missing is stated as missing.
- **[Knowledge outside the model](01-layers.md#174-knowledge-outside-the-model):** what the AI produces is recorded outside the model and leaves its trace, even before the layer's knowledge is recorded where it lives.
- **[Given context](01-layers.md#175-given-context):** every request states the lifecycle stage of the areas involved and the adoption maturity of what it relies on. "Not known" is a valid answer, and level 0 then applies.
- **[Shared, not personal](01-layers.md#176-shared-not-personal):** AI contributions are made through instructions written down and open to everyone who does that work, never through personal chats.
- **[Adaptation](01-layers.md#177-adaptation):** the work is done with the care of the lowest level, and autonomy is as strict as the autonomy policies set for it.

Level 0 is a starting point. What the element lacks for level 1 is its improvement plan.

### 5.4.2 Level 1: Performed
- **Implementation:** the behavior is carried out and produces the outputs defined in the [AI](02-ai-layer.md#25-behavior), [Delivery](03-delivery-layer.md#35-behavior), and [Value](04-value-layer.md#45-behavior) layer chapters. Its instructions are written down, but applied unevenly.
- **Roles:** the role is assigned.
- **Knowledge:** the knowledge of the area exists in some form, but is not trusted without checking.
- **Outcomes:** the outcome is visible only case by case.

### 5.4.3 Level 2: Managed
- **Implementation:** the behavior is run through its skill, with the tools and permissions the [Implementation Guidelines](06-implementation-guidelines.md) set, and returns its output in a fixed form.
- **Roles:** every decision is taken by the role it belongs to.
- **Knowledge:** the knowledge of the area is recorded where the layer says it lives.
- **Outcomes:** the outcome is recorded.

### 5.4.4 Level 3: Established
- **Implementation:** the skill and conventions are shared and used the same way by everyone who runs the behavior. Makers and judges are separated by the setup itself: separate skills and sessions.
- **Roles:** the role is run consistently across requests.
- **Knowledge:** the knowledge of the area is kept current and checked regularly against its source of truth.
- **Outcomes:** the outcome is reviewed regularly.

### 5.4.5 Level 4: Predictable
- **Implementation:** models and skills are evaluated systematically: a fixed set of scenarios from the organization's own products, run before every change, with results compared over time.
- **Roles:** the role bases its decisions on outcomes.
- **Knowledge:** the knowledge of the area survives its checks; contradictions are rare.
- **Outcomes:** the outcome is measured against targets, and results are consistent from request to request.

### 5.4.6 Level 5: Innovating
- **Implementation:** the skill, conventions, and setup are improved from what the outcomes and evaluation results show. Evaluation results drive changes, not only approve them.
- **Roles:** the role feeds what it learns back into the layer.
- **Knowledge:** gaps found in the knowledge of the area lead to improvements in how knowledge is kept, not only to corrections.
- **Outcomes:** the outcome drives change to the layer.

## 5.5 Low and high

The behaviors of each layer ([AI](02-ai-layer.md#25-behavior), [Delivery](03-delivery-layer.md#35-behavior), [Value](04-value-layer.md#45-behavior)) adapt to two bands of adoption maturity:

- **Low:** levels 0 to 2.
- **High:** levels 3 to 5.

The line lies at level 3, the first level at which an element works the same way whoever runs it. The band that applies to a piece of work is that of the lowest element it relies on.

## 5.6 Assessment

- An assessment first establishes that what level 0 requires holds. Where it does not, the work is outside this framework and is given no level.
- Each element is assessed against the criteria of each level.
- Every criterion met is backed by evidence: traces, recorded knowledge, records of outcomes, and decisions.
- An element is not assessed only by the people who run it.
- The result states, for each element, the level reached and what is missing for the next level.

## 5.7 Moving up

- An element moves up one level at a time. What is missing for the next level is its improvement plan.
- Not every element has to reach level 5. The level an element aims for depends on the product and on the lifecycle stage of the areas it serves.
- Elements grow with the work: the knowledge of an area grows where the area is worked on.
- While the elements a piece of work relies on are at a low level, the work is done at low adoption maturity, and autonomy is stricter as the [framework](01-layers.md#182-autonomy) and [AI layer](02-ai-layer.md#243-autonomy) autonomy policies say.

## 5.8 Relation to standards

The levels follow the process capability levels of ISO/IEC 33020, as set out in [Appendix A.3](appendix-a-alignment.md#a3-isoiec-33020).
