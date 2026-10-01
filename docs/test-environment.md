# Test Environment

## Environment Name
UAT (User Acceptance Testing)

## Services Under Test

| Service                     | Role                              | Endpoint Base              |
|-----------------------------|-----------------------------------|----------------------------|
| Transaction Service (X)     | Initiates and orchestrates transfer | `/api/transactions`       |
| Account Ledger Service (Y)  | Maintains balances & ledger       | `/api/accounts`            |

## Database
- Engine: Microsoft SQL Server
- Access tool: DBeaver
- Purpose: Verify balance updates, transaction status, and audit logs

## Tools Used
- **Postman** - API request execution and collection management
- **DBeaver** - Database inspection and validation queries
- **GitHub** - Version control of test artifacts
- Network tools / service stop commands - Simulate timeouts and unavailability

## Access Notes
- All test accounts are pre-seeded and isolated from production data.
- Credentials and connection strings are managed outside this repository (secure vault / local env).
