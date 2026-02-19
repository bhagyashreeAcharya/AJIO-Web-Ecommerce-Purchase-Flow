
# Test Strategy & Plan

## 1. Objective

The objective of this project is to validate the core purchase flow of a web-based e-commerce application inspired by AJIO.

The primary focus is to ensure the reliability and correctness of the revenue-impacting journey:

User Authentication → Product Discovery → Add to Bag → Checkout → Order Confirmation

Priority was given to foundational and high-impact modules before extending to supporting features.

---

## 2. Scope & Constraints

### In Scope
- User Authentication (OTP-based login & registration)
- Product Browsing & Discovery
- Add to Bag functionality
- Cart & Checkout (phased implementation)
- Basic Account and Order visibility (light coverage)

### Out of Scope
- Admin panel functionality
- Backend database-level validation
- Real payment gateway integration
- Performance testing (covered separately)
- Security penetration testing
- Mobile application testing

### Practical Constraints

Since AJIO is a live production application:

- No backend or database access
- No internal logs
- Limited control over test data
- No ability to simulate backend failures

Testing decisions were therefore based entirely on observable UI behavior and system responses.

---

## 3. Test Analysis

Before writing test cases, I explored the live application to understand real user flows and system behavior.

Based on this exploration:

- Functional modules were grouped into epics.
- Features were structured into user stories aligned with business intent.
- Acceptance Criteria were written using Given–When–Then format based on observed behavior and expected business logic.
- Scope boundaries were defined early to avoid over-expansion.

Special attention was given to ownership of shared flows.

For example, mobile number validation is common to both login and registration. Instead of duplicating validation coverage, it was tested once at the entry-point level and treated as a precondition in downstream flows.

This approach ensured clarity, consistency, and controlled coverage.

---

## 4. Test Design Approach

### 4.1 Scenario Structuring

Test scenarios were written to reflect realistic user actions and system outcomes.

Example:
- Verify login behavior for a registered user using a valid Indian mobile number.

Scenarios focused on validating:
- Functional correctness
- Routing logic
- Business rule enforcement
- Dependency behavior

Separate sheets were created for major features (e.g., Registration, Login & OTP) to:

- Maintain clean traceability
- Simplify RTM mapping
- Avoid overlapping validations

---

### 4.2 Test Case Design Principles

While designing test cases, the following principles were followed:

- Every acceptance criterion was covered at least once.
- Related acceptance criteria were combined into a single test case where logically appropriate.
- Shared validations were tested once at their ownership boundary to prevent redundancy.

Example – Mobile Number Validation:

Validation rules:
- Must be 10 digits
- Must start with 6, 7, 8, or 9

Based on this, test cases included:

Valid cases:
- Proper 10-digit Indian mobile numbers

Invalid cases:
- Numbers starting with 0–5
- Less than 10 digits
- More than 10 digits
- Empty input
- Alphanumeric characters
- Attempt to manually enter country code

Boundary Value Analysis and Equivalence Partitioning were applied based on defined validation rules rather than arbitrary combinations.

Negative scenarios were intentionally isolated to ensure clear defect attribution and root cause identification.

---

### 4.3 Redundancy Control

Since login and registration share the same mobile entry flow:

- Input validation was tested once in the Registration module.
- Login flow reused validated input as a precondition.
- Invalid mobile number behavior was not duplicated across multiple sheets.

This prevented artificial inflation of test coverage and maintained clean ownership mapping.

---

### 4.4 OTP Handling

OTP validation included:

- Correct OTP within validity window
- Incorrect OTP
- Expired OTP
- Empty input
- Non-numeric input

Testing focused on system response and user feedback since backend validation logic was not accessible.

---

## 5. Risk-Based Prioritization

Test weightage was assigned based on:

- Business objective (purchase flow priority)
- Revenue impact
- Upstream dependency stability
- Practical constraints of live production testing

High Focus:
- Authentication
- Session handling
- Add to Bag

Medium Focus:
- Filters and sorting

Light Coverage:
- Footer navigation
- External links
- Informational pages

---

## 6. Test Implementation

During implementation:

- Test cases were documented in structured sheets.
- RTM was maintained at both User Story and Acceptance Criteria levels.
- Execution was performed alongside documentation to allow early defect identification.
- Evidence was captured for failed cases and logged in the defect repository.

---

## 7. Test Execution & Completion

Testing was considered stable when:

- All high-priority test cases were executed.
- Critical defects were resolved or documented.
- RTM coverage was verified.
- Test execution summary was prepared.
- Known limitations were documented.
