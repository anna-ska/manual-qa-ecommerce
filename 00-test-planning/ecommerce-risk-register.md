# E-commerce Testing — Risk Register

## Project

Training E-commerce Application

## Purpose

Identify and assess project and product risks that may influence the scope,
priority, thoroughness, and execution of testing.

## Risk Assessment Method

This training project uses a simple ordinal scoring model for prioritization.

### Likelihood Rating

- 1 = Low
- 2 = Medium
- 3 = High

### Impact Rating

- 1 = Low
- 2 = Medium
- 3 = High

### Risk Score

Risk Score = Likelihood Rating × Impact Rating

- 1–2 = Low
- 3–4 = Medium
- 6–9 = High

> The 1–3 ratings and score thresholds are training conventions used for this portfolio.
> They are not measured probabilities. This is not a mandatory ISTQB risk scale.

## Assessment Basis

The ratings below are training assessments based on the available project
information and stated assumptions. They do not represent production data.

## Product Risks

| ID | Risk | Likelihood | Impact | Score | Level | Test Response | Status |
|---|---|---:|---:|---:|---|---|---|
| PR-01 | Free shipping may be calculated incorrectly around the 300.00 PLN threshold. | 2 | 3 | 6 | High | Prioritize early; apply Boundary Value Analysis around 300.00 PLN; increase boundary coverage. | Open |
| PR-02 | An invalid coupon may be accepted or handled incorrectly. | 2 | 2 | 4 | Medium | Apply Decision Table Testing to coupon rules and prioritize invalid-coupon scenarios. | Open |
| PR-03 | Cart quantity validation may accept values outside the allowed range. | 2 | 2 | 4 | Medium | Apply Equivalence Partitioning and Boundary Value Analysis to the allowed quantity range, including invalid and boundary values. | Open |
| PR-04 | Cart information may become inconsistent after products are added or removed. | 2 | 2 | 4 | Medium | Prioritize add/remove sequences; use checklist-based and exploratory testing; include relevant regression testing after changes. | Open |
| PR-05 | Checkout response time may be unacceptable. | 2 | 2 | 4 | Medium | Review the need for measurable response-time criteria and targeted performance testing; if performance testing remains out of scope, document the residual risk. | Open |

## Product Risk Assessment Notes

- PR-01 is rated High because an incorrect shipping fee directly affects the
  order total and customer cost at a defined business threshold.
- PR-02 is rated Medium because incorrect coupon handling may affect discounts
  and the final order value.
- PR-03 is rated Medium because invalid quantity handling may result in an
  incorrect cart state or order data.
- PR-04 is rated Medium because inconsistent cart information may affect later
  checkout behavior.
- PR-05 is rated Medium because slow checkout may negatively affect the user
  experience, but no production evidence is available to justify a higher
  likelihood or impact rating in this training project.

## Project Risks

| ID | Risk | Likelihood | Impact | Score | Level | Response | Status |
|---|---|---:|---:|---:|---|---|---|
| PJ-01 | Testing may be delayed or reduced because only one tester is available. | 2 | 2 | 4 | Medium | Prioritize high-risk testing, estimate and monitor remaining effort, and defer lower-risk work if necessary. | Open |
| PJ-02 | The planned test scope may not be completed within five working days. | 2 | 3 | 6 | High | Use risk-based prioritization, monitor progress, and reduce or defer lower-risk testing if necessary; document any remaining coverage gaps. | Open |
| PJ-03 | Dynamic test execution may be blocked because an executable demo environment is unavailable. | 2 | 3 | 6 | High | Verify environment availability early; continue static and design activities while blocked; record blocked tests and resulting coverage gaps. | Open |

## Project Risk Assessment Notes

- PJ-01 is rated Medium because one tester creates a capacity constraint, but
  the project scope is limited and can be prioritized.
- PJ-02 is rated High because a fixed five-day window may prevent completion of
  the planned scope if effort is greater than expected.
- PJ-03 is rated High because unavailable executable functionality can block
  dynamic testing completely for affected features.

## Testing Impact

Product risk analysis may influence:

- test scope
- test priority
- test techniques
- test types
- coverage
- test effort
- additional risk-reduction activities

High-risk areas should receive earlier and/or more thorough testing where this
is practical and justified by the available information.

## Risk Monitoring

Risks should be reviewed during testing.

Changes in likelihood, impact, mitigation effectiveness, and newly identified
risks should be recorded when relevant.

If new evidence becomes available, the ratings, responses, and status should be
updated rather than treated as fixed values.

## Project Note

This is a training QA portfolio artifact.

The likelihood and impact ratings are training assessments and do not represent
production data or commercial project experience.

