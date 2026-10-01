# Manual Testing Portfolio - Example Project

**QA Engineer Example Project**  
Demonstrates structured manual testing of a microservice-based funds transfer flow (Transaction Service X -> Account Ledger Service Y).

---

## Project Overview

| Item              | Detail                                      |
|-------------------|---------------------------------------------|
| Domain            | Digital Banking / FinTech                   |
| Feature Under Test| Inter-service Funds Transfer                |
| Architecture      | Microservice 
                        (Transfer Service X - 
                            Account Service Y) |
| Testing Approach  | Manual + Exploratory + Regression           |
| Tools Used        | Postman, DBeaver, SQL Server, GitHub        |
| Tester            | Uriel Resendez                              |

This repository showcases end-to-end manual testing artifacts for a realistic banking integration scenario, including:

- Requirements & Traceability
- Detailed Test Plan
- Structured Test Cases (Functional, Negative, Non-Functional, Exploratory, Regression)
- Defect Reports with severity/priority
- Test Execution Summaries (Cycle 1 & Cycle 2)
- Test Data & Environment setup
- Evidence placeholders (screenshots / videos)

---

## Repository Structure

```
QA-testing-portfolio/
├── README.md
├── docs/
│   ├── requirements.md
│   ├── requirements-traceability.md
│   ├── test-plan.md
│   ├── test-environment.md
│   └── test-data.md
├── test-cases/
│   ├── functional/
│   ├── negative/
│   ├── non-functional/
│   ├── exploratory/
│   └── regression/
├── test-data/
│   ├── users.md
│   └── test-inputs.md
├── defects/
│   ├── BUG-001-double-debit.md
│   ├── BUG-002-invalid-balance-update.md
│   ├── BUG-003-timeout-pending.md
│   └── BUG-SUMMARY.md
├── test-reports/
│   ├── bug-metrics.md
│   ├── cycle-1/execution-summary.md
│   └── cycle-2/regression-summary.md
└── evidence/
    ├── screenshots/          # Placeholder for actual screenshots
```

---

## Key Skills Demonstrated

- Writing clear, atomic test cases with preconditions, steps, expected results
- Requirements Traceability Matrix (RTM)
- Negative & boundary testing
- Concurrency / race-condition testing
- Timeout & service-unavailability resilience testing
- Defect reporting (severity, priority, steps to reproduce, status)
- Test cycle reporting & metrics
- Regression suite design after defect fixes
- Evidence collection planning

---

## How to Review

1. Start with `docs/test-plan.md` for overall strategy.
2. Review `docs/requirements.md` + `docs/requirements-traceability.md`.
3. Walk through test cases in `test-cases/`.
4. Examine defects and how they were tracked.
5. Read Cycle 1 (discovery) -> Cycle 2 (verification) reports.
6. Check `evidence/` for visual proof (add your real screenshots/videos).

---

## License

This is a personal portfolio example project. Feel free to fork and adapt for your own use.
