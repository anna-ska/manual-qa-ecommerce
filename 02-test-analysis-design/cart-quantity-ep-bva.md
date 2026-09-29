# Cart Quantity — Equivalence Partitioning and Boundary Value Analysis

## Project

Training E-commerce Application

## Feature

Shopping Cart — Product Quantity

## Test Basis

**REQ-CART-01:**  
The cart quantity field accepts integer values from **1 to 10 inclusive**.  
Values outside this range must be rejected.

## Test Condition

Verify that the cart quantity field correctly accepts valid integer values from 1 to 10 and rejects integer values outside the allowed range.

---

## Equivalence Partitioning

Based on the requirement, three equivalence partitions can be identified.

| ID | Partition | Type | Representative Value | Expected Result |
|---|---|---|---:|---|
| EP-01 | Integer value < 1 | Invalid | -1 | Value is rejected |
| EP-02 | Integer value from 1 to 10 inclusive | Valid | 4 | Value is accepted |
| EP-03 | Integer value > 10 | Invalid | 21 | Value is rejected |

### EP Coverage

All identified integer equivalence partitions are covered.

**Coverage: 3/3 partitions = 100%**

---

## 2-Value Boundary Value Analysis

The valid range has two boundaries:

- lower boundary: **1**
- upper boundary: **10**

For 2-value BVA, the boundary value and the closest value in the adjacent partition are tested.

| ID | Boundary | Test Value | Expected Classification | Expected Result |
|---|---|---:|---|---|
| BVA2-01 | Lower | 0 | Invalid | Value is rejected |
| BVA2-02 | Lower | 1 | Valid | Value is accepted |
| BVA2-03 | Upper | 10 | Valid | Value is accepted |
| BVA2-04 | Upper | 11 | Invalid | Value is rejected |

### 2-Value BVA Coverage

All required 2-value boundary values are covered.

**Coverage: 4/4 boundary values = 100%**

---

## 3-Value Boundary Value Analysis

For 3-value BVA, each boundary and its two direct neighboring values are tested.

### Lower Boundary

For the lower boundary **1**:

- 0 — immediately below the boundary
- 1 — boundary value
- 2 — immediately above the boundary

### Upper Boundary

For the upper boundary **10**:

- 9 — immediately below the boundary
- 10 — boundary value
- 11 — immediately above the boundary

| ID | Boundary | Test Value | Expected Classification | Expected Result |
|---|---|---:|---|---|
| BVA3-01 | Lower | 0 | Invalid | Value is rejected |
| BVA3-02 | Lower | 1 | Valid | Value is accepted |
| BVA3-03 | Lower | 2 | Valid | Value is accepted |
| BVA3-04 | Upper | 9 | Valid | Value is accepted |
| BVA3-05 | Upper | 10 | Valid | Value is accepted |
| BVA3-06 | Upper | 11 | Invalid | Value is rejected |

### 3-Value BVA Coverage

All required boundary values and their direct neighbors are covered.

**Coverage: 6/6 boundary values and neighbors = 100%**

---

## Additional Input Considerations

The requirement explicitly defines the allowed range for integer values but does not describe how the field should handle other types of input.

Examples that may require clarification or additional testing include:

- decimal values, e.g. `1.5`
- alphabetic input, e.g. `abc`
- special characters
- an empty value
- leading or trailing spaces
- values entered using alternative input methods, if supported by the interface

These cases are not included in the EP or BVA coverage above because their expected behavior is not explicitly defined in the current test basis.

If the user interface restricts the field to integer input only, some of these cases may not be applicable.

---

## Test Design Summary

The following specification-based test techniques were applied:

- Equivalence Partitioning
- 2-Value Boundary Value Analysis
- 3-Value Boundary Value Analysis

The selected test data focuses on the defined valid range and its boundaries while avoiding assumptions about behavior not specified in the requirement.

## Project Note

This is a training QA portfolio artifact.

The test conditions and test data were derived from the stated training requirement. No undocumented application behavior was treated as an expected result.
