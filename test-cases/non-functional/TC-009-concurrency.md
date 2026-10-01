# TC-009 - Concurrent Transactions (Balance Integrity)

| Field            | Value                          |
|------------------|--------------------------------|
| Test Case ID     | TC-009                         |
| Title            | Concurrent Transfer Requests   |
| Priority         | Critical                       |
| Type             | Non-Functional / Concurrency   |
| Requirement(s)   | BR-007                         |
| Status           | PASS                           |

## Objective
Verify that simultaneous transfer requests against the same source account never produce a negative balance or double-spend.

## Initial State
- Account ACC-X-1001 balance = 1000.00 USD

## Concurrent Requests
- Request A: amount = 700.00 USD
- Request B: amount = 700.00 USD
(Both targeting the same source account, different or same destination)

## Steps
1. Trigger both requests as close to simultaneously as possible (Postman Runner / parallel scripts).
2. Wait for both responses.
3. Query final balance of ACC-X-1001.
4. Inspect transaction records and ledger entries.

## Expected Result
- Only one request succeeds
- The other fails with `INSUFFICIENT_FUNDS` (or equivalent)
- Final balance is never negative
- Database remains consistent (sum of successful debits ≤ original balance)

## Actual Result
PASS - only one transfer succeeded; balance stayed non-negative.
