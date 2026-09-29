# Checkout Requirements Review

## Project
Training E-commerce Application

## Feature
Checkout

## Objective
Identify ambiguities, omissions, testability issues, and other anomalies
in checkout requirements before implementation.

## Scope
Requirements REQ-CHK-01 to REQ-CHK-06.

## Review Findings

| ID | Requirement | Finding / Anomaly | Question / Recommendation | Category | Status |
|---|---|---|---|---|---|
| REV-001 | REQ-CHK-01: User can proceed to checkout if there is at least one product in the cart. | The requirement does not specify whether checkout is available to guest users, logged-in users, or both. | Clarify which user types are allowed to proceed to checkout. | Omission | Open |
| REV-002 | REQ-CHK-02: User must provide valid personal data. | The term "valid personal data" is not defined. | Specify mandatory fields and validation rules for each field. | Ambiguity | Open |
| REV-003 | REQ-CHK-03: Delivery should be selected automatically. | The rule used to select the delivery method is not defined. | Clarify how the delivery method is selected and whether the user can change it. | Ambiguity | Open |
| REV-004 | REQ-CHK-04: The order should be processed quickly. | The word "quickly" does not provide a measurable acceptance criterion. | Define the maximum acceptable order processing time. | Testability | Open |
| REV-005 | REQ-CHK-05: User receives purchase confirmation. | The required confirmation channel and content are not specified. | Clarify whether confirmation is shown on screen, sent by email, or both, and define the required information. | Omission | Open |
| REV-006 | REQ-CHK-06: If payment fails, the user should be able to try again. | The requirement does not specify how the user is informed about the failed payment. | Define the expected error message or notification after payment failure. | Omission | Open |
| REV-007 | REQ-CHK-06: If payment fails, the user should be able to try again. | The allowed number of payment retries is not specified. | Clarify whether there is a retry limit and what happens after the limit is reached. | Omission | Open |
| REV-008 | REQ-CHK-06: If payment fails, the user should be able to try again. | The state of the order and cart after payment failure is not defined. | Clarify whether the cart contents are preserved and what status the order receives after payment failure. | Omission | Open |

## Summary

- Requirements reviewed: 6
- Findings identified: 8
- Main finding categories:
  - Ambiguity
  - Omission
  - Testability

## Key Observation

Several requirements describe expected behavior using vague or incomplete wording.
Clarifying these points before implementation would make the requirements easier
to understand, implement, and test.

## Project Note

This is a training QA portfolio project created for learning and demonstrating
software testing skills. It does not represent commercial project experience.