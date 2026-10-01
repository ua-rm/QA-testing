# TC-004 - Insufficient Funds

| Field            | Value                          |
|------------------|--------------------------------|
| Test Case ID     | TC-004                         |
| Title            | Insufficient Funds Rejection   |
| Priority         | High                           |
| Type             | Negative                       |
| Requirement(s)   | BR-002, BR-006                 |
| Status           | PASS                           |

## Preconditions
- Source account ACC-X-1001 balance = 1000.00 USD

## Test Data
```json
{
  "transactionId": "tx-uuid-004",
  "sourceAccountId": "ACC-X-1001",
  "targetAccountId": "ACC-Y-2002",
  "amount": 5000.00,
  "currency": "USD"
}
```

## Steps
1. Submit the transfer request with amount larger than available balance.
2. Capture response.
3. Verify source and destination balances remain unchanged.
4. Check that a failure log entry exists.

## Expected Result
- HTTP 400 / 422 or business error
- Error code / message contains `INSUFFICIENT_FUNDS`
- Balances unchanged
- Failed transaction logged

## Actual Result
PASS
