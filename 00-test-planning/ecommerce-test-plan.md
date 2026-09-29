# E-commerce Manual Testing - Test Plan

## Project

Training E-commerce Application

## Test Plan Version

v1.0

## Test Objectives

- Verify the in-scope shopping cart, checkout, coupon, and free-shipping behavior against the training test basis.
- Identify and document defects, anomalies, and deviations found during planned manual testing activities.
- Produce clear test evidence and a test completion report for the in-scope training work.

## Test Scope

### In Scope

- Shopping cart
- Checkout
- Coupon handling
- Free shipping rules

### Out of Scope

- Full performance assessment
- Full security assessment

## Test Basis

- [E-commerce Training Requirements](ecommerce-requirements.md)
- Reviewed checkout requirements
- Defined acceptance criteria used in the test design artifacts

## Assumptions and Constraints

- This is a training QA project, not a commercial project.
- Testing time is limited to five working days.
- One tester is available.
- Planned execution is manual unless a portfolio artifact explicitly states otherwise.
- Some repository artifacts are design-only training examples; they are not presented as executed tests unless an executable feature is available.

## Stakeholders and Resources

- One tester is responsible for test planning, analysis, design, execution, defect reporting, and test completion activities.
- Business expectations are represented by the training requirements and acceptance criteria stored in the repository.
- No live commercial stakeholders are involved in this training project.

## Test Approach

### Execution Approach

- Dynamic test execution is performed manually where an executable feature is available.
- Design-only artifacts are not presented as executed tests.

### Test Types

- Functional testing for the in-scope features

### Test Techniques

- Equivalence Partitioning
- Boundary Value Analysis
- Decision Table Testing
- State Transition Testing
- Checklist-Based Testing
- Exploratory Testing where appropriate

### Test Case Prioritization

- Risk-based prioritization is based on the current risk analysis documented in the E-commerce Risk Register.
- Dependencies and resource availability may require a lower-priority prerequisite test to be executed before a higher-priority dependent test.

### Test Activities

- Requirements review
- Test analysis and design
- Test execution where an executable feature is available
- Defect reporting
- Confirmation testing when a defect fix is available
- Regression testing after relevant changes
- Test completion

## Entry Criteria

- In-scope training requirements and acceptance criteria are available in the repository.
- The required tester is available.
- Relevant test cases, checklists, and required test data are available before dynamic test execution.
- The relevant test environment or executable demo feature is accessible for activities that require dynamic execution.

## Exit Criteria

- All planned test activities have a documented outcome.
- Planned tests for executable features have been executed, or tests that could not be executed are clearly identified with the reason documented.
- All defects and significant test observations found during execution have been documented.
- A test completion report has been prepared for the in-scope work.

## Test Environment

- Dynamic tests are performed in a desktop web browser when an executable training or demo application is available.
- The application/environment used for execution should be recorded with the relevant test evidence.
- Specification-based artifacts without a matching executable feature remain design-only and are clearly identified as such.

## Test Deliverables

- Requirements review
- Test design artifacts
- Test cases
- Checklists
- Defect reports
- Test execution results
- Test completion report

## Communication

Testing progress and significant issues will be documented in the repository.

## Risks

Product and project risks are documented in the E-commerce Risk Register.

## Schedule

Planned testing duration: five working days.

## Budget

Not applicable to this training portfolio project.

## Project Note

This is a training QA portfolio project.

It does not represent commercial project experience.
