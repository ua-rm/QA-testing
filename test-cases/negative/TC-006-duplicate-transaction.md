# TC-006 - Duplicate Transaction Prevention

| Field            | Value                          |
|------------------|--------------------------------|
| Test Case ID     | TC-006                         |
| Title            | Duplicate Transaction Prevention |
| Priority         | High                           |
| Type             | Negative / Idempotency         |
| Requirement(s)   | BR-004, BR-008                 |
| Status           | PASS (after fix)               |

## Preconditions
- A transaction with ID `tx-uuid-001` has already been successfully processed.

## Test Data
Re-submit the exact same payload used in the original successful transfer (same `transactionId`).

## Steps
1. Submit the original successful transfer (record response).
2. Immediately re-submit the identical request (same transactionId).
3. Observe second response and final balances.

## Expected Result
- First request: SUCCESS, balances updated once
- Second request: Rejected with `DUPLICATE_TRANSACTION` or HTTP 409 Conflict
- Balances reflect only a single debit/credit

## Actual Result
Initially failed (see BUG-001). After idempotency key implementation -> PASS.
