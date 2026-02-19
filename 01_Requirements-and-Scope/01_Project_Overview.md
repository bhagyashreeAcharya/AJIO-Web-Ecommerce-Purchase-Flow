# Project Overview

## Application Description

This project is a structured QA case study of a web-based e-commerce application inspired by AJIO.  
It focuses on validating core user journeys that directly impact business revenue, including authentication, product discovery, and purchase flow.

The system under test includes modules for:

- User Authentication (OTP-based login & registration)
- Product Browsing & Discovery
- Product Detail Page (PDP)
- Add to Bag & Cart Management
- Checkout & Order Flow (Planned / Partial)
- Basic Account & Order Management (Light Coverage)

The project prioritizes deep validation of core flows before extending to supporting modules.

---

## Business Objective

The primary objective of this testing initiative is to validate the reliability and correctness of the core revenue-generating journey:

User Login → Product Discovery → Add to Bag → Checkout → Order Confirmation

The testing effort ensures:

- Functional correctness
- Validation enforcement
- Controlled session handling
- Traceability between requirements and execution
- Structured defect management

---

## Testing Approach Summary

This project follows a structured Agile-inspired workflow:

- Epics defined based on functional modules
- User Stories broken into testable behaviors
- Acceptance Criteria written using Given–When–Then format
- Test Scenarios derived from business rules
- Detailed Test Cases designed using boundary and negative thinking
- Defects logged with reproducible evidence
- RTM maintained at User Story and Acceptance Criteria level
- Test Execution Summary documented with release recommendation
