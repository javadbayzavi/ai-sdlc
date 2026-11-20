# Appendix A: Alignment with Established Practices

## A.1 Purpose

This appendix shows how the framework relates to established methods and standards. It states alignment only; it does not claim conformance to any standard.

## A.2 PDCA

The behaviors of each layer cover the Plan-Do-Check-Act cycle at that layer's level of abstraction:

| Step | [Value](04-value-layer.md#45-behavior) | [Delivery](03-delivery-layer.md#35-behavior) | [AI](02-ai-layer.md#25-behavior) |
|---|---|---|---|
| Plan | [Discover](04-value-layer.md#451-discover), [Shape](04-value-layer.md#452-shape), [Prioritize](04-value-layer.md#453-prioritize) | [Explain](03-delivery-layer.md#351-explain), [Evaluate](03-delivery-layer.md#352-evaluate) | [Explore](02-ai-layer.md#251-explore), [Assess](02-ai-layer.md#254-assess) |
| Do | [Commit](04-value-layer.md#454-commit), [Realize](04-value-layer.md#455-realize) | [Deliver](03-delivery-layer.md#353-deliver) | [Change](02-ai-layer.md#252-change) |
| Check | [Measure](04-value-layer.md#456-measure) | [Validate](03-delivery-layer.md#354-validate), [Confirm](03-delivery-layer.md#355-confirm) | [Verify](02-ai-layer.md#253-verify), [Reconcile](02-ai-layer.md#255-reconcile) |
| Act | [Steer](04-value-layer.md#457-steer) | Decided in Value | Decided in Delivery |

- **Act.** Acting on what a check finds belongs to whoever is accountable for it ([1.7.1](01-layers.md#171-accountability)). What the checks of Delivery find is decided in Value, and what the checks of the AI layer find is decided in Delivery. Corrections are made through Do.
- **Do in Value.** Value does not change the product. What it commits is delivered by Delivery.
- **Not an order of steps.** The cycle shows that each layer can plan, do, check, and act at its own level. A request may be served by any of the behaviors, or answered from knowledge already held, without the others.

## A.3 ISO/IEC 33020

The [adoption maturity levels](05-maturity.md#54-levels) follow the process capability levels of ISO/IEC 33020: 0 Incomplete, 1 Performed, 2 Managed, 3 Established, 4 Predictable, 5 Innovating. As ISO/IEC 33020 rates each process on its own rather than an organization as a whole, the framework assesses each element on its own rather than a layer or a product ([5.2](05-maturity.md#52-unit-of-assessment)). The framework is aligned with that scale; it does not claim conformance to it.

## A.4 Principles and policies

The [principles](01-layers.md#17-principles) of the framework restate established principles of governance and management for work in which AI takes part:

| Principle | Established principle | Example source |
|---|---|---|
| [Accountability](01-layers.md#171-accountability) | One accountable party for every decision | ISO/IEC 38500 (Responsibility) |
| [Independence](01-layers.md#172-independence) | Segregation of duties | ISO/IEC 27001 (Annex A 5.3) |
| [Knowledge outside the model](01-layers.md#174-knowledge-outside-the-model) | Organizational knowledge is maintained and made available | ISO 9001 (7.1.6) |
| [Shared, not personal](01-layers.md#176-shared-not-personal) | Work follows documented instructions available to everyone who needs them, not individual practice | ISO 9001 (7.5, Documented information) |
| [Adaptation](01-layers.md#177-adaptation) | Tailoring to the context of the work | PRINCE2 (Tailor to suit the project) |

[Honesty](01-layers.md#173-honesty) and [Given context](01-layers.md#175-given-context) have no direct counterpart; they are specific to this framework.

Some policies realize an external principle directly rather than a principle of the framework. [Data protection](01-layers.md#184-data-protection) realizes information security and privacy, as set out in ISO/IEC 27001, ISO/IEC 27701, and the security practices of COBIT.
