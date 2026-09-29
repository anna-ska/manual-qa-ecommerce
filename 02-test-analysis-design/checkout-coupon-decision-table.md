# Checkout Coupon - Decision Table Test Design

## Project
Training E-commerce Application

## Feature
Checkout / Coupon

## Test Basis

**REQ-CPN-01 — Optional Coupon**  
Coupon is optional. If no coupon is entered, checkout continues without a discount.

**REQ-CPN-02 — Invalid Coupon**  
If a coupon is entered but is invalid, the system displays an invalid coupon error.

**REQ-CPN-03 — Valid Coupon and Minimum Cart Value**  
A valid coupon applies a 15% discount only when the cart total is at least 100.00 PLN.

**REQ-CPN-04 — Valid Coupon Below Minimum Cart Value**  
If the coupon is valid but the cart total is below 100.00 PLN, the system displays a minimum cart value message.

## Conditions

- C1: Coupon entered?
- C2: Coupon valid?
- C3: Cart total >= 100.00 PLN?

## Actions

- A1: Continue without discount
- A2: Show invalid coupon error
- A3: Show minimum cart value message
- A4: Apply 15% discount

## Decision Table

| Conditions / Actions | R1 | R2 | R3 | R4 |
|---|---|---|---|---|
| C1: Coupon entered? | F | T | T | T |
| C2: Coupon valid? | - | F | T | T |
| C3: Cart total >= 100.00 PLN? | - | - | F | T |
| A1: Continue without discount | X |  |  |  |
| A2: Show invalid coupon error |  | X |  |  |
| A3: Show minimum cart value message |  |  | X |  |
| A4: Apply 15% discount |  |  |  | X |

## Derived Test Scenarios

| ID | Requirement | Rule | Test Data / Conditions | Expected Result |
|---|---|---|---|---|
| DT-01 | REQ-CPN-01 | R1 | No coupon entered; cart total: 80.00 PLN | Checkout continues without a discount. |
| DT-02 | REQ-CPN-02 | R2 | Invalid coupon entered; cart total: 150.00 PLN | System displays an invalid coupon error. |
| DT-03 | REQ-CPN-04 | R3 | Valid coupon entered; cart total: 99.99 PLN | System displays a minimum cart value message. |
| DT-04 | REQ-CPN-03 | R4 | Valid coupon entered; cart total: 100.00 PLN | System applies a 15% discount. |

## Coverage

Decision table rule coverage: 4/4 = 100%

## Notes

The test scenarios were derived from the stated training requirements.
No undocumented application behavior was assumed.
