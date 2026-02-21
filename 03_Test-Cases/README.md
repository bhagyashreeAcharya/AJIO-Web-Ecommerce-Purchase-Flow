# Test Cases – AJIO Web Purchase Flow

This folder contains the structured test case documentation and execution tracking for the AJIO Web Purchase Flow project.

---

## 📂 File Included

### AJIO_Test_Cases_v1.0.xlsx

This Excel file represents the complete functional test design and execution tracking.

It includes:

- Module-wise test case sheets (Registration, Login, OTP, PLP, PDP, Cart, etc.)
- Master Execution sheet with:
  - Test Case ID
  - Module
  - Execution Status (Pass / Fail / Blocked)
  - Test Priority (High / Medium / Low)
  - Linked Defect ID (where applicable)
- Project-level execution summary dashboard
- Requirement impact summary
- Exploratory testing notes (where relevant)

---

## 🧠 Test Case Design Approach

Test cases were designed based on:

- Approved Epics and User Stories
- Acceptance Criteria written in Given–When–Then format
- Business-critical purchase flow prioritization

Key principles followed:

- Each Acceptance Criterion is covered at least once.
- Related ACs are combined into single test cases where logically appropriate.
- Shared validations (e.g., mobile number format) are tested once at ownership boundary to avoid redundancy.
- Negative scenarios are isolated to ensure clear defect attribution.

---

## 🔎 Techniques Applied

Selective test design techniques were applied where applicable:

- Boundary Value Analysis (e.g., mobile number validation)
- Time-bound validation (OTP expiry window)
- State transition validation (session persistence)
- UI behavior and routing verification
- Filter & sort logic validation
- Mandatory field enforcement

Testing was performed strictly at UI level due to production environment constraints.

---

## 📊 Execution Tracking

The Master Execution sheet provides:

- Total unique test case count
- Passed, Failed, and Blocked counts
- Pass percentage (excluding blocked cases)
- Defect mapping for failed scenarios

Each test case is counted once in execution metrics to avoid duplication across shared flows.

---

## 🔗 Traceability

Test cases are mapped in the RTM file:

Requirements → Acceptance Criteria → Test Cases

This ensures full end-to-end traceability and controlled coverage.

---

This file represents the core functional validation effort for the project.Test Cases
