# Requirements Traceability Matrix (RTM)

| Requirement ID | Requirement Summary                     | Test Case ID | Test Case Title                     | Coverage Type   |
|----------------|-----------------------------------------|--------------|-------------------------------------|-----------------|
| BR-001         | Successful funds transfer               | TC-001       | Successful Transfer                 | Functional      |
| BR-001         | Successful funds transfer               | TC-002       | Account Balance Update              | Functional      |
| BR-001         | Successful funds transfer               | TC-003       | Transaction Status Persistence      | Functional      |
| BR-002         | Balance validation                      | TC-004       | Insufficient Funds                  | Negative        |
| BR-003         | Invalid account rejection               | TC-005       | Invalid Destination Account         | Negative        |
| BR-004         | Duplicate transaction prevention        | TC-006       | Duplicate Transaction               | Negative        |
| BR-005         | Transaction consistency                 | TC-007       | Timeout Handling                    | Non-Functional  |
| BR-005         | Transaction consistency                 | TC-008       | Service Unavailable                 | Non-Functional  |
| BR-006         | Failed transaction logging              | TC-004       | Insufficient Funds                  | Negative        |
| BR-006         | Failed transaction logging              | TC-005       | Invalid Destination Account         | Negative        |
| BR-006         | Failed transaction logging              | TC-008       | Service Unavailable                 | Non-Functional  |
| BR-007         | Balance integrity                       | TC-009       | Concurrent Transactions             | Non-Functional  |
| BR-008         | Unique transaction identifier           | TC-001       | Successful Transfer                 | Functional      |
| BR-008         | Unique transaction identifier           | TC-006       | Duplicate Transaction               | Negative        |

**Coverage Summary**
- All 8 Business Requirements are mapped to at least one test case.
- Critical paths (transfer, balance integrity, consistency) have multiple test cases.
