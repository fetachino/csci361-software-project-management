# Expense Tracker — Project Plan

## Motivation

People often lose visibility into where their money goes. The proposed Expense Tracker turns individual transactions into organized categories, budget comparisons, and understandable spending reports.

## Scope

### In scope

- User authentication
- Recording expenses with dates, amounts, and categories
- Category budgets
- Dashboard summaries
- Graphical spending reports
- Persistent user data

### Out of scope for the initial release

- Bank-account synchronization
- Payment processing
- Shared household accounts
- Mobile-store deployment
- Financial advice or automated investment decisions

## Functional requirements

| ID | Requirement | Acceptance evidence |
|---|---|---|
| FR-01 | A user can create an account and sign in. | Valid credentials open the dashboard; invalid credentials are rejected. |
| FR-02 | A signed-in user can record an expense. | Date, amount, and category are validated and saved. |
| FR-03 | A user can organize expenses by category. | Category totals reconcile with the transaction list. |
| FR-04 | A user can define a budget for a category. | The dashboard compares spending with the configured budget. |
| FR-05 | A user can view spending reports. | Reports show category and time-based summaries. |
| FR-06 | Data persists between sessions. | Saved records remain available after restarting the application. |

## Proposed design

The proposal described a layered Java application:

```text
Authentication → Dashboard → Expense service → Budget service → Reporting
                                      ↓
                              Persistent storage
```

Collections such as lists or maps were proposed for in-memory operations, with a persistence layer responsible for saving user and transaction data.

## User flow

1. Create an account or sign in.
2. Review the dashboard.
3. Add an expense and select a category.
4. Configure or update category budgets.
5. Review charts and spending reports.
6. Return to the dashboard to monitor progress.

## Three-week delivery plan

| Period | Planned work | Deliverable |
|---|---|---|
| Week 1 | Requirements, task breakdown, environment setup, UML, core classes, authentication | Design baseline and working application skeleton |
| Week 2 | Expense entry, categorization, budgeting, and reporting | Feature-complete prototype |
| Week 3 | Unit testing, user testing, defect fixes, documentation, and presentation | Verified project package and presentation |

## Verification strategy

- Unit-test authentication, validation, expense totals, budget comparisons, and report calculations.
- Test invalid amounts, missing categories, duplicate accounts, and empty reports.
- Perform user testing on the add-expense and reporting flows.
- Re-run the full test set after defect fixes.
- Confirm that saved data can be retrieved in a new application session.

## Risks and mitigations

| Risk | Mitigation |
|---|---|
| Scope grows beyond the three-week schedule | Prioritize authentication, expense entry, budgets, and one useful report. |
| Incorrect totals undermine trust | Keep calculation logic isolated and cover it with unit tests. |
| Requirements are ambiguous | Convert each feature into acceptance evidence before implementation. |
| Persistence introduces integration defects | Test save/retrieve behavior separately from UI behavior. |

## Current evidence

The source material recovered from the computer contains the project proposal and its planning details. A complete Java source tree was not located, so implementation status is intentionally recorded as **not confirmed**.
