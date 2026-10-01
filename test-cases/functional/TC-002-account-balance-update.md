# TC-002 - Account Balance Update

| Field            | Value                          |
|------------------|--------------------------------|
| Test Case ID     | TC-002                         |
| Title            | Account Balance Update         |
| Priority         | High                           |
| Type             | Functional                     |
| Requirement(s)   | BR-001                         |
| Status           | PASS                           |

## Preconditions
- Source ACC-X-1001 = 1000.00 USD
- Destination ACC-Y-2002 = 500.00 USD

## Test Data
Amount: 250.00 USD

## Steps
1. Execute a successful transfer of 250.00 USD (reuse TC-001 flow).
2. Immediately query both account balances via Account Service or direct DB.
3. Confirm the delta matches the transferred amount.

## Expected Result
- Source balance decreased by exactly 250.00
- Destination balance increased by exactly 250.00
- No intermediate or partial updates visible

## Actual Result
Matched expected (after BUG-002 was fixed).
