# Manual QA E-commerce Portfolio Project

This repository demonstrates my practical understanding of core manual software testing activities based on concepts covered in the ISTQB CTFL v4.0.1 syllabus.

The project focuses on test planning, requirements review, risk analysis, test design, acceptance testing, defect reporting, and traceability.

> This is a training portfolio project. It does not represent commercial project experience.

## What This Project Demonstrates

- test planning
- requirements review and static testing
- product and project risk analysis
- risk-based test prioritization
- equivalence partitioning
- boundary value analysis
- decision table testing
- state transition testing
- checklist-based testing
- acceptance test design
- defect reporting
- traceability between requirements and testware
- Git and GitHub workflow
- Markdown documentation

## Project Scope

The training application represents an e-commerce system with selected functionality related to:

- shopping cart
- checkout
- coupon handling
- free shipping rules

Some artifacts are specification-based and were created to demonstrate test analysis and design.

Where no executable feature was available, the artifact is clearly marked as design-only or simulated.

## Repository Structure

### 01. Test Basis and Planning

- [E-commerce Training Requirements](00-test-planning/ecommerce-requirements.md)
- [Test Plan](00-test-planning/ecommerce-test-plan.md)
- [Risk Register](00-test-planning/ecommerce-risk-register.md)

The requirements document provides the test basis for the project. The Test Plan and Risk Register define the testing scope, approach, constraints, risks, priorities, and planned testing activities.

### 02. Requirements Review

- [Checkout Requirements Review](01-requirements-review/checkout-requirements-review.md)

This artifact demonstrates static testing by identifying ambiguities, omissions, and testability concerns before dynamic testing.

### 03. Test Analysis and Design

- [Cart Quantity — Equivalence Partitioning and Boundary Value Analysis](02-test-analysis-design/cart-quantity-ep-bva.md)
- [Checkout Coupon — Decision Table](02-test-analysis-design/checkout-coupon-decision-table.md)
- [Checkout Payment Retry — State Transition Test Design](02-test-analysis-design/checkout-payment-retry-state-transition.md)
- [Checkout — Experience-Based Checklist](02-test-analysis-design/checkout-experience-based-checklist.md)

These artifacts demonstrate specification-based and experience-based test design techniques.

### 04. Acceptance Testing

- [Free Shipping — ATDD-style Acceptance Tests](03-test-cases/free-shipping-atdd-acceptance-tests.md)

The acceptance tests are derived directly from defined acceptance criteria and include basic traceability.

### 05. Defect Reporting

- [Free Shipping Threshold — Simulated Defect Report](04-defect-reports/free-shipping-simulated-defect.md)

This artifact demonstrates defect documentation structure, including reproduction steps, expected and actual results, severity, priority, and references.

The defect is simulated and is not presented as a defect found during real application testing.

### 06. Traceability

- [Requirements Traceability Matrix](05-traceability/requirements-traceability-matrix.md)

The matrix links requirements to related risks, review findings, test design artifacts, test cases, execution status, and defects where applicable.

## Requirements Traceability Overview

| Area | Requirement IDs | Main Related Artifact |
|---|---|---|
| Shopping Cart | REQ-CART-01 | Equivalence Partitioning and Boundary Value Analysis |
| Checkout | REQ-CHK-01 to REQ-CHK-06 | Requirements Review |
| Checkout — Payment Retry | REQ-CHK-06 | State Transition Testing |
| Coupon | REQ-CPN-01 to REQ-CPN-04 | Decision Table Testing |
| Free Shipping | REQ-FS-01 to REQ-FS-03 | ATDD-style Acceptance Tests |

## Test Design Techniques Used

### Equivalence Partitioning

Used to divide input data into valid and invalid partitions and select representative values.

### Boundary Value Analysis

Used to test values around defined input boundaries.

### Decision Table Testing

Used to test combinations of business conditions and resulting system actions.

### Checklist-Based Testing

Used to identify additional test ideas based on requirements, risks, and common failure patterns.

### Acceptance Test Design

Used to derive test cases directly from acceptance criteria.

### State Transition Testing

Used to model payment retry behavior as states and valid transitions, with training assumptions clearly separated from documented requirements.

## Risk-Based Testing

The project includes a separate risk register covering:

- product risks
- project risks
- likelihood and impact
- risk levels
- planned testing responses

Risk analysis is used to influence test priority and depth.

## Current Limitations

This repository currently focuses mainly on test analysis, design, and documentation.

It does not yet represent a complete real-world test execution project.

The following areas will be demonstrated in separate practical portfolio projects:

- execution of tests against a live application
- Pass / Fail / Blocked test results
- real test evidence
- exploratory testing sessions
- real defect reports
- regression and confirmation testing
- API testing
- SQL-based data validation

## Tools Used

- Git
- GitHub
- GitHub Desktop
- Markdown

Additional tools will be documented only after they are used in practical portfolio projects.

## Portfolio Development

This repository is one part of a broader QA portfolio.

The practical manual testing stage is demonstrated in the [DemoBlaze Manual Testing Project](https://github.com/anna-ska/manual-testing-demoblaze).

Future portfolio development may include:

1. API testing using Postman
2. basic SQL data validation
3. defect and test management workflow

## Status

Design phase complete.

This training repository is complete for its intended scope: test planning, requirements review, risk analysis, test design, acceptance test design, simulated defect reporting, and requirements traceability.

Dynamic test execution is intentionally not represented in this repository and will be demonstrated in separate practical portfolio projects.

