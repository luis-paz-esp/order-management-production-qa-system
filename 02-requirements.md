# Requirements

## Project Name

Order Management & Production Planning QA System

## Purpose

This document defines the main business rules, functional requirements, validation rules, and acceptance criteria for the order management workflow.

The goal is to provide a clear foundation for test case design, smoke testing, sanity testing, regression testing, bug reporting, and future AI-assisted automation.

---

## Business Requirements

| ID | Requirement |
|---|---|
| BR-001 | The system must allow users to submit weekly orders. |
| BR-002 | The system must allow users to submit individual day orders. |
| BR-003 | The system must capture customer information required for order tracking. |
| BR-004 | The system must separate weekly orders from individual orders. |
| BR-005 | The system must capture product selections and customer preferences. |
| BR-006 | The system must capture payment status or payment method. |
| BR-007 | The system must detect incomplete order records before production planning. |
| BR-008 | The system must help identify duplicate customer records. |
| BR-009 | The system must support weekly production planning. |
| BR-010 | The system must support weekly requisition generation. |
| BR-011 | The system must reduce manual consolidation errors. |
| BR-012 | The system should support future AI-assisted validation and automation. |

---

## Functional Requirements

| ID | Module | Requirement |
|---|---|---|
| FR-001 | Customer Registration | The system must capture customer name. |
| FR-002 | Customer Registration | The system must capture customer phone number. |
| FR-003 | Customer Registration | The system must capture delivery or contact information when required. |
| FR-004 | Order Type | The system must allow users to choose between weekly order and individual order. |
| FR-005 | Weekly Order Flow | The system must register all selected days included in the weekly order. |
| FR-006 | Individual Order Flow | The system must register only the selected individual day or days. |
| FR-007 | Product Selection | The system must capture product and complement selections. |
| FR-008 | Customer Preferences | The system must capture customer preferences or special notes. |
| FR-009 | Payment Status | The system must capture payment method or payment confirmation status. |
| FR-010 | Data Validation | The system must prevent required fields from being submitted empty. |
| FR-011 | Data Validation | The system must make duplicate customer records easier to identify. |
| FR-012 | Production Planning | The system must generate daily production totals based on confirmed orders. |
| FR-013 | Requisition Planning | The system must support weekly requisition calculation based on production totals. |
| FR-014 | AI Validation | The system should allow structured data to be reviewed by AI for inconsistencies. |

---

## Validation Rules

| ID | Rule |
|---|---|
| VR-001 | Customer name must not be empty. |
| VR-002 | Customer phone number must not be empty. |
| VR-003 | Order type must be selected before submission. |
| VR-004 | Weekly orders must generate records for the full selected weekly flow. |
| VR-005 | Individual orders must only generate records for selected days. |
| VR-006 | Product selection must not be empty when required. |
| VR-007 | Customer preferences must remain associated with the correct customer. |
| VR-008 | Payment status must be visible before production planning. |
| VR-009 | Duplicate customer names should be identified using phone number or another unique field. |
| VR-010 | Production totals must match confirmed order records. |
| VR-011 | Requisition totals must be based on production totals. |
| VR-012 | Critical notes must be visible before production starts. |

---

## Acceptance Criteria

### Customer Registration

| ID | Acceptance Criteria |
|---|---|
| AC-001 | Given a user opens the order form, when they enter a valid name and phone number, then the information must be saved correctly. |
| AC-002 | Given a user tries to submit the form without a name, when they continue, then the system must prevent submission. |
| AC-003 | Given two users have the same name, when records are reviewed, then each user must be distinguishable by phone number or another unique field. |

---

### Order Type Selection

| ID | Acceptance Criteria |
|---|---|
| AC-004 | Given a user selects a weekly order, when the form continues, then the weekly order flow must be displayed. |
| AC-005 | Given a user selects an individual order, when the form continues, then only individual day options must be displayed. |
| AC-006 | Given a user does not select an order type, when they try to continue, then the system must prevent the user from moving forward. |

---

### Product and Preference Selection

| ID | Acceptance Criteria |
|---|---|
| AC-007 | Given a user selects products and complements, when the order is submitted, then all selections must appear in the response sheet. |
| AC-008 | Given a user adds a special preference or note, when the order is reviewed, then the note must remain linked to the correct customer. |
| AC-009 | Given a required product selection is missing, when the user tries to submit, then the system must block the submission. |

---

### Payment Status

| ID | Acceptance Criteria |
|---|---|
| AC-010 | Given a user selects a payment method, when the form is submitted, then the payment method must be saved correctly. |
| AC-011 | Given payment has not been confirmed, when records are reviewed, then the order must be marked as pending or requiring review. |

---

### Production Planning

| ID | Acceptance Criteria |
|---|---|
| AC-012 | Given confirmed orders exist for a specific day, when production totals are generated, then the total must match the number of confirmed orders. |
| AC-013 | Given an individual order exists for only one day, when weekly production is generated, then it must only affect that selected day. |
| AC-014 | Given customer preferences exist, when production output is generated, then preferences must be visible in the production list. |

---

### Weekly Requisition Generation

| ID | Acceptance Criteria |
|---|---|
| AC-015 | Given production totals are available, when requisitions are generated, then ingredient or supply totals must be based on confirmed production quantities. |
| AC-016 | Given an order is incomplete or unconfirmed, when requisitions are generated, then the system should flag the record for review before final calculation. |

---

### AI-Assisted Validation

| ID | Acceptance Criteria |
|---|---|
| AC-017 | Given structured order data is available, when AI-assisted validation is performed, then incomplete records should be identified. |
| AC-018 | Given duplicate names exist, when AI-assisted validation is performed, then potential duplicate records should be flagged. |
| AC-019 | Given production totals and requisition totals are generated, when AI-assisted validation is performed, then inconsistencies should be highlighted for review. |

---

## Non-Functional Requirements

| ID | Requirement |
|---|---|
| NFR-001 | The form must be usable from mobile devices. |
| NFR-002 | The response sheet must be easy to review and filter. |
| NFR-003 | The workflow must reduce manual review time. |
| NFR-004 | The system must protect sensitive customer information when used for portfolio purposes. |
| NFR-005 | Sample data used in the public repository must be fictional or anonymized. |

---

## Test Design Notes

The requirements in this document will be used to create:

- Smoke test cases
- Sanity test cases
- Functional test cases
- Negative test cases
- Regression test scenarios
- Bug reports
- Risk matrix
- AI-assisted automation proposal