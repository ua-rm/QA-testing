# Test Data Overview

Primary accounts used across most test cases:

| Role                | Account ID    | Initial Balance | Status   |
|---------------------|---------------|-----------------|----------|
| Source Account      | ACC-X-1001    | 1000.00 USD     | ACTIVE   |
| Destination Account | ACC-Y-2002    | 500.00 USD      | ACTIVE   |
| Zero-Balance Source | ACC-X-3003    | 0.00 USD        | ACTIVE   |
| Invalid Account     | INVALID999    | N/A             | NOT FOUND|

Common amounts used:
- Happy path: 100.00 / 250.00 USD
- Insufficient funds: 5000.00 USD
- Concurrent scenario: 700.00 USD each

Full payload samples and additional accounts are maintained in:
- `test-data/users.md`
- `test-data/test-inputs.md`
