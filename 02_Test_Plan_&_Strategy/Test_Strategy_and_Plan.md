# Test Strategy & Plan

## 1. Objective

The objective of this project is to validate the core purchase flow of a web-based e-commerce application modeled after a real-world platform (AJIO).

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
- Performance testing  
- Security penetration testing  
- Mobile application testing  
- Automation testing  
- API-level validation  

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
- Acceptance Criteria were written using Given–When–Then format based on observed behavior and expected logic.
- Scope boundaries were defined early to avoid over-expansion.

Special attention was given to ownership of shared flows.

For example, mobile number validation is common to both login and registration. Validation was owned at the entry-point level and treated as a precondition for downstream flows.

This ensured clarity, consistency, and controlled coverage.

---

## 4. Test Design Approach

### 4.1 Scenario Structuring

Test scenarios were written to reflect realistic user actions and expected system outcomes.

Example:
- Verify login behavior for a registered user using a valid Indian mobile number.

Scenarios focused on:

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

---

### 4.3 Validation & Boundary Coverage

Validation rules defined in acceptance criteria were used to derive boundary-focused and rule-based test cases.

Test design techniques were applied selectively where numeric, format-based, time-based, or state-based constraints existed.

---

#### Mobile Number Validation (AC7, AC8)

Defined Rules:

- Must be exactly 10 digits  
- Must start with 6, 7, 8, or 9  
- Country code handled internally  

Boundary values tested:

Lower boundary:
- 5999999999 → Rejected (invalid lower boundary)
- 6000000000 → Accepted (lower valid boundary)
- 6000000001 → Accepted (just above lower boundary)

Upper boundary:
- 9999999998 → Accepted (just below upper boundary)
- 9999999999 → Accepted (upper valid boundary)
- 10000000000 → Rejected (invalid upper boundary – exceeds 10 digits)

Additional validations:

- Less than 10 digits  
- Alphanumeric input  
- Mobile number starting with 0  
- Manual entry of country code (+91 / 91XXXXXXXXXX)  

This ensured enforcement at structural and numeric limits.

---

#### OTP Validation – Format & Time Boundaries (AC11–AC17)

Defined Rules:

- OTP must be 4 digits  
- OTP valid for 10 minutes  
- Resend invalidates previous OTP  

Format boundary coverage:

- 123 → Rejected (less than required digits)
- 12345 → Rejected (more than required digits)
- 12abC → Rejected (non-numeric input)
- Empty input → Validation message displayed

Time boundary coverage:

- Correct OTP within 10 minutes → Accepted
- Correct OTP after 10 minutes → Expired message
- Previously generated OTP after clicking Resend → Rejected

This validated both structural and time-based enforcement logic.

---

#### Session Handling & State Boundaries (AC10, AC21, AC25, AC26)

Logical boundary testing was applied to authentication state transitions:

- Navigating back from OTP screen should not create session.
- Refresh after login should retain session.
- Refresh after logout should not restore session.
- Accessing protected pages after logout should redirect to login.

These tests validated session state boundaries rather than numeric constraints.

---

#### Registration Field Validations (AC3, AC4, AC4A, AC4B)

Validation grouping was applied based on field rules.

Name field:

- Non-alphabetic characters → Rejected  
- Multiple consecutive spaces → Rejected  
- Empty name → Rejected  

Email field:

- Invalid format → Rejected  
- Valid format but non-existing → Accepted  
- Already registered email → Recovery message displayed  

Representative cases were selected per logical input group rather than testing all permutations.

---

#### Product Listing & Filter Behavior (AC45–AC61)

Boundary-style thinking was applied to filter and sort behavior:

- Single filter application  
- Multiple filters combined  
- Removing filters  
- Rapid filter toggling  
- Applying sort after filter  
- Applying filter after sort  
- Persistence after refresh and navigation  

These scenarios validated UI state transitions and dependency handling.

---

#### Product Variation Enforcement (AC102–AC107)

Variation rules were validated through:

- Default selection behavior when only one variation exists  
- Mandatory selection enforcement for secondary variation  
- Attempt to add to bag without required variation  
- Retention of selected variation after refresh/navigation  
- Handling of unavailable (out-of-stock) variations  

This ensured required user inputs were enforced before purchase action.

---

### 4.4 Redundancy Control

Since login and registration share the same mobile entry flow:

- Input validation was tested once in the Registration module.
- Login flow reused validated input as a precondition.
- Invalid mobile number behavior was not duplicated across sheets.

This prevented artificial inflation of coverage and maintained clean ownership mapping.

---

### 4.5 Controlled Negative Isolation

Negative scenarios were structured to isolate one failure condition at a time.

Examples:

- Invalid mobile number tested independently of OTP logic.
- Expired OTP tested with otherwise valid session.
- Invalid invite code tested with valid registration data.
- Add-to-bag failure tested without variation selection only.

This prevented overlapping failures and allowed clear defect attribution.

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

Checkout and payment flows were planned but executed in phased manner based on prioritization strategy.

---

## 6. Test Implementation

During implementation:

- Test cases were documented in structured sheets.
- RTM was maintained at both User Story and Acceptance Criteria levels.
- Execution was performed alongside documentation to allow early defect identification.
- Evidence was captured for failed cases and logged in the defect repository.

---

## 7. Test Execution & Completion

Testing phase was considered complete when:

- All high-priority test cases were executed.
- Critical defects were resolved or formally documented.
- RTM coverage was verified.
- Test execution summary was prepared.
- Known limitations were documented.
