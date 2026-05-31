# User Stories

## Project Name

Order Management & Production Planning QA System

## Purpose

This document defines the main user stories for the order management workflow. These stories help describe how different users interact with the system and provide a foundation for test cases, acceptance criteria, and validation scenarios.

---

## User Roles

| Role | Description |
|---|---|
| Customer | User who submits an order through the order form. |
| Returning Customer | User who has already submitted previous orders. |
| New Customer | User who submits an order for the first time and may need additional registration information. |
| Operations Admin | User responsible for reviewing orders, validating data, and preparing production planning. |
| Production Team | Team that uses order data to prepare daily production quantities. |
| Purchasing / Requisition User | User who uses production totals to generate weekly supply requirements. |
| QA Tester | User responsible for validating the workflow, testing form logic, documenting bugs, and identifying risks. |

---

## Epic 1: Customer Registration

### US-001: Submit basic customer information

As a customer,  
I want to enter my name and phone number,  
So that my order can be identified and tracked correctly.

**Acceptance Criteria**

| ID | Criteria |
|---|---|
| AC-001 | Customer name must be required. |
| AC-002 | Customer phone number must be required. |
| AC-003 | Submitted customer information must appear in the response sheet. |

---

### US-002: Identify returning customers

As a returning customer,  
I want my order to be associated with my existing contact information,  
So that the operations team can avoid duplicate or confusing records.

**Acceptance Criteria**

| ID | Criteria |
|---|---|
| AC-001 | Returning customers must be identifiable by name and phone number. |
| AC-002 | Duplicate names must be easier to detect using phone number or another unique field. |
| AC-003 | The system should reduce confusion when two customers share the same name. |

---

### US-003: Register new customers

As a new customer,  
I want to provide all required information for my first order,  
So that my order can be processed without missing delivery or contact details.

**Acceptance Criteria**

| ID | Criteria |
|---|---|
| AC-001 | New customers must provide required registration information. |
| AC-002 | Missing required fields must block form submission. |
| AC-003 | New customer records must be visible for review before production planning. |

---

## Epic 2: Order Type Selection

### US-004: Submit a weekly order

As a customer,  
I want to submit a weekly order,  
So that I can receive products for the full weekly flow.

**Acceptance Criteria**

| ID | Criteria |
|---|---|
| AC-001 | Weekly order option must be available. |
| AC-002 | Weekly order selection must display the correct weekly flow. |
| AC-003 | Weekly orders must be clearly separated from individual orders in the response sheet. |

---

### US-005: Submit an individual order

As a customer,  
I want to submit an order for one or more specific days,  
So that I only receive the products I selected.

**Acceptance Criteria**

| ID | Criteria |
|---|---|
| AC-001 | Individual order option must be available. |
| AC-002 | The form must allow the customer to select specific days. |
| AC-003 | Individual orders must only affect selected days in production planning. |

---

## Epic 3: Product and Complement Selection

### US-006: Select products

As a customer,  
I want to select the products included in my order,  
So that the operations team knows what to prepare.

**Acceptance Criteria**

| ID | Criteria |
|---|---|
| AC-001 | Product selection must be required when applicable. |
| AC-002 | Selected products must be saved correctly in the response sheet. |
| AC-003 | Missing product selection must block submission when required. |

---

### US-007: Select complements or preferences

As a customer,  
I want to select complements and preferences,  
So that my order matches my selected configuration.

**Acceptance Criteria**

| ID | Criteria |
|---|---|
| AC-001 | Complement options must be visible in the correct order flow. |
| AC-002 | Selected complements must remain associated with the correct customer. |
| AC-003 | Complement data must be available for production planning. |

---

## Epic 4: Customer Preferences and Notes

### US-008: Add special preferences

As a customer,  
I want to add special preferences or notes,  
So that the operations team can review them before production.

**Acceptance Criteria**

| ID | Criteria |
|---|---|
| AC-001 | Customer notes must be saved in the response sheet. |
| AC-002 | Notes must remain linked to the correct customer. |
| AC-003 | Critical notes must be visible before production planning starts. |

---

### US-009: Track preference types

As an operations admin,  
I want customer preferences to be clearly visible,  
So that production mistakes can be reduced.

**Acceptance Criteria**

| ID | Criteria |
|---|---|
| AC-001 | Preferences must be visible in the order review process. |
| AC-002 | Preferences must be included in production outputs when relevant. |
| AC-003 | Missing or unclear preferences should be flagged for review. |

---

## Epic 5: Payment Status

### US-010: Capture payment method

As an operations admin,  
I want to capture the payment method or payment status,  
So that orders can be reviewed before production planning.

**Acceptance Criteria**

| ID | Criteria |
|---|---|
| AC-001 | Payment method or status must be captured. |
| AC-002 | Payment status must be visible in the response sheet. |
| AC-003 | Pending payments must be easy to identify. |

---

### US-011: Review unconfirmed payments

As an operations admin,  
I want to identify orders with pending payment status,  
So that they can be reviewed before final production totals are generated.

**Acceptance Criteria**

| ID | Criteria |
|---|---|
| AC-001 | Orders with pending payment status must be flagged for review. |
| AC-002 | Pending payment orders should not be treated as fully confirmed without review. |
| AC-003 | Payment status must be included in the production planning validation process. |

---

## Epic 6: Production Planning

### US-012: Generate daily production totals

As a production team member,  
I want to see daily production totals,  
So that I know how many units must be prepared each day.

**Acceptance Criteria**

| ID | Criteria |
|---|---|
| AC-001 | Daily production totals must be based on confirmed order records. |
| AC-002 | Weekly and individual orders must be counted correctly. |
| AC-003 | Totals must match the number of confirmed orders for each day. |

---

### US-013: Identify production inconsistencies

As an operations admin,  
I want to identify inconsistencies in production totals,  
So that errors can be corrected before production starts.

**Acceptance Criteria**

| ID | Criteria |
|---|---|
| AC-001 | Inconsistent totals must be flagged for review. |
| AC-002 | Orders with missing required data must be reviewed before being included in final totals. |
| AC-003 | Production totals must be traceable back to order records. |

---

## Epic 7: Weekly Requisition Generation

### US-014: Generate weekly requisitions

As a purchasing or requisition user,  
I want to generate weekly requisitions based on production totals,  
So that required supplies can be estimated accurately.

**Acceptance Criteria**

| ID | Criteria |
|---|---|
| AC-001 | Requisition totals must be based on confirmed production quantities. |
| AC-002 | Requisition outputs must reflect daily production needs. |
| AC-003 | Incomplete or unconfirmed records must be flagged before final requisition generation. |

---

### US-015: Review requisition accuracy

As an operations admin,  
I want to review requisition outputs before using them,  
So that calculation or data errors can be corrected.

**Acceptance Criteria**

| ID | Criteria |
|---|---|
| AC-001 | Requisition outputs must be reviewable. |
| AC-002 | Requisition totals must be traceable to production totals. |
| AC-003 | Any unusual quantity should be flagged for manual review. |

---

## Epic 8: AI-Assisted Validation and Automation

### US-016: Detect incomplete records with AI assistance

As a QA tester,  
I want to use AI-assisted validation to detect incomplete records,  
So that data quality issues can be identified faster.

**Acceptance Criteria**

| ID | Criteria |
|---|---|
| AC-001 | AI-assisted validation should identify missing required fields. |
| AC-002 | Flagged records must be reviewed before final production planning. |
| AC-003 | AI output must be treated as a support tool, not as the only source of truth. |

---

### US-017: Detect duplicate or inconsistent records

As a QA tester,  
I want AI-assisted validation to flag duplicate or inconsistent records,  
So that the operations team can review possible errors before production.

**Acceptance Criteria**

| ID | Criteria |
|---|---|
| AC-001 | Duplicate names should be flagged when unique fields are unclear. |
| AC-002 | Inconsistent order data should be highlighted for review. |
| AC-003 | Final decisions must be confirmed manually by the operations admin. |

---

### US-018: Generate production and requisition summaries

As an operations admin,  
I want AI-assisted automation to generate production and requisition summaries,  
So that weekly planning can be faster and less error-prone.

**Acceptance Criteria**

| ID | Criteria |
|---|---|
| AC-001 | The system should generate a production summary from structured order data. |
| AC-002 | The system should generate a requisition summary from production totals. |
| AC-003 | The generated summary must include alerts for missing, duplicate, or inconsistent data. |

---

## Traceability Notes

These user stories will be used to design:

- Smoke test scenarios
- Sanity test scenarios
- Functional test cases
- Negative test cases
- Regression test scenarios
- Bug reports
- Risk matrix items
- AI-assisted validation scenarios