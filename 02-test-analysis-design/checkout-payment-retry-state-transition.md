# Checkout Payment Retry — State Transition Test Design

## Project

Training E-commerce Application

## Feature

Checkout / Payment Retry

## Purpose

Demonstrate state transition testing using the checkout payment retry flow.

This is a design-only training artifact. The state model below is based on the available requirement and explicitly stated training assumptions. It does not represent behavior verified in a live application.

---

## Test Basis

**REQ-CHK-06 — Payment Retry**

If payment fails, the user should be able to try again.

Related requirements review findings:

- **REV-006** — the payment failure notification is not defined.
- **REV-007** — the allowed number of retries is not defined.
- **REV-008** — the order and cart state after payment failure is not defined.

Because REQ-CHK-06 does not define a complete state model, additional assumptions are required to demonstrate the state transition technique.

These assumptions are used only for this training exercise and should require stakeholder confirmation in a real project.

---

## Training Assumptions

For this state transition model:

1. The checkout is ready for payment before the user submits a payment attempt.
2. Submitting payment moves the payment flow to a processing state.
3. A successful payment confirms the order.
4. A failed payment does not confirm the order and moves the flow to a payment-failed state.
5. From the payment-failed state, the user can retry payment.
6. Retrying payment starts a new payment-processing attempt.
7. No maximum retry count is modeled because REQ-CHK-06 does not define one.

The model does not define cart persistence, payment-provider behavior, timeout behavior, cancellation, or browser-navigation behavior.

---

## States

| State ID | State | Description |
|---|---|---|
| S1 | Ready for Payment | Checkout data is available and the user can submit payment. |
| S2 | Payment Processing | A payment attempt has been submitted and is being processed. |
| S3 | Payment Failed | The current payment attempt failed and the order is not confirmed. |
| S4 | Order Confirmed | Payment succeeded and the order is confirmed. |

---

## Events

| Event ID | Event | Description |
|---|---|---|
| E1 | Submit payment | User submits a payment attempt. |
| E2 | Payment succeeds | The payment attempt returns a successful result. |
| E3 | Payment fails | The payment attempt returns a failed result. |
| E4 | Retry payment | User starts another payment attempt after a failure. |

---

## State Transition Table

| Transition ID | Current State | Event | Next State | Expected Result |
|---|---|---|---|---|
| T1 | S1 — Ready for Payment | E1 — Submit payment | S2 — Payment Processing | A payment attempt starts. |
| T2 | S2 — Payment Processing | E2 — Payment succeeds | S4 — Order Confirmed | The order is confirmed. |
| T3 | S2 — Payment Processing | E3 — Payment fails | S3 — Payment Failed | The order remains unconfirmed and retry is available. |
| T4 | S3 — Payment Failed | E4 — Retry payment | S2 — Payment Processing | A new payment attempt starts. |

---

## State Flow

```text
S1 Ready for Payment
        |
        | T1: Submit payment
        v
S2 Payment Processing
     /              \
    / T3: failure    \ T2: success
   v                  v
S3 Payment Failed   S4 Order Confirmed
   |
   | T4: Retry payment
   +--------------------> S2 Payment Processing
```

---

## Derived Test Scenarios

| ID | Requirement | Transition(s) | Preconditions | Action / Event | Expected State / Result |
|---|---|---|---|---|---|
| ST-01 | REQ-CHK-06 | T1 | Checkout is in S1 — Ready for Payment. | Submit payment. | System moves to S2 — Payment Processing. |
| ST-02 | REQ-CHK-06 | T1, T2 | Checkout is in S1 — Ready for Payment. | Submit payment and receive a successful payment result. | System moves through S2 and ends in S4 — Order Confirmed. |
| ST-03 | REQ-CHK-06 | T1, T3 | Checkout is in S1 — Ready for Payment. | Submit payment and receive a failed payment result. | System moves through S2 and ends in S3 — Payment Failed; order is not confirmed. |
| ST-04 | REQ-CHK-06 | T4 | Checkout is in S3 — Payment Failed. | Retry payment. | System moves to S2 — Payment Processing and starts a new payment attempt. |
| ST-05 | REQ-CHK-06 | T4, T2 | Checkout is in S3 — Payment Failed. | Retry payment and receive a successful payment result. | System moves through S2 and ends in S4 — Order Confirmed. |
| ST-06 | REQ-CHK-06 | T4, T3 | Checkout is in S3 — Payment Failed. | Retry payment and receive another failed payment result. | System moves through S2 and returns to S3 — Payment Failed; retry remains available within this simplified training model. |

---

## Transition Coverage

The model contains four identified valid transitions:

- T1 — Ready for Payment → Payment Processing
- T2 — Payment Processing → Order Confirmed
- T3 — Payment Processing → Payment Failed
- T4 — Payment Failed → Payment Processing

All four transitions are covered by the derived scenarios.

**Valid transition coverage: 4/4 = 100%**

This coverage statement applies only to the simplified training model defined in this document.

---

## Traceability

| Requirement / Finding | Related State Transition Coverage |
|---|---|
| REQ-CHK-06 | T1, T2, T3, T4; ST-01 to ST-06 |
| REV-006 | Not resolved by this model; failure-message behavior remains undefined. |
| REV-007 | Not resolved by this model; no maximum retry count is modeled. |
| REV-008 | Partially addressed through explicit training assumptions: the order remains unconfirmed after payment failure, while the cart state remains undefined. Stakeholder clarification would be required in a real project. |

---

## Limitations

This artifact demonstrates state transition test design only.

It does not claim that:

- the modeled states exist in a real application,
- the scenarios were executed,
- the training assumptions are approved business requirements,
- payment retries are unlimited in a real system.

If an executable system or clarified requirements become available, the state model and expected results should be reviewed before test execution.

---

## Project Note

This is a training QA portfolio artifact.

It demonstrates state transition modeling while keeping assumptions separate from documented requirements and previously identified requirements-review findings.
