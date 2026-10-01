# Test Plan - Funds Transfer (Microservice X -> Microservice Y)

## 1. Document Information

| Item              | Value                                      |
|-------------------|--------------------------------------------|
| Project           | Digital Banking Platform                   |
| Module / Feature  | Funds Transfer                             |
| Test Type         | Manual Testing (Functional, Negative, Non-Functional, Exploratory, Regression) |
| Version           | 1.0                                        |
| Environment       | UAT / QA                                   |
| Tester            | Uriel Resendez                             |
| Date              | 2026-10-01                                 |
| Status            | Approved                                   |

---

## 2. Objective

Validate that the funds transfer flow between **Transaction Service (X)** and **Account Ledger Service (Y)** correctly:

- Processes valid transfers and updates balances
- Rejects invalid / insufficient / duplicate requests
- Maintains data consistency under timeouts, service unavailability, and concurrency
- Logs failures appropriately
- Preserves balance integrity (no negative balances)

---

## 3. Scope

### In Scope
- Happy-path transfer (X -> Y)
- Balance validation and updates
- Error handling (insufficient funds, invalid account, duplicate)
- Timeout and service-down scenarios
- Concurrent transfer attempts
- Transaction status persistence
- Basic exploratory scenarios (decimals, boundaries, rapid retries)

### Out of Scope
- UI / frontend testing
- Performance / load testing beyond basic concurrency
- Security testing (auth, encryption)
- Other banking features (payments, statements, etc.)

---

## 4. Testing Types

| Type              | Description                                      |
|-------------------|--------------------------------------------------|
| Functional        | Verify core transfer logic and balance updates   |
| Negative          | Invalid inputs, business rule violations         |
| Non-Functional    | Timeout, service unavailable, concurrency        |
| Integration       | Communication & consistency between Service X and Y |
| Exploratory       | Unscripted discovery of edge behavior            |
| Regression        | Re-execution after defect fixes                  |

---

## 5. Entry Criteria

- Requirements signed off
- Test environment (UAT) available and stable
- Test accounts seeded with known balances
- Postman collections / API endpoints accessible
- Database access via DBeaver granted

## 6. Exit Criteria

- All planned test cases executed
- Critical and High defects either fixed or accepted with documented risk
- Regression suite passed after fixes
- Test summary report published
- Evidence (screenshots / logs) attached

---

## 7. Test Environment

See `docs/test-environment.md`

## 8. Test Data

See `docs/test-data.md` and `test-data/` folder

## 9. Risks & Mitigations

| Risk                              | Impact | Mitigation                              |
|-----------------------------------|--------|-----------------------------------------|
| Unstable UAT environment          | High   | Schedule testing in stable windows; use mocks where possible |
| Incomplete requirements           | Medium | Clarify with BA / Dev early             |
| Difficulty simulating timeouts    | Medium | Use network tools / service stop        |
| Concurrent test interference      | Low    | Dedicated test accounts                 |

---

## 10. Schedule (High Level)

| Phase                  | Activities                          | Target    |
|------------------------|-------------------------------------|-----------|
| Cycle 1 - Discovery    | Full suite + exploratory            | Week 1    |
| Defect Triage          | Log & prioritize bugs               | Week 1    |
| Cycle 2 - Regression   | Verify fixes + full regression      | Week 2    |
| Sign-off               | Final report & evidence             | Week 2    |

---

## 11. Deliverables

- This Test Plan
- Requirements Traceability Matrix
- Test Cases (all categories)
- Defect Reports
- Execution Summaries (Cycle 1 & 2)
- Bug Metrics
- Evidence (screenshots / short videos)

---

## 12. Approvals

| Role          | Name             | Date       | Signature |
|---------------|------------------|------------|-----------|
| QA Lead       |                  |            |           |
| Dev Lead      |                  |            |           |
| Product Owner |                  |            |           |
