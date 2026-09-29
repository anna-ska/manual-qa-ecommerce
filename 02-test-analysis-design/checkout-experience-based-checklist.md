# Checkout — Experience-Based Test Checklist

## Project
Training E-commerce Application

## Feature
Checkout / Shopping Cart

## Purpose
Provide a concise experience-based checklist for areas that may require
additional testing beyond the previously designed specification-based tests.

## Sources

The checklist is based on:
- available training requirements
- previously identified review findings
- experience-based risk ideas

## Checklist

| ID | Check | Source / Rationale | Status | Notes |
|---|---|---|---|---|
| CHK-01 | Check that the visible cart item count remains consistent after adding and removing multiple products. | State-synchronization issues are a common cart risk. | Not Run | |
| CHK-02 | Check the cart state after removing the last remaining product, including any visible cart indicator. | Removing the last remaining item is a state-sensitive cart scenario that may expose synchronization issues. | Not Run | |
| CHK-03 | Check cart and checkout state after navigating away from the cart and returning to it. | Navigation can expose stale-state or synchronization problems. | Not Run | |
| CHK-04 | Check that leaving the optional coupon field empty does not prevent checkout and does not apply a discount. | Based on the stated coupon requirement. | Not Run | |
| CHK-05 | Check handling of leading/trailing whitespace in coupon input for consistent behavior and clear feedback. | Whitespace is a common input-validation risk. | Not Run | |
| CHK-06 | Check a very long coupon input for field behavior, UI stability, and clear feedback. | Long inputs can expose validation and UI issues. | Not Run | |
| CHK-07 | Check repeated submission of the same coupon for consistent behavior and clear feedback. | Repeated actions may expose state-handling issues. | Not Run | |
| CHK-08 | Check cart contents and visible totals after several add/remove operations before proceeding to checkout. | Repeated state changes may expose calculation or synchronization problems. | Not Run | |

## Maintenance

The checklist should be reviewed and updated when new defects,
risks, or recurring failure patterns are identified.

## Project Note

This is a training QA portfolio artifact.
No commercial project experience is implied.
