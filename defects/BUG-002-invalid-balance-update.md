# BUG-002 - Destination Balance Not Updated

| Field            | Value                                                      |
|------------------|--------------------------------                            |
| Bug ID           | BUG-002                                                    |
| Title            | Destination balance not updated after successful transfer  |
| Severity         | High                                                       |
| Priority         | High                                                       |
| Status           | Closed                                                     |
| Found In         | Cycle 1                                                    |
| Fixed In         | Cycle 1 / early patch                                      |
| Environment      | UAT                                                        |

## Description
After a transfer reported as SUCCESS, the source account was correctly debited but the destination account balance remained unchanged.

## Steps to Reproduce
1. Note initial balances (Source 1000, Destination 500).
2. Execute a transfer of 250.00 USD.
3. Query both balances.

## Expected
Source = 750.00, Destination = 750.00

## Actual
Source = 750.00, Destination = 500.00

## Resolution
Fixed in the Account Ledger Service update logic. Re-tested and closed.
