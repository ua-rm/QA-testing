# BUG-003 - Transaction Remains PENDING After Timeout

| Field            | Value                                                  |
|------------------|--------------------------------                        |
| Bug ID           | BUG-003                                                |
| Title            | Transaction remains PENDING indefinitely after timeout |
| Severity         | Medium                                                 |
| Priority         | Medium                                                 |
| Status           | Closed                                                 |
| Found In         | Cycle 1                                                |
| Fixed In         | Cycle 2                                                |
| Environment      | UAT                                                    |

## Description
When Account Service (Y) timed out, the transaction stayed in PENDING state indefinitely instead of moving to a terminal FAILED state or triggering compensation.

## Steps to Reproduce
1. Introduce latency > timeout threshold on Service Y.
2. Submit a transfer.
3. Poll transaction status over time.

## Expected
Transaction reaches a terminal state (FAILED) within a defined window, or a compensation transaction is executed.

## Actual
Status remained PENDING with no further action.

## Resolution
Service X now triggers a compensation / rollback path and marks the transaction FAILED. Verified in Cycle 2.
