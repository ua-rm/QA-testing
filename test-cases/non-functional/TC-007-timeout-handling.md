# TC-007 - Timeout Handling

| Field            | Value                          |
|------------------|--------------------------------|
| Test Case ID     | TC-007                         |
| Title            | Timeout Handling & Consistency |
| Priority         | High                           |
| Type             | Non-Functional / Resilience    |
| Requirement(s)   | BR-005                         |
| Status           | PASS (after fix)               |

## Objective
Verify that when Account Service (Y) responds slowly or times out, Transaction Service (X) does not leave balances in an inconsistent state.

## Steps
1. Introduce artificial latency / timeout on the call from X to Y (> 3000 ms).
2. Submit a valid transfer request.
3. Observe final transaction status and account balances.
4. Confirm whether a compensation / rollback occurred.

## Expected Result
- Transaction ends in a terminal state: `FAILED` or `PENDING` -> eventually resolved
- No partial debit (source and destination remain consistent)
- Appropriate error is logged

## Actual Result
Initially left transaction in PENDING indefinitely (BUG-003). After fix -> proper compensation and terminal status. PASS.
