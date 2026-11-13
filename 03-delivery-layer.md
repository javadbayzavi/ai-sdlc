# Chapter 3: Delivery Layer

## 3.1 Purpose

The Delivery layer turns product intent into work the AI can do, and turns what the AI returns into product change that is delivered to users and that Value can trust.

## 3.2 Contracts

Delivery uses the [contracts of the AI layer](02-ai-layer.md#22-contracts) as defined there. This section defines the contracts Delivery owns towards Value.

Each business request concerns one or more features, each with its lifecycle stage. It ends with either its result or a stop with a question. Delivery reports feature state and risk as they arise, not only when asked.

### 3.2.1 Explain
- **Receives:** a question about a feature or an area of the product.
- **Returns:** what the feature does and why it works that way, and its current state and risks, in business terms.

### 3.2.2 Evaluate
- **Receives:** an intent that has not been committed to.
- **Returns:** what delivering it would take, which features it would touch, the risks, and what cannot be known yet.

### 3.2.3 Deliver
- **Receives:** a committed intent.
- **Returns:** the intent delivered to users and healthy in production, with evidence that it meets the intent, any debt introduced, and the feature knowledge updated to match.

### 3.2.4 Validate
- **Receives:** a delivered intent.
- **Returns:** whether what was delivered serves the intent in the hands of users, with evidence.

### 3.2.5 Confirm
- **Receives:** a claim about the product.
- **Returns:** whether the product supports it, contradicts it, or does not allow it to be decided, feature by feature.

## 3.3 Knowledge sources

### 3.3.1 Sources
- **Feature knowledge:** the why of each feature: decisions and trade-offs, acceptance criteria, and how its business terms map to its technical parts.
- **Intents and evaluations:** what was asked for, why, what was evaluated, and what was committed or turned down.
- **Designs:** the intended experience. For a new idea, the design may be the main thing delivered; in development, it is part of what met means; once delivered, the decision behind it lives on in feature knowledge.
- **Delivery records:** what was released, when, and to whom, including versions and configuration per customer.
- **Product usage:** how features are actually used.
- **Problem reports:** incidents and support issues, tied to features and their business impact.
- **Validation results:** what each delivery taught.
- **Code-level truth, through the AI layer:** claims checked with [Reconcile](02-ai-layer.md#225-reconcile), gaps filled with [Explore](02-ai-layer.md#221-explore), technical reach from [Assess](02-ai-layer.md#224-assess). The code is never read directly.

### 3.3.2 Where knowledge lives
- **Specs** live in the code: versioned with what they describe, and checkable against it.
- **Business knowledge** lives outside the code, in the ticketing and documentation systems.
- The two point to each other: each spec references the business record it serves, and each business record references the specs that realize it.

### 3.3.3 Precedence
Sources of truth are defined in [the Layers chapter (1.4.2)](01-layers.md#142-sources-of-truth). Feature knowledge, designs, memory, and opinion give way to them. The code is reached only through the AI layer.

## 3.4 Policies

The framework policies defined in [the Layers chapter (1.7)](01-layers.md#17-framework-policies) apply. This layer adds:

### 3.4.1 Knowledge
- A delivery is not complete until the feature knowledge matches it.
- Specs and business knowledge always point to each other.
- Code-level truth comes only through the AI layer. The code is not read directly.
- The layer reaches only knowledge at its own level. Value knowledge comes only through the contract.

### 3.4.2 Intent
- An unclear intent is returned with questions, never delivered on assumptions.
- A change to a committed intent during delivery is a new business request. The delivery in progress continues as committed or is stopped; it is never silently reshaped.
- Urgency may compress Explain and Evaluate, never skip Validate.

### 3.4.3 Debt
- Debt introduced is always reported.
- Reported debt receives an explicit decision from Value: pay it, accept it, or defer it.

### 3.4.4 Data and security
- Usage data, problem reports, and delivery records are cleaned of personal data before they enter any AI context.

### 3.4.5 Autonomy
- The AI never decides in this layer. Every draft requires confirmation by its owner, at every lifecycle stage and adoption maturity.

## 3.5 Behavior

### 3.5.1 Explain

**Aim:** an account of a feature in business terms: what it does, why it works that way, and its current state and risks, grounded in the product as it really is.

**Used for:**
- Informing business decisions about a feature.
- Providing evidence for lifecycle stage decisions.
- Understanding a feature before an intent concerning it is weighed.

**Expected behavior:**
- The explanation reflects the product as it really is, not what was intended or documented.
- It is written in business terms. Technical detail appears only where it changes a business decision.
- The why is traced to the decisions that shaped the feature. Where the reason has been lost, that is said instead of invented.
- Every statement is either backed by the code or marked as unverified.

**Adaptation by adoption maturity:**

| Adoption maturity | Basis of the explanation | Main risk |
|---|---|---|
| Low | Little feature knowledge; relies mostly on code-level findings | Interpretation compounding across layers; an invented why |
| High | Feature knowledge, confirmed against the code | A stale why, which the code cannot confirm or contradict |

**Adaptation by lifecycle stage:**

| Lifecycle stage | Focus | Unknowns are treated as |
|---|---|---|
| New idea | The hypothesis, and what has been learned so far | Expected |
| In development | What has been built against what was intended, and what remains | Open points |
| Mature | The value it delivers, the behavior users rely on, and its risks | Risks |
| Retiring | Who still relies on it, and what removing it costs | Risks |

**Highest demand:** mature features with low adoption maturity. The business relies on them most, and their why is least known.

**Outputs:**
- What the feature does, and why.
- Its current state.
- Its risks.
- What could not be explained or verified.

**Constraints:**
- Lifecycle stage and adoption maturity are given, never inferred.
- Does not change the product.
- Does not judge whether a feature is worth keeping. That belongs to [Value](04-value-layer.md).

### 3.5.2 Evaluate

**Aim:** a judgment in business terms, before commitment, of what delivering an intent would take, what it would touch, and what could go wrong.

**Used for:**
- Deciding whether to commit to an intent.
- Comparing intents that compete for the same capacity.

**Expected behavior:**
- The intent is weighed against the product as it really is: the features it touches, and its technical reach and risk.
- An unclear intent is returned with questions, not evaluated on assumptions.
- What delivery would take, the risks, and the unknowns are stated in business terms.
- An evaluation is not a promise. Delivery commits only when the intent is committed.

**Adaptation by adoption maturity:**

| Adoption maturity | Basis for identifying reach | Main risk |
|---|---|---|
| Low | Little feature knowledge; relies mostly on code-level findings | Underestimating what the intent touches |
| High | Feature knowledge maps the intent to the features it touches, confirmed against the code | Overconfidence in a familiar picture |

**Adaptation by lifecycle stage of the features touched:**

| Lifecycle stage | Focus | Unknowns are treated as |
|---|---|---|
| New idea | The cost of testing the hypothesis | Expected |
| In development | The effect on completing the feature | Open points |
| Mature | The risk to behavior users rely on | Risks |
| Retiring | What still depends on it, and the cost of removing it | Risks |

**Highest demand:** an intent that touches mature features with low adoption maturity.

**Outputs:**
- What delivering it would take.
- The features touched, each with its lifecycle stage.
- Risks.
- Unknowns.
- Questions about the intent.

**Constraints:**
- Lifecycle stage and adoption maturity are given, never inferred.
- Does not change the product.
- Does not decide whether to commit. That belongs to [Value](04-value-layer.md).

### 3.5.3 Deliver

**Aim:** the committed intent in users' hands and healthy in production, with evidence that it meets the intent, and the feature knowledge updated to match.

**Used for:**
- New features.
- Changes to existing features.
- Fixes, including urgent ones.
- Debt reduction.
- Retiring features.

**Expected behavior:**
- The intent is turned into acceptance criteria before work starts, so that met is defined in advance.
- The work is broken into pieces, each with its boundary and lifecycle stage.
- Every result is decided on: accepted or sent back.
- Accepted pieces are judged together as a whole before they reach users. Pieces that are each correct can still fail together.
- The release reaches users in a way that can be reversed. Its health is watched after release, and a failed release is restored.
- Delivered means users have it and it works.
- Debt introduced is stated, not hidden.
- Feature knowledge is updated as part of the delivery.

**Adaptation by adoption maturity:**

| Adoption maturity | Basis for acceptance criteria | Main risk |
|---|---|---|
| Low | Little feature knowledge; criteria written from the intent and what is known of the product; smaller releases | Criteria that do not capture the intent |
| High | Rich feature knowledge | Routine releases skipping the check of the whole |

**Adaptation by lifecycle stage:**

| Lifecycle stage | A good delivery means | Evidence emphasis |
|---|---|---|
| New idea | Fast, reversible, possibly to a limited audience | The hypothesis can be tested |
| In development | Moving the feature towards completeness | Acceptance criteria met |
| Mature | No disruption to users | Acceptance criteria met, preserved behavior intact, healthy after release |
| Retiring | Users and dependents moved off cleanly | Nothing left behind, no user disrupted |

**Highest demand:** a delivery touching mature features with low adoption maturity.

**Outputs:**
- The release, delivered and healthy.
- Evidence that it meets the intent.
- Debt introduced.
- Updated feature knowledge.

**Constraints:**
- Lifecycle stage and adoption maturity are given, never inferred.
- Nothing is delivered beyond the committed intent.
- Does not judge whether the right thing was built. That belongs to Validate.

### 3.5.4 Validate

**Aim:** a judgment, backed by evidence, of whether what was delivered serves the intent in the hands of users.

**Used for:**
- Closing a delivery.
- Learning whether the hypothesis behind an intent holds.
- Providing evidence for lifecycle stage decisions.

**Expected behavior:**
- Judged against the intent, not against the acceptance criteria. A release can meet every criterion and still miss the intent.
- Evidence comes from how users actually use the product and how it behaves after release, not from the delivery's own report.
- Takes as long as the intent needs. Some intents can be validated at once; others only after real use.
- Inconclusive is a valid result.
- A failed validation is reported, not repaired.

**Adaptation by adoption maturity:**

| Adoption maturity | Basis for judging | Main risk |
|---|---|---|
| Low | Little knowledge of how users relied on the feature before the release | Mistaking noise for an effect of the release |
| High | Knowledge of how the feature was used before the release | Validation becoming a formality |

**Adaptation by lifecycle stage:**

| Lifecycle stage | Validation asks | An inconclusive result is |
|---|---|---|
| New idea | Did the hypothesis hold? | Learning, reported as such |
| In development | Does the feature serve its intent as it grows? | An open point |
| Mature | Did the change serve its intent without users losing what they relied on? | A risk |
| Retiring | Were users and dependents moved off without loss? | A risk |

**Highest demand:** mature features with low adoption maturity.

**Outputs:**
- A verdict: serves the intent, does not, or inconclusive, with its evidence.
- What was learned.
- Gaps between the intent and what was delivered.

**Constraints:**
- Lifecycle stage and adoption maturity are given, never inferred.
- Does not change the product.
- Does not decide what follows a failed validation.

### 3.5.5 Confirm

**Aim:** a judgment, feature by feature, of whether a claim about the product is supported by the product as it really is.

**Used for:**
- Checking a commitment before it reaches customers.
- Checking claims about lifecycle stage, such as "this feature is mature".
- Keeping what the business says about the product consistent with what the product does.

**Expected behavior:**
- Each claim is broken down into the features it concerns, and each part gets its own verdict: supported, contradicted, or undecidable.
- Judged against the product as it really is, including what has been delivered to whom.
- A contradiction is stated precisely: what the claim says, and what the product does.
- Claims about value, market, or strategy are outside this layer and are reported as such.
- A contradiction is not resolved here. Either the claim is wrong or the product falls short; that decision belongs to [Value](04-value-layer.md#457-steer).

**Adaptation by adoption maturity:**

| Adoption maturity | Basis for judging | Main risk |
|---|---|---|
| Low | Little feature knowledge; many claims undecidable | Confirming from memory or assumption |
| High | Current feature knowledge, checked against the product | Routine confirmation becoming superficial |

**Adaptation by lifecycle stage:**

| Lifecycle stage | Typical claims | A contradiction is |
|---|---|---|
| New idea | What has been learned or proven | An open point |
| In development | Completeness and availability | A risk of committing too early |
| Mature | Reliability, and what customers can depend on | A false commitment |
| Retiring | Claims that still promise the feature | A claim to withdraw |

**Highest demand:** claims about mature features with low adoption maturity, especially commitments to customers.

**Outputs:**
- A verdict per claim, feature by feature, with evidence.
- Each contradiction, described.
- Undecidable claims.
- Claims outside this layer.

**Constraints:**
- Lifecycle stage and adoption maturity are given, never inferred.
- Does not change the product.
- Does not decide whether the claim or the product is wrong.

## 3.6 AI contributions

**Posture:** the AI is an instrument. People decide and own; the AI drafts, analyzes, and challenges for them.

**Principles:**
- **Instrument, not actor.** Work is done by people through the contracts; the AI supports them and never decides. A draft becomes knowledge only when a person confirms it.
- **Shared, not personal.** The same contracts, skills, and conventions apply whoever uses the AI. Personal prompts and habits are not a channel for work in this layer.
- **Autonomy is set by policy.** How much the AI does without human review follows the autonomy policies of the [framework](01-layers.md#173-autonomy) and [this layer](#345-autonomy), not personal preference or tool defaults.
- **Makers and judges are separate.** The AI that helps prepare a delivery and the AI that helps validate or confirm it are different, with separate contexts, and both are independent of the actors in the AI layer.
- **The model holds nothing.** Everything the AI needs and everything it produces exists outside the model. Models are interchangeable, subject to evaluation for each contract.
- **Every contribution leaves a trace:** the contract served, the adaptation parameters, the skill version, the model used, and who confirmed the result.

**Materialization:**

| What | Contents | Where |
|---|---|---|
| Inputs | Skills (how the work is done), conventions (craft rules), Delivery knowledge sources | Repository and documentation systems |
| Outputs of Deliver | Release, evidence, updated feature knowledge | Specs in the repository; business knowledge in the documentation systems |
| Outputs of Explain, Evaluate, Validate, Confirm | Explanations, evaluations, verdicts | Returned to Value through the contract |
| Trace | Contract, adaptation parameters, skill version, model, confirmation | With the output |

## 3.7 Role contributions

### 3.7.1 Agentic Engineer

Delivery is where the Agentic Engineer and the Product Manager meet. The [Agentic Engineer](roles/08-agentic-engineer.md) turns intent into technical delivery and is accountable for it reaching users.

- **Specs and acceptance criteria.** Every committed intent becomes specs and acceptance criteria that make it checkable. Criteria that do not capture the intent are a failure of the translation.
- **Delivery to users.** The Agentic Engineer owns the release until it is in users' hands and healthy, including restoring a failed release.
- **Decisions on results.** Every result from the AI layer is accepted or sent back by the Agentic Engineer.
- **Technical half of feature knowledge.** Specs and the mapping from business terms to technical parts.
- **Debt.** Debt introduced by a delivery is reported, never hidden.

### 3.7.2 Product Manager

The [Product Manager](roles/07-product-manager.md) brings the business into Delivery and is accountable for what is delivered serving the intent.

- **Intent quality.** Every intent states what is wanted and why. Questions about the intent are answered by the Product Manager.
- **Acceptance criteria.** The Product Manager confirms that the acceptance criteria capture the intent before delivery starts.
- **Business half of feature knowledge.** Intents and the business why.
- **Validation.** Validation results are written with the Agentic Engineer, with one named owner.

### 3.7.3 AI Enablement Lead

The [AI Enablement Lead](roles/09-ai-enablement-lead.md) keeps the layer fit for the products and does not use it for product work.

- **Definition of the layer.** Contracts, behaviors, policies, and shared skills and conventions. Changes to them are deliberate and known to the people who rely on them.
- **Independence.** What prepares a delivery and what validates or confirms it stay separate, in practice and not only on paper.
- **Models.** Which model supports which contract is decided from evaluations on the organization's own products.
- **Alignment with the products.** The layer's adaptation reflects the real lifecycle stages and adoption maturity of each product.
- **Outcomes and change.** The layer changes based on its outcomes, not on opinion. Where its use is disputed, the AI Enablement Lead's interpretation applies.

## 3.8 Outcomes

### 3.8.1 Understanding
- **Explanations that hold.** What Explain said about a feature is borne out by the product and its use.
- **Features become known.** Feature knowledge grows where intents are delivered, and adoption maturity rises with it.
- **Evaluations that match reality.** What Evaluate predicted a delivery would take and touch is what it actually took and touched.

### 3.8.2 Delivering
- **Intents delivered.** Committed intents reach users and run healthy.
- **Releases that hold.** Few releases are restored or followed by incidents.
- **Little rework.** Acceptance criteria capture the intent the first time.
- **Validated intents.** Deliveries serve their intents in the hands of users.

### 3.8.3 Honesty
- **Claims that hold.** False commitments are caught by Confirm before customers find them.
- **Debt that is visible.** Debt is reported when introduced, not discovered later.
- **Stops that were needed.** The questions the layer raised were real gaps, not noise.

### 3.8.4 What matters by lifecycle stage
- **New idea:** hypotheses tested quickly, learning reported. Rework is acceptable.
- **In development:** little rework, validated intents.
- **Mature:** releases that hold, claims that hold. Speed comes second.
- **Retiring:** users and dependents moved off cleanly, claims withdrawn. Speed comes second.

### 3.8.5 What matters by adoption maturity
- **Low:** features become known, explanations that hold. Stops are frequent and expected; releases are smaller.
- **High:** releases that hold, little rework, evaluations that match reality.
