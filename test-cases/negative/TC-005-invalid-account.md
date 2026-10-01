# TC-005 - Invalid Destination Account

| Field            | Value                          |
|------------------|--------------------------------|
| Test Case ID     | TC-005                         |
| Title            | Invalid Destination Account    |
| Priority         | High                           |
| Type             | Negative                       |
| Requirement(s)   | BR-003, BR-006                 |
| Status           | PASS                           |

## Test Data
```json
{
  "transactionId": "tx-uuid-005",
  "sourceAccountId": "ACC-X-1001",
  "targetAccountId": "INVALID999",
  "amount": 100.00,
  "currency": "USD"
}
```

## Steps
1. Submit transfer with non-existent destination account.
2. Capture response and check balances.
3. Verify failure is logged.

## Expected Result
- Request rejected
- Error: `ACCOUNT_NOT_FOUND` (or equivalent)
- Source balance unchanged
- Failure logged

## Actual Result
PASS
