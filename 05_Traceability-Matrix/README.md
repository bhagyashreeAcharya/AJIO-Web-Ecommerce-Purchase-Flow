trace
# Requirements Traceability Matrix (RTM)

This folder contains the end-to-end traceability mapping for the AJIO Web Purchase Flow project.

---

## 📂 File Included

### AJIO_RTM.xlsx

The RTM provides structured mapping between:

Requirement → Acceptance Criteria → Test Cases

This ensures:

- No requirement is left untested
- Every Acceptance Criterion is covered by at least one test case
- No orphan test cases exist without requirement linkage
- Full traceability from business requirement to execution

---

## 🎯 Purpose of RTM

The RTM was created to:

- Validate coverage completeness
- Support impact analysis
- Enable defect root cause tracing
- Prevent scope leakage
- Maintain structured test governance

---

## 🔎 Traceability Structure

Each row in the RTM maps:

- Requirement ID (e.g., REQ-101)
- Acceptance Criteria ID (e.g., AC4)
- Linked Test Case IDs (e.g., TC_REG_18, TC_REG_19)

This structured mapping allows:

- Requirement-level coverage verification
- AC-level validation coverage tracking
- Quick identification of missing coverage

---

## 🧠 Coverage Integrity Check

The following validation checks were performed:

- Every Acceptance Criterion has at least one linked test case.
- Every test case references at least one Acceptance Criterion.
- Shared validations are mapped at ownership boundary to avoid duplication.

---

The RTM represents the formal coverage control layer of this project.
