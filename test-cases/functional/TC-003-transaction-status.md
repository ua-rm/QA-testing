# TC-003 - Transaction Status Persistence

| Field            | Value                          |
|------------------|--------------------------------|
| Test Case ID     | TC-003                         |
| Title            | Transaction Status Persistence |
| Priority         | Medium                         |
| Type             | Functional                     |
| Requirement(s)   | BR-001, BR-008                 |
| Status           | PASS                           |

## Preconditions
- Valid transfer request ready

## Steps
1. Submit a successful transfer.
2. Query the transactions table / endpoint using the returned transactionId.
3. Verify status field and timestamps.

## Expected Result
- Status = `SUCCESS`
- Created and updated timestamps are populated
- Transaction is queryable by ID

## Actual Result
PASS
