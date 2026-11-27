# Appendix B: Glossary

Each term is explained in a few words, with a link to where the handbook defines or uses it. Where the two differ, the linked section is the reference.

**Acceptance criteria.** The conditions that say when an intent or a change is met. They are set before work starts, so that met is defined in advance. See [3.5.3](03-delivery-layer.md#353-deliver) and [2.2.2](02-ai-layer.md#222-change).

**Accountability.** The principle that people are accountable and AI never is. See [1.7.1](01-layers.md#171-accountability).

**Actor and instrument.** The two ways AI takes part. In the AI layer it is the actor: it does the work. In the Delivery and Value layers it is an instrument: it prepares, drafts, and challenges, and people decide. See [1.2](01-layers.md#12-the-role-of-ai-in-each-layer).

**Adaptation.** The principle that how a layer works, and how much autonomy the AI has, follow lifecycle stage and adoption maturity. See [1.7.7](01-layers.md#177-adaptation).

**Adaptation parameters.** The lifecycle stage of the areas a request involves and the adoption maturity of what the work relies on, stated with every request to the AI layer. See [2.2](02-ai-layer.md#22-contracts).

**Adoption maturity.** How far the framework is in place in the development of a product, assessed for each element on its own, on levels 0 to 5. See [1.5](01-layers.md#15-two-kinds-of-maturity) and [Chapter 5](05-maturity.md).

**Agentic Engineer.** The role that turns intent into product change delivered to users, with the AI doing the work. It is the only role that brings work into the AI layer. See [Chapter 8](roles/08-agentic-engineer.md).

**AI Enablement Lead.** The role that keeps the framework fit for the products: the definition and implementation of every layer. It does not do product work. See [Chapter 9](roles/09-ai-enablement-lead.md).

**AI layer.** The core layer, where the product is understood as it really is and changed. See [Chapter 2](02-ai-layer.md).

**Area.** A piece of the product that knowledge and a lifecycle stage are held for: the product as a whole, a domain, a feature, or the code that realizes it. See [1.5](01-layers.md#15-two-kinds-of-maturity).

**Assess.** The AI-layer behavior that shows, before a change is made, what it would touch and what could go wrong. See [2.5.4](02-ai-layer.md#254-assess).

**Autonomy.** How much the AI does without step-by-step human review. It is lowest where the stakes are highest and understanding is lowest. See [1.8.2](01-layers.md#182-autonomy) and [2.4.3](02-ai-layer.md#243-autonomy).

**Behavior.** How a layer is expected to act, for each contract it serves or each of its activities. Each layer has its own set. See [1.3](01-layers.md#13-contracts-and-behavior).

**Boundary.** The limit of what a request may look at or change. What is noticed outside it is reported, not acted on. See [1.8.1](01-layers.md#181-authority).

**Business knowledge.** The part of Delivery knowledge kept outside the code, in ticketing and documentation systems. It points to the specs that realize it. See [3.3.2](03-delivery-layer.md#332-where-knowledge-lives).

**Change.** The AI-layer behavior that makes a change to the product that fulfills its job description, and returns it with proof and updated knowledge. See [2.5.2](02-ai-layer.md#252-change).

**Claim.** A statement about the product that is checked against it: about what the product does, in [Reconcile](02-ai-layer.md#255-reconcile), or about the product in business terms, such as a commitment to customers, in [Confirm](03-delivery-layer.md#355-confirm).

**Code-level knowledge.** What the AI layer records about the code, versioned with it: local knowledge in comments and tests, and structural knowledge in files next to the code it describes. Also called recorded knowledge. See [2.3.2](02-ai-layer.md#232-where-recorded-knowledge-lives).

**Commit.** The Value behavior that turns a prioritized initiative into an intent for Delivery and, where deliberate, a promise made outward. See [4.5.4](04-value-layer.md#454-commit).

**Commitment.** A promise made outward, to customers or peer plans. It is made only when what it would take is known and the claim is confirmed against the product. See [4.4.2](04-value-layer.md#442-commitments).

**Confirm.** The Delivery behavior that judges, feature by feature, whether a claim about the product is supported by the product. Not to be confused with an owner confirming a draft. See [3.5.5](03-delivery-layer.md#355-confirm).

**Confirmation of a draft.** The owner's acceptance that turns a draft into knowledge or a decision. See [3.4.5](03-delivery-layer.md#345-autonomy) and [4.4.6](04-value-layer.md#446-autonomy).

**Contract.** How two neighboring layers communicate in all cases: what is asked of the inner layer, what it returns, and what happens when it cannot deliver. See [1.3](01-layers.md#13-contracts-and-behavior).

**Convention.** A craft rule of a layer, shared by all the skills of that layer. See [6.3.1](06-implementation-guidelines.md#631-skill).

**Customer evidence.** Interviews, feedback, requests, and observed behavior that show customers' jobs, pains, and gains. What customers do outweighs what they say. See [4.3](04-value-layer.md#43-knowledge-sources).

**Debt.** Technical debt introduced by a delivery. It is always reported, and Value decides whether to pay, accept, or defer it. See [3.4.3](03-delivery-layer.md#343-debt).

**Deliver.** The Delivery behavior that puts a committed intent in users' hands, healthy in production, with evidence that it meets the intent and feature knowledge updated to match. See [3.5.3](03-delivery-layer.md#353-deliver).

**Delivery layer.** The translation layer between business intent and technical work, in both directions. See [Chapter 3](03-delivery-layer.md).

**Delivery records.** What was released, when, and to whom, including versions and configuration per customer. See [3.3.1](03-delivery-layer.md#331-sources).

**Dimension.** One of the four kinds of element that adoption maturity assesses: knowledge, implementation, roles, and outcomes. See [5.3](05-maturity.md#53-dimensions).

**Discover.** The Value behavior that builds an understanding, from outside the product, of where value lies. See [4.5.1](04-value-layer.md#451-discover).

**Draft.** An output of the AI in the Delivery or Value layer. It becomes knowledge or a decision only when its owner confirms it. See [3.4.5](03-delivery-layer.md#345-autonomy) and [4.4.6](04-value-layer.md#446-autonomy).

**Element.** One of the parts that describe a layer, such as its knowledge sources, behaviors, roles, and outcomes. Adoption maturity is assessed for each element. In Chapter 6, the word also names the parts of a behavior's implementation. See [1.9](01-layers.md#19-what-defines-each-layer) and [6.2](06-implementation-guidelines.md#62-elements-of-an-implementation).

**Evaluate.** The Delivery behavior that judges, before commitment, what delivering an intent would take, what it would touch, and what could go wrong. See [3.5.2](03-delivery-layer.md#352-evaluate).

**Explain.** The Delivery behavior that gives an account of a feature in business terms: what it does, why it works that way, and its current state and risks. See [3.5.1](03-delivery-layer.md#351-explain).

**Explore.** The AI-layer behavior that gives an accurate account of the product as it really is, within a boundary, including what could not be determined. See [2.5.1](02-ai-layer.md#251-explore).

**Feature knowledge.** The why of each feature: decisions and trade-offs, acceptance criteria, and how its business terms map to its technical parts. See [3.3.1](03-delivery-layer.md#331-sources).

**Finding.** Something Explore or Verify reports about the product, either backed by the code or marked as what could not be determined. See [2.5.1](02-ai-layer.md#251-explore) and [2.5.3](02-ai-layer.md#253-verify).

**Framework policy.** A policy that applies to every layer. See [1.8](01-layers.md#18-framework-policies).

**Given context.** The principle that the AI works on the context it is given and asks for what is missing, never assuming it. See [1.7.5](01-layers.md#175-given-context).

**Highest demand.** For each behavior, the combination of lifecycle stage and adoption maturity that calls for the most care, usually a mature area whose knowledge is at low adoption maturity. Stated with each behavior in Chapters 2 to 4.

**Honesty.** The principle that uncertainty is stated, never filled with assumptions. See [1.7.3](01-layers.md#173-honesty).

**Hypothesis.** What a new idea is meant to test. For a new idea, success means the hypothesis is answered, either way. See [4.5.2](04-value-layer.md#452-shape).

**Independence.** The principle that no one judges their own work. See [1.7.2](01-layers.md#172-independence).

**Initiative.** What Value would do and for whom, with the customer and business value it expects, how success would be recognized, when it stops, and the lifecycle stage it concerns. See [4.5.2](04-value-layer.md#452-shape).

**Intent.** What is wanted and why, without the solution. Value commits an intent, and Delivery delivers it. An intent not yet committed can be evaluated. See [3.2](03-delivery-layer.md#32-contracts).

**Job description.** What a change is asked to do: its intent, acceptance criteria, and what must not change. See [2.2.2](02-ai-layer.md#222-change).

**Jobs, pains, and gains.** What customers are trying to get done, what stands in their way, and what they hope to gain: the basis of customer value. See [4.1](04-value-layer.md#41-purpose) and [4.5.1](04-value-layer.md#451-discover).

**Knowledge outside the model.** The principle that everything the AI needs and produces exists outside the model, so models can be replaced. See [1.7.4](01-layers.md#174-knowledge-outside-the-model).

**Layer.** One of the three levels at which the framework describes product development: Value, Delivery, and AI. See [1.1](01-layers.md#11-the-three-layers).

**Levels of adoption maturity.** 0 Incomplete, 1 Performed, 2 Managed, 3 Established, 4 Predictable, 5 Innovating. See [5.4](05-maturity.md#54-levels).

**Lifecycle stage.** The maturity of an area of the product: new idea, in development, mature, or retiring. See [1.5](01-layers.md#15-two-kinds-of-maturity).

**Low and high.** The two bands of adoption maturity that behaviors adapt to: levels 0 to 2, and levels 3 to 5. See [5.5](05-maturity.md#55-low-and-high).

**Materialization.** Where the inputs, outputs, and trace of the AI's contributions live in each layer. See [2.6](02-ai-layer.md#26-ai-contributions), [3.6](03-delivery-layer.md#36-ai-contributions), and [4.6](04-value-layer.md#46-ai-contributions).

**Measure.** The Value behavior that judges, against what an initiative expected, whether value was created for customers and for the business. See [4.5.6](04-value-layer.md#456-measure).

**Model.** The AI model used for a behavior. It is part of the setup, chosen from evaluations on the organization's own products, not by whoever runs the behavior. See [2.4.4](02-ai-layer.md#244-models) and [6.3.8](06-implementation-guidelines.md#638-models).

**Open point.** An unknown, an item that could not be verified, or a contradiction that is kept open to be resolved rather than treated as a risk. Behaviors treat them this way mostly for new ideas and areas in development.

**Opportunity.** A place where value could be created, found by Discover with its evidence. Shape turns it into an initiative. See [4.5.1](04-value-layer.md#451-discover).

**Outcome.** What a layer has achieved over time against its purpose. The output of a single request is not an outcome. See [1.9](01-layers.md#19-what-defines-each-layer).

**Peer plans.** The plans of other products and shared platforms: what they need from the product, and what it depends on. See [4.3.1](04-value-layer.md#431-sources).

**Pinning.** Capturing the existing behavior of a mature or retiring area in tests, through a separate Change that changes no behavior, before the area is changed at low adoption maturity. The pinning is verified and accepted before the change starts. See [2.4.3](02-ai-layer.md#243-autonomy).

**Policy.** A rule that turns a principle into what must or must not be done. See [1.8](01-layers.md#18-framework-policies).

**Posture.** How AI is used in a layer: as a delegated actor or as an instrument. See [2.6](02-ai-layer.md#26-ai-contributions), [3.6](03-delivery-layer.md#36-ai-contributions), and [4.6](04-value-layer.md#46-ai-contributions).

**Principle.** What the framework stands on. Principles apply everywhere and are never tailored. See [1.7](01-layers.md#17-principles).

**Prioritize.** The Value behavior that orders initiatives within strategy and capacity, and lays them out over time as the roadmap. See [4.5.3](04-value-layer.md#453-prioritize).

**Problem reports.** Incidents and support issues, tied to features and their business impact. See [3.3.1](03-delivery-layer.md#331-sources).

**Product knowledge.** The one body of knowledge about the product that runs through all three layers, at a different level of abstraction in each. See [1.4](01-layers.md#14-product-knowledge-a-cross-cutting-concern).

**Product Manager.** The role accountable for the value of the product. It runs the Value layer and brings the business into Delivery. See [Chapter 7](roles/07-product-manager.md).

**Proof of change.** The evidence returned with a change that it fulfills its job description and leaves everything else intact. See [2.5.2](02-ai-layer.md#252-change).

**Realize.** The Value behavior that turns delivered change into value customers actually get, and keeps what is said about the product outward true. See [4.5.5](04-value-layer.md#455-realize).

**Reconcile.** The AI-layer behavior that judges, claim by claim, whether existing knowledge still holds against the code. See [2.5.5](02-ai-layer.md#255-reconcile).

**Release.** Delivered change reaching users. It reaches them in a way that can be reversed, its health is watched, and a failed release is restored. See [3.5.3](03-delivery-layer.md#353-deliver).

**Request.** Any inquiry or contribution to the development of the product, made to a layer through its contracts. It is answered with a result or with a stop. Many requests are questions answered from knowledge already held, and need not lead to any change. See [2.2](02-ai-layer.md#22-contracts) and [3.2](03-delivery-layer.md#32-contracts).

**Risk.** An unknown, an item that could not be verified, or a contradiction that is treated as possible harm. Behaviors treat them this way mostly for mature and retiring areas.

**Roadmap.** The initiatives laid out over time. It is a plan, not a commitment, and can be revised. See [4.5.3](04-value-layer.md#453-prioritize).

**Role.** One of the three parts people play in running the layers: Product Manager, Agentic Engineer, and AI Enablement Lead. A role may be held by many people. See [1.6](01-layers.md#16-running-the-layers).

**Runtime signals.** Logs, exceptions, and other technical details from development, test, deployment, and production. They are cleaned of personal data, secrets, and credentials before use. See [2.3.1](02-ai-layer.md#231-sources) and [2.4.2](02-ai-layer.md#242-data-and-security).

**Sensitive area.** An area of the product where work is never fully autonomous, such as authentication, authorization, secrets, or licensing. Its list is kept current by the AI Enablement Lead. See [1.8.2](01-layers.md#182-autonomy), [2.4.2](02-ai-layer.md#242-data-and-security), and [9.3.2](roles/09-ai-enablement-lead.md#932-in-the-ai-layer).

**Session.** One run of a behavior. It starts from the skill, the conventions, and the request, and ends with the output. Nothing is kept between sessions except what is in an output. See [6.3.3](06-implementation-guidelines.md#633-knowledge) and [6.3.4](06-implementation-guidelines.md#634-invocation).

**Shape.** The Value behavior that turns an opportunity into an initiative clear enough to be weighed, delivered, and judged. See [4.5.2](04-value-layer.md#452-shape).

**Shared, not personal.** The principle that AI contributions are made through instructions written down and open to everyone who does that work, never through personal prompts or habits. See [1.7.6](01-layers.md#176-shared-not-personal).

**Skill.** The codified instructions the AI follows for a behavior. Each behavior has one. See [6.3.1](06-implementation-guidelines.md#631-skill).

**Source of truth.** The one source that each kind of fact is checked against. When another source disagrees, the other source is corrected. See [1.4.2](01-layers.md#142-sources-of-truth).

**Specs.** The technical half of feature knowledge. They live in the code, versioned with what they describe, and point to the business record they serve. See [3.3.2](03-delivery-layer.md#332-where-knowledge-lives).

**Standing intent.** A committed intent with an explicit scope and capacity, such as capacity committed to debt reduction. See [4.5.4](04-value-layer.md#454-commit).

**Steer.** The Value behavior that adjusts the product's direction to what has been learned: lifecycle stages, initiatives, and the roadmap. See [4.5.7](04-value-layer.md#457-steer).

**Stop.** An answer that names what is missing, unclear, or in conflict, as a question, instead of a result built on an assumption. A stop is a complete answer. See [1.8.1](01-layers.md#181-authority) and [6.3.5](06-implementation-guidelines.md#635-output).

**Stop condition.** The evidence, decided when an initiative is shaped, that would end it. See [4.5.2](04-value-layer.md#452-shape) and [4.5.7](04-value-layer.md#457-steer).

**Tailoring.** Adopting and adapting the framework to a product. Everything except the principles is tailored. Improving how the framework is tailored is the work of the AI Enablement Lead, governed by the organization's own frameworks for improvement and governance. See [1.7](01-layers.md#17-principles) and [9.1](roles/09-ai-enablement-lead.md#91-purpose).

**Trace.** What every AI contribution leaves with its output: what it served, the adaptation parameters, the skill version, the model, and who confirmed the result. See [1.8.3](01-layers.md#183-trace).

**Validate.** The Delivery behavior that judges whether what was delivered serves the intent in the hands of users. See [3.5.4](03-delivery-layer.md#354-validate).

**Value.** What makes the product worth building: customer value, how it helps customers with their jobs, pains, and gains, and business value, what it returns against what it costs and risks. See [4.1](04-value-layer.md#41-purpose).

**Value layer.** The outer layer, which decides what is worth building over the product's lifecycle and judges whether what is delivered creates that value. See [Chapter 4](04-value-layer.md).

**Verdict.** A judgment backed by evidence, given per acceptance criterion, claim, or feature, such as supported, contradicted, or undecidable. See [2.5.3](02-ai-layer.md#253-verify), [2.5.5](02-ai-layer.md#255-reconcile), and [3.5.5](03-delivery-layer.md#355-confirm).

**Verify.** The AI-layer behavior that judges, independently and with evidence, whether a change fulfills its job description and leaves everything else intact. See [2.5.3](02-ai-layer.md#253-verify).

**What must not change.** The part of a job description that names the behavior a change must preserve. It is checked as rigorously as what should change. See [2.2.2](02-ai-layer.md#222-change) and [2.5.3](02-ai-layer.md#253-verify).
