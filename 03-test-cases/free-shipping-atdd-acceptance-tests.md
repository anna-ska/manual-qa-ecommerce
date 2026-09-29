# Free Shipping — ATDD-style Acceptance Tests

## Project
Training E-commerce Application

## Feature
Checkout / Shipping

## User Story

As a customer,
I want free shipping for sufficiently large orders,
so that I can reduce delivery costs.

## Acceptance Criteria

### AC1 — REQ-FS-01
Cart subtotal equal to or greater than 300.00 PLN results in a shipping fee of 0.00 PLN.

### AC2 — REQ-FS-02
Cart subtotal below 300.00 PLN results in a standard shipping fee of 20.00 PLN.

### AC3 — REQ-FS-03
The shipping fee is displayed before the customer confirms the order.

## Acceptance Criteria Format

The criteria above are written primarily in a rule-oriented format.

## ATDD-style Test Cases

| ID | Requirement | Acceptance Criterion | Preconditions | Test Data | Action | Expected Result |
|---|---|---|---|---|---|---|
| ATDD-01 | REQ-FS-01 | AC1 | Cart contains products | Cart subtotal = 300.00 PLN | Open checkout | Shipping fee is displayed as 0.00 PLN. |
| ATDD-02 | REQ-FS-02 | AC2 | Cart contains products | Cart subtotal = 299.99 PLN | Open checkout | Shipping fee is displayed as 20.00 PLN. |
| ATDD-03 | REQ-FS-01 | AC1 | Cart contains products | Cart subtotal = 350.00 PLN | Open checkout | Shipping fee is displayed as 0.00 PLN. |
| ATDD-04 | REQ-FS-03 | AC3 | Checkout is open and the order has not yet been confirmed | Cart subtotal = 300.00 PLN | Observe the shipping fee before confirming the order | The shipping fee is visible before order confirmation. For this test data, the displayed fee is 0.00 PLN. |

## Scenario-Oriented Example

### Scenario: Free shipping at the threshold

Given the cart subtotal is 300.00 PLN  
When the customer opens checkout  
Then the shipping fee is 0.00 PLN

## Traceability

| Requirement | Acceptance Criterion | Covered By |
|---|---|---|
| REQ-FS-01 | AC1 | ATDD-01, ATDD-03 |
| REQ-FS-02 | AC2 | ATDD-02 |
| REQ-FS-03 | AC3 | ATDD-04 |

## Test Data Rationale

- 299.99 PLN is immediately below the free-shipping threshold.
- 300.00 PLN is the threshold value.
- 350.00 PLN is an additional representative value above the threshold.

The values around 300 PLN illustrate how boundary-focused test data can be used while deriving ATDD-style tests from acceptance criteria.

## Notes

The acceptance tests were derived directly from the stated acceptance criteria before implementation, following a training ATDD-style approach.

No behavior outside the stated user story and acceptance criteria was assumed.

## Project Note

This is a training QA portfolio artifact.
It does not represent commercial project experience.
