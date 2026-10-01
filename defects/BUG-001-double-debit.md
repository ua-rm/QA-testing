# BUG-001 - Double Debit on Retry / Concurrency

| Field            | Value                                          |
|------------------|--------------------------------                |
| Bug ID           | BUG-001                                        |
| Title            | Double debit after retry / concurrent requests |
| Severity         | Critical                                       |
| Priority         | High                                           |
| Status           | Closed (Fixed)                                 |
| Found In         | Cycle 1                                        |
| Fixed In         | Cycle 2                                        |
| Environment      | UAT                                            |

## Description
Under certain timing conditions (timeout + retry, or near-simultaneous requests), Transaction Service (X) could send the same payload more than once to Account Service (Y), resulting in the source account being debited twice.

## Steps to Reproduce
1. Submit a valid transfer.
2. Force a timeout or network delay on the response from Service Y.
3. Retry the same request (or fire a second concurrent request with the same or overlapping data).
4. Observe the final balance of the source account.

## Expected Behavior
Only a single debit occurs. Duplicate requests are rejected via idempotency.

## Actual Behavior
Source account was debited twice. Balance integrity violated.

## Root Cause (after investigation)
Missing idempotency key / request ID handling between Service X and Service Y.

## Resolution
Implemented `X-Request-ID` / transactionId-based idempotency. Duplicate requests now return HTTP 409 Conflict. Verified in Cycle 2 regression.
