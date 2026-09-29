# Free Shipping Threshold — Simulated Defect Report

## Project

Training E-commerce Application

## Artifact Type

Simulated training defect report.

This report demonstrates defect documentation skills using a fictional failure scenario. It does not represent a defect discovered in a commercial or production system.

## Defect Details

**ID:** BUG-TR-001

**Title:** Shipping fee remains 20.00 PLN when cart subtotal is 300.00 PLN at checkout

**Date:** Training exercise

**Author / Role:** QA Tester — Training Project

**Status:** Open

## Test Object

**Application:** Training E-commerce Application  
**Build:** Training Build 1.0

## Environment

Simulated desktop web environment.

## Test Basis

REQ-FS-01:

Cart subtotal equal to or greater than 300.00 PLN should result in a shipping fee of 0.00 PLN.

## Preconditions

- Cart contains products.
- Cart subtotal equals 300.00 PLN.

## Steps to Reproduce

1. Open the cart.
2. Verify that the cart subtotal equals 300.00 PLN.
3. Proceed to checkout.
4. Observe the shipping fee.

## Expected Result

The shipping fee is 0.00 PLN.

## Actual Result

The shipping fee is 20.00 PLN.

## Severity

Medium

**Rationale:** The failure violates a pricing requirement and changes the customer's order cost, while the training scenario does not provide evidence of a broader system-wide impact.

## Priority

High

**Rationale:** The anomaly violates a defined business rule at the exact free-shipping threshold and should be resolved before the feature is accepted.

## Evidence

No real screenshot or execution log is attached because this is a simulated training scenario.

## References

- REQ-FS-01
- Related acceptance test: ATDD-01

## Project Note

This is a training QA portfolio artifact and does not represent commercial testing experience.
