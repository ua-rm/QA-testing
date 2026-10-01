# TC-001 - Successful Transfer

| Field            | Value                          |
|------------------|--------------------------------|
| Test Case ID     | TC-001                         |
| Title            | Successful Funds Transfer      |
| Priority         | High                           |
| Type             | Functional / Integration       |
| Requirement(s)   | BR-001, BR-008                 |
| Status           | PASS                           |

## Preconditions
- Source account ACC-X-1001 has balance 1000.00 USD
- Destination account ACC-Y-2002 has balance 500.00 USD
- Both accounts are ACTIVE
- Services X and Y are healthy

## Test Data
```json
{
  "transactionId": "tx-uuid-001",
  "sourceAccountId": "ACC-X-1001",
  "targetAccountId": "ACC-Y-2002",
  "amount": 100.00,
  "currency": "USD"
}
```

## Steps
1. Send POST request to Transaction Service (`/api/transactions`) with the payload above.
2. Capture the response (status code and body).
3. Query the database for the transaction record using `transactionId`.
4. Query balances for both accounts.

## Expected Result
- HTTP 200 / 201
- Response contains status = `SUCCESS` and a unique transactionId
- Source balance = 900.00 USD
- Destination balance = 600.00 USD
- Transaction record exists with status SUCCESS

## Actual Result
(As executed in Cycle 1 - matched expected)

## Evidence
- Screenshot of Postman response
- Database query result for balances
