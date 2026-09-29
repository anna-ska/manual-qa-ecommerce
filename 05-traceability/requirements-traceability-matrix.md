# Requirements Traceability Matrix

## Project

Training E-commerce Application

## Purpose

This matrix links the training requirements to related risks, requirements-review findings, test design artifacts, test cases, execution status, and defects where applicable.

The matrix reflects the current state of this repository.

It does not claim dynamic test execution where no executable application was available.

---

## Traceability Matrix

| Requirement ID | Requirement / Area | Related Risk | Review Finding | Test Design / Test Cases | Execution Status | Defect | Traceability Status |
|---|---|---|---|---|---|---|---|
| REQ-CART-01 | Product quantity: integers 1–10 inclusive | PR-03 | — | EP-01 to EP-03; BVA2-01 to BVA2-04; BVA3-01 to BVA3-06 | Design completed; Not Run | — | Covered by test design |
| REQ-CHK-01 | Checkout available with at least one cart product | — | REV-001 | — | Static review completed; dynamic test not designed | — | Review coverage only |
| REQ-CHK-02 | User provides valid personal data | — | REV-002 | — | Static review completed; dynamic test not designed | — | Review coverage only |
| REQ-CHK-03 | Delivery selected automatically | — | REV-003 | — | Static review completed; dynamic test not designed | — | Review coverage only |
| REQ-CHK-04 | Order processed quickly | PR-05 | REV-004 | — | Static review completed; measurable criterion unresolved | — | Review coverage only |
| REQ-CHK-05 | User receives purchase confirmation | — | REV-005 | — | Static review completed; dynamic test not designed | — | Review coverage only |
| REQ-CHK-06 | User can retry after payment failure | — | REV-006, REV-007, REV-008 | ST-01 to ST-06; transitions T1 to T4 | Design completed; Not Run | — | Covered by state transition design using explicit training assumptions |
| REQ-CPN-01 | Coupon is optional | — | — | DT-01 / R1 | Design completed; Not Run | — | Covered by decision table |
| REQ-CPN-02 | Invalid coupon shows an error | PR-02 | — | DT-02 / R2 | Design completed; Not Run | — | Covered by decision table |
| REQ-CPN-03 | Valid coupon gives 15% discount at cart total ≥ 100.00 PLN | — | — | DT-04 / R4 | Design completed; Not Run | — | Covered by decision table |
| REQ-CPN-04 | Valid coupon below 100.00 PLN shows minimum cart value message | — | — | DT-03 / R3 | Design completed; Not Run | — | Covered by decision table |
| REQ-FS-01 | Cart subtotal ≥ 300.00 PLN gives 0.00 PLN shipping | PR-01 | — | AC1; ATDD-01, ATDD-03 | Design completed; Not Run | BUG-TR-001 (simulated) | Covered by acceptance test design |
| REQ-FS-02 | Cart subtotal < 300.00 PLN gives 20.00 PLN shipping | PR-01 | — | AC2; ATDD-02 | Design completed; Not Run | — | Covered by acceptance test design |
| REQ-FS-03 | Shipping fee visible before order confirmation | — | — | AC3; ATDD-04 | Design completed; Not Run | — | Covered by acceptance test design |

---

## Artifact References

| Artifact Type | Repository File |
|---|---|
| Test basis | `00-test-planning/ecommerce-requirements.md` |
| Risk analysis | `00-test-planning/ecommerce-risk-register.md` |
| Requirements review | `01-requirements-review/checkout-requirements-review.md` |
| EP / BVA design | `02-test-analysis-design/cart-quantity-ep-bva.md` |
| Decision table design | `02-test-analysis-design/checkout-coupon-decision-table.md` |
| State transition design | `02-test-analysis-design/checkout-payment-retry-state-transition.md` |
| Experience-based checklist | `02-test-analysis-design/checkout-experience-based-checklist.md` |
| ATDD-style acceptance tests | `03-test-cases/free-shipping-atdd-acceptance-tests.md` |
| Simulated defect report | `04-defect-reports/free-shipping-simulated-defect.md` |

---

## Risk-to-Test Notes

Not every product risk maps directly to a formal requirement in the current training test basis.

- **PR-01** is linked to REQ-FS-01 and REQ-FS-02 and is addressed through boundary-focused free-shipping acceptance tests.
- **PR-02** is linked directly to REQ-CPN-02 and is addressed through decision-table scenario DT-02.
- **PR-03** is linked to REQ-CART-01 and is addressed through Equivalence Partitioning and Boundary Value Analysis.
- **PR-04** concerns cart-state consistency. It is addressed by experience-based checklist items CHK-01, CHK-02, CHK-03, and CHK-08, but no dedicated formal requirement currently defines that behavior.
- **PR-05** is linked to REQ-CHK-04. The requirement remains non-measurable, as documented in REV-004, so meaningful performance verification cannot yet be derived from the current test basis.

---

## Coverage Summary

- Total requirements in the current test basis: **14**
- Requirements with specification-based or acceptance test design: **9**
- Requirements with requirements-review coverage only: **5**
- Requirement with both review coverage and state transition design: **1** (`REQ-CHK-06`)
- Requirements with recorded dynamic execution results: **0**
- Real defects found during execution: **0**
- Simulated defect reports: **1**

The absence of dynamic execution results is intentional and consistent with the training-project limitations documented in the repository.

---

## Traceability Limitations

This matrix demonstrates traceability within a training portfolio.

It should not be interpreted as evidence that all requirements were dynamically tested.

Where requirements are ambiguous, incomplete, or non-testable, the matrix retains that limitation instead of inventing missing expected behavior.

Execution results, confirmation testing, regression results, and real defect links should be added only when testing is performed against an executable system.

---

## Project Note

This is a training QA portfolio artifact.

The matrix is intended to demonstrate how requirements, risks, review findings, test design, test cases, and defects can be linked while preserving the distinction between designed, reviewed, simulated, and executed work.
