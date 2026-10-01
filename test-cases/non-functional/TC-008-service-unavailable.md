# TC-008 - Service Unavailable

| Field            | Value                          |
|------------------|--------------------------------|
| Test Case ID     | TC-008                         |
| Title            | Account Service Unavailable    |
| Priority         | High                           |
| Type             | Non-Functional / Resilience    |
| Requirement(s)   | BR-005, BR-006                 |
| Status           | PASS                           |

## Steps
1. Stop / disable Account Ledger Service (Y).
2. Submit a transfer request via Transaction Service (X).
3. Observe response and final balances.
4. Restart Service Y and verify no orphaned records.

## Expected Result
- Transfer fails gracefully
- Transaction marked FAILED (or equivalent)
- Error logged
- No balance changes on either account
- System recovers cleanly when Y is restored

## Actual Result
PASS
