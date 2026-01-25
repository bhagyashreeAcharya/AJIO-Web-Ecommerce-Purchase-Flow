# Invalid lower boundary mobile number is accepted without validation at entry point

## Bug Details
- **Bug ID:** BUG-001
- **Module:** Authentication Entry Point / Mobile Number Validation
- **Project:** AJIO Web – E-commerce Purchase Flow (Portfolio Project)

## Description
The system accepts an invalid Indian mobile number below the defined lower boundary and allows the user to proceed without displaying any validation message. As a result, the user is incorrectly routed to the Registration screen. As per the acceptance criteria, only 10-digit mobile numbers starting with digits 6–9 are considered valid.

## Environment
- Application: AJIO Web (https://www.ajio.com)
- Browser: Chrome v121
- OS: Windows 10
- User Type: Logged-out user

## Preconditions
- Application is launched and accessible
- User has clicked on **Sign in / Join AJIO**
- User is on the mobile number entry screen

## Test Data
- Mobile Number Entered: **5999999999**

## Steps to Reproduce
1. Enter the mobile number **5999999999** on the mobile number entry screen
2. Click on **Continue**

## Expected Result
- System should display a validation message indicating an invalid mobile number
- User should remain on the mobile number entry screen

## Actual Result
- No validation message is displayed
- User is allowed to proceed to the Registration screen

## Severity
High

## Priority
High

## Impact
- Boundary value validation rules are violated
- Invalid mobile numbers are accepted silently
- User flow is incorrectly branched
- Can lead to invalid user onboarding and data integrity issues
