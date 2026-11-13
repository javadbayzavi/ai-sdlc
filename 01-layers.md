# Chapter 1: Layers

The development model has three concentric layers. Each layer wraps the one inside it and constrains it. Everything is built around AI.

## 1.1 The three layers

**[Value](04-value-layer.md).** Treats the product as a business entity that generates value over its lifecycle. Faces the organization, the market, and the users. Decides what is worth doing, how much risk is acceptable, when to stop or retire, and who is accountable for the result. Value here covers cost and risk as well as gain; it is not a value stream in the sense of a delivery flow.

**[Delivery](03-delivery-layer.md).** The translation layer. It maps business terms to technical terms per domain, per product feature, and for cross-cutting concerns such as technical debt, security, deployment, and infrastructure. The mapping runs in both directions: business intent is explained to the technical side, and technical reality is explained to the business side. Delivery knowledge is owned by the Agentic Engineer for its technical half and by the Product Manager for its business half. Where AI drafts it, its owner confirms it.

**[AI](02-ai-layer.md).** Where almost all the work is done. The AI is fast and cheap, but non-deterministic, limited to the context it is given, and unable to be accountable.

## 1.2 The role of AI in each layer

In the core, the AI is the **actor**: it does the work.

In the outer layers, the AI is an **instrument** of the humans who own the layer. It prepares evidence, drafts, and challenges. Decisions and accountability stay with people.

Any AI used in the Delivery and Value layers must be independent of the AI doing the work in the core. Otherwise the system ends up judging itself.

## 1.3 Contracts and behavior

Each layer works through two kinds of things:

- **Contracts** between neighboring layers: Value and Delivery, and Delivery and AI. A contract defines how two layers communicate in all cases: what is requested inward, what is returned outward, and what happens when the inner layer cannot deliver. Contracts change only deliberately, based on the layer's outcomes, and are known to everyone who relies on them before they change.
- **Behavior** inside each layer: how the layer plays its part so the product gets built.

Contracts are designed from the core outward. We first define what the AI needs to do reliable work and what it must return to be trusted. Delivery is shaped by that, and Value by what Delivery needs.

AI used as an instrument inside a layer belongs to that layer's behavior, not to the contracts.

## 1.4 Product knowledge: a cross-cutting concern

Product knowledge is one body of knowledge that runs through all three layers. Each layer holds it at a different level of abstraction. The outer levels are written for humans and the business. The inner levels are more technical and written for AI.

| Layer | Level of knowledge | Example sources |
|---|---|---|
| [Value](04-value-layer.md#43-knowledge-sources) | Why the product is worth building | Strategy, customer evidence, market, business data |
| [Delivery](03-delivery-layer.md#33-knowledge-sources) | Why the product works the way it does | Business-to-technical mapping per domain and feature, cross-cutting concerns |
| [AI](02-ai-layer.md#23-knowledge-sources) | What the product does | Code, PR comments, commit messages, static analysis reports |

At both edges the model touches the product. The AI layer touches the product as it is built. The Value layer touches the product as it is experienced. Neither can be used raw: code repeats its own bad patterns, and feedback is noisy and late.

### 1.4.1 Consistency

The knowledge must be consistent across all levels. The code is explained by Delivery knowledge, and Delivery knowledge is justified by Value.

A gap between levels is a signal:

- Code that Delivery cannot explain: undocumented behavior or a bug.
- A feature that Value cannot justify: waste, or a candidate for retirement.
- A Value claim that Delivery and the code do not support: a false commitment.

Improving knowledge means finding and closing these gaps, not only writing more of it.

### 1.4.2 Sources of truth

Each kind of fact has exactly one source of truth across the whole framework. When another source disagrees with it, the other source is corrected.

| Kind of fact | Source of truth | Owning layer |
|---|---|---|
| What the product does | The code | AI |
| What the product should do | The committed intent and its specs | Delivery |
| Why it works this way | Recorded decisions | Delivery |
| What was delivered to whom | Delivery records | Delivery |
| How it is used | Usage data | Delivery |
| Why it is worth building | Value decisions | Value |

The code is the truth for what the product is; the intent and its specs are the truth for what it should be. When they disagree, either the code departs from what it should be, which is a bug, or knowledge departs from what the product is, which is stale knowledge.

## 1.5 Two kinds of maturity

The model uses two separate kinds of maturity. They answer different questions and must not be confused.

**Lifecycle stage** is the maturity of the product, a domain, or a feature: new idea, in development, mature, or retiring. It answers: *what does this work demand?* A new idea calls for fast, cheap learning. A feature in development calls for building towards completeness. A mature feature calls for preserving what already works. A retiring feature calls for removing it without breaking what still depends on it.

**Adoption maturity** is how far this model has been adopted in a layer of a given product. It answers: *how ready is this layer to carry its part?* It covers four dimensions: the layer's knowledge, implementation, roles, and outcomes. Its levels and how they are assessed are defined in [the Maturity chapter (Chapter 5)](05-maturity.md).

Adoption maturity is measured per layer, not per product. A product can have strong Value and a weak AI layer, or the reverse. This is what lets the model be applied to any product, including an existing product with poor knowledge: each layer works at its current level instead of the product having to be ready first.

The two combine. A mature part of the product in a layer with low adoption maturity is the riskiest combination: the work must preserve behavior that the layer does not yet fully understand.

Maturity adapts only the elements of a layer it actually affects. It does not apply to every element.

## 1.6 Running the layers

Layers do not run themselves; roles run them: the [Product Manager](roles/07-product-manager.md), the [Agentic Engineer](roles/08-agentic-engineer.md), and the [AI Enablement Lead](roles/09-ai-enablement-lead.md). When something fails, such as a failed validation, it is handled by the judgment of whoever runs the layer, not by a mechanism inside the layer.

## 1.7 Framework policies

These policies apply to every layer. A layer may make a framework policy stricter or give it a concrete interpretation, but never make it looser.

### 1.7.1 Authority
- A layer acts only within its purpose and on requests that come through its contracts.
- A layer never fills gaps with assumptions. When intent is unclear, conflicts with reality, or would cross a boundary, it stops and asks.
- No one judges their own work. Verification is independent of whoever produced the work.
- A layer acts only within the boundary it was given. What it notices outside that boundary, it reports.

### 1.7.2 Honesty
- Uncertainty is always stated, never hidden. "Could not be determined" is a valid answer; a confident guess is not.

### 1.7.3 Autonomy
- The autonomy given to AI follows lifecycle stage and adoption maturity, never personal preference or tool defaults.
- Autonomy is lowest where the stakes are highest and understanding is lowest: mature parts with low adoption maturity.
- Work touching a sensitive area is never fully autonomous, at any stage or maturity.
- Autonomy can be tightened for a single request, but never loosened beyond the layer's interpretation.

### 1.7.4 Data protection
- No personal data, secrets, or credentials enter the context of any AI, in any layer.

## 1.8 What defines each layer

Each layer is described by the same elements:

| Element | Question |
|---|---|
| Purpose | The layer's main duties: what would be lost without the layer, which no other layer can take over |
| Contracts | How it communicates with its neighboring layers in all cases |
| Knowledge sources | What product knowledge it owns, keeps alive, and learns from |
| Policies | The rules the layer must follow, including what it must never do |
| Behavior | How the layer is expected to act, for each contract it serves or, where it owns no contracts, for each of its activities |
| AI contributions | How AI is used in this layer, as actor or as instrument, and how that use is materialized |
| Role contributions | What each role is responsible for in this layer |
| Outcomes | What the layer has actually achieved over time against its purpose. Outputs of an individual request, including proof of change, are not part of this element. |
| Adaptation | How lifecycle stage and adoption maturity change the layer. Stated within each element where it applies. |

## 1.9 Model

![The layered model](model.svg)

- **Rings:** Value (outer), Delivery (middle), AI (core).
- **[Value layer](04-value-layer.md#45-behavior):** the seven behaviors as slices, each with its place in the PDCA loop, around a band naming the components of the layer.
- **[Delivery layer](03-delivery-layer.md#35-behavior):** the five behaviors as slices, each with its place in the PDCA loop, around a band naming the components of the layer.
- **[AI layer](02-ai-layer.md#25-behavior):** the five behaviors as slices, each with its place in the PDCA loop, around a core naming the components of the layer.
- Each Delivery behavior sits directly outside its AI counterpart: Explain and Explore, Evaluate and Assess, Deliver and Change, Validate and Verify, Confirm and Reconcile.
- **[Product knowledge](#14-product-knowledge-a-cross-cutting-concern):** the cross-cutting slice through all layers, at a different level of abstraction in each: what the product does (AI), why it works this way (Delivery), and why it is worth building (Value).
