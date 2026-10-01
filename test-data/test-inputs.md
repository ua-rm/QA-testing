# API Payload Samples

## Valid Transfer
```json
{
  "transactionId": "tx-uuid-001",
  "sourceAccountId": "ACC-X-1001",
  "targetAccountId": "ACC-Y-2002",
  "amount": 250.00,
  "currency": "USD"
}
```

## Insufficient Funds
```json
{
  "transactionId": "tx-uuid-003",
  "sourceAccountId": "ACC-X-1001",
  "targetAccountId": "ACC-Y-2002",
  "amount": 5000.00,
  "currency": "USD"
}
```

## Invalid Destination
```json
{
  "transactionId": "tx-uuid-002",
  "sourceAccountId": "ACC-X-1001",
  "targetAccountId": "INVALID999",
  "amount": 100.00,
  "currency": "USD"
}
```

## Duplicate Transaction
(Re-use the exact payload of a previously successful transaction, including the same `transactionId`.)
