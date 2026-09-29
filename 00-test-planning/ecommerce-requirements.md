# E-commerce Training Requirements

## Project

Training E-commerce Application

## Purpose

This document provides the test basis for the training artifacts stored in this repository.

The requirements below are used for requirements review, test analysis, test design, acceptance testing, risk analysis, and defect reporting.

Some requirements are intentionally incomplete or ambiguous because they are used as input for static testing and requirements review exercises.

This is a training portfolio artifact and does not represent requirements from a commercial project.

---

## Shopping Cart Requirements

### REQ-CART-01 — Product Quantity

The cart quantity field accepts integer values from **1 to 10 inclusive**.

Values outside this range must be rejected.

---

## Checkout Requirements

### REQ-CHK-01 — Checkout Availability

The user can proceed to checkout if there is at least one product in the cart.

### REQ-CHK-02 — Personal Data

The user must provide valid personal data.

### REQ-CHK-03 — Delivery Selection

Delivery should be selected automatically.

### REQ-CHK-04 — Order Processing Time

The order should be processed quickly.

### REQ-CHK-05 — Purchase Confirmation

The user receives purchase confirmation.

### REQ-CHK-06 — Payment Retry

If payment fails, the user should be able to try again.

> Note: The checkout requirements above intentionally preserve the wording used in the requirements review artifact.  
> Identified ambiguities, omissions, and testability issues are documented separately in `checkout-requirements-review.md`.

---

## Coupon Requirements

### REQ-CPN-01 — Optional Coupon

The coupon is optional.

If no coupon is entered, checkout continues without a discount.

### REQ-CPN-02 — Invalid Coupon

If a coupon is entered but is invalid, the system displays an invalid coupon error.

### REQ-CPN-03 — Valid Coupon and Minimum Cart Value

A valid coupon applies a **15% discount** only when the cart total is at least **100.00 PLN**.

### REQ-CPN-04 — Valid Coupon Below Minimum Cart Value

If the coupon is valid but the cart total is below **100.00 PLN**, the system displays a minimum cart value message.

---

## Free Shipping Requirements

### REQ-FS-01 — Free Shipping Threshold

A cart subtotal equal to or greater than **300.00 PLN** results in a shipping fee of **0.00 PLN**.

### REQ-FS-02 — Standard Shipping Below Threshold

A cart subtotal below **300.00 PLN** results in a standard shipping fee of **20.00 PLN**.

### REQ-FS-03 — Shipping Fee Visibility

The shipping fee is displayed before the customer confirms the order.

---

## Requirement Summary

| Area | Requirement IDs | Count |
|---|---|---:|
| Shopping Cart | REQ-CART-01 | 1 |
| Checkout | REQ-CHK-01 to REQ-CHK-06 | 6 |
| Coupon | REQ-CPN-01 to REQ-CPN-04 | 4 |
| Free Shipping | REQ-FS-01 to REQ-FS-03 | 3 |
| **Total** |  | **14** |

---

## Current Traceability

| Requirement(s) | Related Artifact |
|---|---|
| REQ-CART-01 | `02-test-analysis-design/cart-quantity-ep-bva.md` |
| REQ-CHK-01 to REQ-CHK-06 | `01-requirements-review/checkout-requirements-review.md` |
| REQ-CHK-06 | `02-test-analysis-design/checkout-payment-retry-state-transition.md` |
| REQ-CPN-01 to REQ-CPN-04 | `02-test-analysis-design/checkout-coupon-decision-table.md` |
| REQ-FS-01 to REQ-FS-03 | `03-test-cases/free-shipping-atdd-acceptance-tests.md` |
| REQ-FS-01 | `04-defect-reports/free-shipping-simulated-defect.md` |

This table provides only basic artifact-level traceability.

Detailed traceability is documented in the [Requirements Traceability Matrix](../05-traceability/requirements-traceability-matrix.md), linking requirements to risks, review findings, test design, test cases, execution status, and defects where applicable.

---

## Project Note

This document is the test basis for a training QA portfolio project.

The requirements are intentionally limited in scope and support the manual testing techniques demonstrated in this repository.
