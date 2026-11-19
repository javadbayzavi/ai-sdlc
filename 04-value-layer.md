# Chapter 4: Value Layer

## 4.1 Purpose

The Value layer decides what is worth building for the product over its lifecycle, and judges whether what is delivered creates that value.

Worth building has two sides:
- **Customer value:** how the product helps customers with their jobs, relieves their pains, and creates gains for them.
- **Business value:** what the product returns to the business against what it costs and risks.

## 4.2 Contracts

Value uses the [contracts of the Delivery layer](03-delivery-layer.md#32-contracts) as defined there, and owns no contracts of its own.

## 4.3 Knowledge sources

### 4.3.1 Sources
- **Company strategy and goals:** the frame for what is worth building.
- **Peer plans:** other products and shared platforms; what they need from us and what we depend on.
- **Customer evidence:** interviews, feedback, requests, and observed behavior, showing customers' jobs, pains, and gains.
- **Market:** competitors, alternatives, and trends.
- **Business data:** revenue, cost, pricing, contracts, and the customer base.
- **Sales and support signals:** why deals are won or lost, and recurring patterns in what customers need help with.
- **Initiatives and decisions:** what each initiative expected, what was decided and why, and what Measure concluded.
- **The roadmap and outward commitments.**
- **What Delivery returns through [its contracts](03-delivery-layer.md#32-contracts):** explanations, evaluations, validations, confirmations, and reports of feature state and risk.

### 4.3.2 Where knowledge lives
- In the documentation and ticketing systems, linked to Delivery's business records.
- Every item carries its source, its reach (how many customers it represents), its date, and its confidence.

### 4.3.3 Precedence
- Sources of truth are defined in [the Layers chapter (1.4.2)](01-layers.md#142-sources-of-truth). For this layer, Value decisions are the truth for why the product is worth building.
- What customers do outweighs what they say, and both outweigh internal opinion.
- Figures from their systems of record outweigh estimates.
- Recent evidence outweighs old evidence.

## 4.4 Policies

The [principles (1.7)](01-layers.md#17-principles) and [framework policies (1.8)](01-layers.md#18-framework-policies) apply. This layer adds:

### 4.4.1 Alignment
- Every initiative traces to the company strategy. Pursuing one that does not is an explicit decision, recorded with its reasoning. ([1.7.1](01-layers.md#171-accountability))
- Product reality reaches this layer only through Delivery's contracts. ([1.7.5](01-layers.md#175-given-context))

### 4.4.2 Commitments
- Nothing is promised outward, to customers or peer plans, before what it would take is known and the claim is confirmed against the product. ([1.7.3](01-layers.md#173-honesty))
- An outward commitment that no longer holds is withdrawn or corrected, never left to expire silently. ([1.7.3](01-layers.md#173-honesty))

### 4.4.3 Independence
- The value of an initiative is not judged solely by whoever shaped it. ([1.7.2](01-layers.md#172-independence))

### 4.4.4 Reporting
- The layer reports to the company how the product contributes to the strategy, and tells peer plans what they can rely on. ([1.7.1](01-layers.md#171-accountability))

### 4.4.5 Data and security
- Customer evidence, tickets, and business data are cleaned of personal data before they enter any AI context. ([1.8.4](01-layers.md#184-data-protection))

### 4.4.6 Autonomy
- The AI never decides in this layer. A draft becomes knowledge or a decision only when its owner confirms it. ([1.7.1](01-layers.md#171-accountability))
- Nothing goes out to customers or outside the team on the AI's own initiative: no launch material, claims, or commitments. ([1.7.1](01-layers.md#171-accountability))

## 4.5 Behavior

### 4.5.1 Discover

**Aim:** an understanding, from outside the product, of where value lies: customers' jobs, pains, and gains, and what the business and its strategy need.

**Used for:**
- Finding opportunities.
- Understanding why a feature is or is not valued.
- Grounding initiatives in evidence before they are shaped.

**Expected behavior:**
- Evidence over opinion. What customers do outweighs what they say, and both outweigh internal assumption.
- Both sides of value are covered: customer and business.
- It stays within the frame of company strategy and peer plans.
- Problems are kept apart from proposed solutions. A customer request is evidence of a job or a pain, not a specification.
- The loudest customer is not the market. Signals are weighed by how widely they hold.
- Uncertainty is stated.

**Adaptation by adoption maturity:**

| Adoption maturity | Basis of understanding | Main risk |
|---|---|---|
| Low | Scattered signals and anecdotes; little recorded understanding of customers or business value | Mistaking anecdotes for patterns |
| High | Established knowledge of customers' jobs, pains, and gains | Confirming what is already believed |

**Adaptation by lifecycle stage:**

| Lifecycle stage | Discover asks | Unknowns are treated as |
|---|---|---|
| New idea | Is there a real job, pain, or gain worth addressing? | Expected |
| In development | Are we learning what customers need as it grows? | Open points |
| Mature | Is the value still there, or are needs and alternatives shifting? | Risks |
| Retiring | Who still depends on it, and what would they lose? | Risks |

**Highest demand:** mature features with low adoption maturity. The business relies on them, while the understanding of why customers value them is thin.

**Outputs:**
- Opportunities, with their evidence.
- Customers' jobs, pains, and gains as understood.
- Business needs.
- What remains unknown.

**Constraints:**
- Does not decide what to build. That belongs to Prioritize and Commit.
- Makes no commitments outward.

### 4.5.2 Shape

**Aim:** an initiative clear enough to be weighed, delivered, and judged: what would be done, for whom, the value expected on both sides, how we would know it worked, when to stop, and which lifecycle stage it concerns.

**Used for:**
- Turning an opportunity into something that can be prioritized.
- Making an intent clear before it reaches Delivery.
- Making value measurable later.

**Expected behavior:**
- Every initiative states the customer value and the business value it expects.
- Every initiative states how success would be recognized and what evidence would stop it, decided before it starts, not after.
- An initiative describes the problem and the value, not the solution. How belongs to [Delivery](03-delivery-layer.md).
- Assumptions are named as assumptions.
- The size of an initiative matches its uncertainty: the less is known, the smaller the initiative.

**Adaptation by adoption maturity:**

| Adoption maturity | Basis for expected value | Main risk |
|---|---|---|
| Low | Few reliable measures of value; initiatives rely on proxies | Initiatives that cannot be measured later |
| High | Established measures of value | Shaping initiatives to fit existing measures rather than real value |

**Adaptation by lifecycle stage:**

| Lifecycle stage | An initiative is about | Success means |
|---|---|---|
| New idea | Learning | The hypothesis is answered, either way |
| In development | Completeness and adoption | Customers adopt it as expected |
| Mature | Keeping or improving value against cost | Value maintained, cost contained |
| Retiring | Stopping with the least loss | Customers moved off, cost removed |

**Highest demand:** initiatives on mature features with low adoption maturity, where expected value is hardest to state honestly.

**Outputs:**
- The initiative: problem, customers, expected customer and business value, evidence of success, stop condition, lifecycle stage, and assumptions.

**Constraints:**
- Does not decide whether to pursue it. That belongs to Prioritize.
- Does not design the solution. That belongs to [Delivery](03-delivery-layer.md).

### 4.5.3 Prioritize

**Aim:** an ordered choice among initiatives within strategy and capacity: what to pursue, what to keep, and what to drop, laid out over time as the roadmap.

**Used for:**
- Choosing among competing initiatives.
- Balancing new ideas, features in development, upkeep of mature features, and debt.
- Producing and revising the roadmap.
- Deciding on reported debt.

**Expected behavior:**
- Initiatives are weighed against each other, never one at a time.
- They are weighed against strategy, capacity, and expected value on both sides, including the cost of keeping mature features alive.
- What an initiative would take is known before it is placed.
- Reported debt receives an explicit decision: pay it, accept it, or defer it. The decision is recorded.
- The roadmap is a plan, not a commitment. Its items are uncommitted initiatives and can be revised.
- Every lifecycle stage has its place. New ideas do not crowd out upkeep or retirement.

**Adaptation by adoption maturity:**

| Adoption maturity | Basis for weighing | Main risk |
|---|---|---|
| Low | Little reliable evidence of value or cost | Priorities set by the loudest voice or the latest request |
| High | Established evidence of value and cost | Inertia: favoring what is already measured over what is new |

**Adaptation by lifecycle stage:**

| Lifecycle stage | Weighed by |
|---|---|
| New idea | Cost of learning, time-boxed |
| In development | Progress towards adoption against remaining cost |
| Mature | Value against cost of upkeep |
| Retiring | Cost of continuing against cost of stopping |

**Highest demand:** mature features with low adoption maturity competing with new ideas, where upkeep is most easily neglected or a declining feature kept alive too long.

**Outputs:**
- Initiatives in order.
- Decisions on reported debt.
- The roadmap, with each initiative's expected lifecycle path, the evidence expected, and when to revisit it.

**Constraints:**
- Does not commit. That belongs to Commit.
- Roadmap items are not promises.

### 4.5.4 Commit

**Aim:** a decision turned into a binding commitment: an initiative handed to Delivery as an intent and, where deliberate, a promise made outward to customers or peer plans.

**Used for:**
- Starting delivery of an initiative.
- Standing intents, such as capacity committed to debt reduction.
- Commitments to customers or peer plans.
- Changing a committed intent, which is a new commitment.

**Expected behavior:**
- Only shaped and prioritized initiatives are committed.
- The intent handed over states what is wanted and why, without the solution. Expected value and stop conditions stay with Value.
- Outward promises are deliberate. They are made only after what it would take is known and the claim is checked against the product.
- A change to a committed intent is a new commitment, never a silent change.
- A standing intent has an explicit scope and capacity.

**Adaptation by adoption maturity:**

| Adoption maturity | What the intent carries | Main risk |
|---|---|---|
| Low | Little context | Intents returned as unclear; promises made on assumption |
| High | Rich context | Committing by habit; treating the roadmap as committed |

**Adaptation by lifecycle stage:**

| Lifecycle stage | Commitment means | Outward promises |
|---|---|---|
| New idea | Small and time-boxed | Avoided |
| In development | Steps towards completeness | Made only with care |
| Mature | A change, with the behavior to preserve stated | Reflect what customers rely on |
| Retiring | Removal and moving customers off | Withdrawn |

**Highest demand:** committing changes to mature features with low adoption maturity, where outward promises are most tempting and least supported.

**Outputs:**
- The committed intent.
- Outward commitments, with their basis.
- A record of what was committed and why.

**Constraints:**
- Does not deliver.
- Does not commit what was not prioritized.
- Outward commitments are never made from the roadmap alone.

### 4.5.5 Realize

**Aim:** delivered change turned into value customers actually get and the business actually captures, with everything said about the product outward kept true.

**Used for:**
- Launching delivered change.
- Enabling customers, sales, and support, including demos and self-support material.
- Packaging and pricing, where affected.
- Keeping outward claims true: marketing, sales promises, roadmap commitments, and support content.
- Moving customers off retiring features.

**Expected behavior:**
- Value is not assumed from availability. Customers must know about the change, understand it, and be able to use it.
- Those who sell and support the product are ready before customers arrive.
- Customers can help themselves; self-support material reflects the product as it is.
- Outward claims are kept true. Stale claims are corrected or withdrawn.
- What stands in the way of adoption is identified and fed back.
- Realize makes sure what is needed exists. Producing it, such as a demo environment or help content, may be delivered as an intent.

**Adaptation by adoption maturity:**

| Adoption maturity | Basis | Main risk |
|---|---|---|
| Low | Little established launch and support practice; outward claims scattered and unchecked | Value lost to customers who never find or understand the change; stale claims |
| High | Established channels and checked claims | Routine launches that miss the customers who matter |

**Adaptation by lifecycle stage:**

| Lifecycle stage | Realization means |
|---|---|
| New idea | A limited audience, enough to learn from |
| In development | A widening audience, with enablement growing as the feature matures |
| Mature | Changes communicated without disrupting what customers rely on; claims kept true |
| Retiring | Customers informed, moved off, and supported through the change; claims withdrawn |

**Highest demand:** changes to mature features with low adoption maturity, where many customers rely on the feature and outward claims about it are many and least checked.

**Outputs:**
- Launch and enablement in place.
- Outward claims updated or withdrawn.
- Obstacles to adoption, identified.
- For retiring features, customers moved off.

**Constraints:**
- Does not change the product.
- Does not judge whether value was created. That belongs to Measure.
- Makes no new commitments. That belongs to Commit.

### 4.5.6 Measure

**Aim:** a judgment, against what the initiative expected, of whether value was created for customers and for the business.

**Used for:**
- Closing the loop on an initiative.
- Evidence for lifecycle stage decisions.
- Testing whether the assumptions behind the roadmap held.

**Expected behavior:**
- Judged against the expectations set when the initiative was shaped, not new ones chosen afterwards.
- Both sides of value are measured: customer and business.
- Early signals are read as early signals. The final judgment waits for value to show, and is revisited when that evidence arrives.
- A shortfall is traced to where it lies: the idea, customers never reached, or a delivery that missed the intent.
- Other causes are considered before value is credited to an initiative.
- Inconclusive is a valid result.

**Adaptation by adoption maturity:**

| Adoption maturity | Basis for judging | Main risk |
|---|---|---|
| Low | Few reliable measures; relies on proxies | False conclusions |
| High | Established measures | Measuring what is easy instead of what matters |

**Adaptation by lifecycle stage:**

| Lifecycle stage | Measure asks | An inconclusive result is |
|---|---|---|
| New idea | Was the hypothesis answered? | Learning, reported as such |
| In development | Is adoption growing as expected? | An open point |
| Mature | Does value still exceed cost? | A risk |
| Retiring | Was cost removed without more loss of value than expected? | A risk |

**Highest demand:** mature features with low adoption maturity, where most revenue is at stake and measures are weakest.

**Outputs:**
- A verdict per initiative on both sides of value: created, not created, or inconclusive, with its evidence.
- Where any shortfall lies: idea, realization, or delivery.
- What was learned.

**Constraints:**
- Does not act on the result. That belongs to Steer.
- Never changes expectations after the fact.

### 4.5.7 Steer

**Aim:** the product's direction adjusted to what has been learned: lifecycle stages changed; initiatives continued, adjusted, stopped, or retired; the roadmap revised.

**Used for:**
- Acting on Measure's verdicts.
- Acting on reports of feature state, debt, and risk.
- Responding to changes in company strategy or peer plans.
- Changing lifecycle stages.

**Expected behavior:**
- Decisions follow evidence. Stage changes require evidence, not intuition.
- Stop conditions are honoured. When the evidence set at shaping says stop, the initiative stops, unless a recorded decision says otherwise.
- Sunk cost does not justify continuing.
- Every decision is recorded with its reasoning.
- The roadmap is revised when evidence contradicts it, and outward commitments affected are revisited.
- Retirement is a deliberate decision, not neglect.

**Adaptation by adoption maturity:**

| Adoption maturity | Basis for decisions | Main risk |
|---|---|---|
| Low | Thin evidence | Steering by opinion or inertia |
| High | Established evidence | Over-steering on early signals |

**Adaptation by lifecycle stage:**

| Lifecycle stage | Typical decisions |
|---|---|
| New idea | Continue, change direction, or stop learning; move to in development if the hypothesis holds |
| In development | Continue, adjust, or stop; move to mature when maturity criteria are met |
| Mature | Maintain, reinvest, or begin retiring |
| Retiring | Complete retirement, or reverse it if value reappears |

**Highest demand:** mature features with low adoption maturity, where decisions to change or retire core features rest on the weakest evidence.

**Outputs:**
- Decisions on stage changes and on continuing, adjusting, stopping, or retiring, each with its reasoning.
- The revised roadmap.
- Commitments to revisit.

**Constraints:**
- Does not create work directly. New direction goes through Shape, Prioritize, and Commit.
- Never rewrites past expectations.

## 4.6 AI contributions

**Posture:** the AI is an instrument. People decide and own; the AI gathers, drafts, analyzes, and challenges for them.

**Materialization:**

| What | Contents | Where |
|---|---|---|
| Inputs | Skills (how the work is done), conventions (craft rules), Value knowledge sources | Documentation and ticketing systems |
| Outputs of Shape, Prioritize, Commit, Steer | Initiatives, roadmap, committed intents, decisions | Documentation and ticketing systems |
| Outputs of Discover, Measure | Opportunities, verdicts, learning | Documentation systems |
| Outputs of Realize | Launch and enablement material, outward claims | Where customers, and those who sell and support the product, find them |
| Trace | Behavior, adaptation parameters, skill version, model, confirmation | With the output |

## 4.7 Role contributions

### 4.7.1 Product Manager

The [Product Manager](roles/07-product-manager.md) runs the Value layer and is accountable for the value of the product.

- **Initiatives.** Every initiative states the value it expects on both sides, how success will be recognized, and when it stops.
- **Priorities and roadmap.** What is pursued, kept, and dropped, and how the roadmap reflects it.
- **Commitments.** What is committed to Delivery and what is promised outward, each on its stated basis.
- **Realization.** Delivered change reaches customers as value, and every outward claim stays true.
- **Decisions on evidence.** Stage changes, stopping, retiring, and decisions on reported debt, each recorded with its reasoning.
- **Reporting.** The company knows how the product contributes to the strategy, and peer plans know what they can rely on.

### 4.7.2 Agentic Engineer

No role in this layer.

### 4.7.3 AI Enablement Lead

The [AI Enablement Lead](roles/09-ai-enablement-lead.md) keeps the layer fit for the products and does not use it for product work.

- **Definition of the layer.** Behaviors, policies, and shared skills and conventions. Changes to them are deliberate and known to the people who rely on them.
- **Independence.** What shapes an initiative and what measures it stay separate, in practice and not only on paper.
- **Models.** Which model supports which behavior is decided from evaluations on the organization's own products.
- **Alignment with the products.** The layer's adaptation reflects the real lifecycle stage of each area and the real adoption maturity of each element.
- **Outcomes and change.** The layer changes based on its outcomes, not on opinion. Where its use is disputed, the AI Enablement Lead's interpretation applies.

## 4.8 Outcomes

### 4.8.1 Understanding
- **Opportunities that prove real.** What Discover found turns out to matter to customers and the business.
- **Customers become known.** Understanding of customers' jobs, pains, and gains grows where the product is worked on, and adoption maturity rises with it.
- **Expectations that match reality.** What initiatives expected is close to what Measure finds.

### 4.8.2 Value
- **Value realized.** Delivered change is adopted, and its value shows for customers and the business.
- **Strategy served.** Initiatives trace to the strategy, and the product's contribution is visible to the company.
- **Initiatives stopped on time.** Stop conditions are honoured; little is spent on initiatives the evidence had already rejected.
- **Features retired deliberately.** Features that no longer earn their keep are retired by decision, not left to decay.

### 4.8.3 Honesty
- **Commitments that hold.** Outward promises are kept, or withdrawn openly; none are broken silently.
- **Claims that are true.** What is said about the product outward matches what it does.
- **Decisions with reasons.** Every major decision can be traced to its evidence.

### 4.8.4 What matters by lifecycle stage
- **New idea:** hypotheses answered quickly and cheaply, opportunities that prove real. Stopping is a success when the evidence says so.
- **In development:** adoption growing as expected, expectations that match reality.
- **Mature:** value that still exceeds cost, commitments that hold.
- **Retiring:** customers moved off with the least loss, cost removed, claims withdrawn.

### 4.8.5 What matters by adoption maturity
- **Low:** customers become known, claims that are true. Evidence is thin; initiatives are smaller and revisited more often.
- **High:** expectations that match reality, initiatives stopped on time, value realized.
