# Known Limitations & Assumptions

## 1. Environment Limitations

This project was executed on a live production e-commerce website modeled after AJIO.  
As a result, the following constraints existed:

- No backend or database access  
- No access to server logs  
- No visibility into API responses  
- No control over OTP generation logic  
- No ability to simulate backend service failures  
- No internal payment gateway configuration access  

All validations were performed strictly based on observable UI behavior and system responses.

---

## 2. Test Data Constraints

Since testing was performed on a live production environment:

- Registered mobile numbers were limited to controlled test accounts.
- OTP behavior was validated using real-time received OTPs.
- No database resets or controlled test data seeding were possible.
- Scenarios requiring specific account states (e.g., email already linked to another account) were validated only when reproducible using available data.
- Inventory availability depended on real-time product stock and could not be manipulated.

---

## 3. Functional Assumptions

The following assumptions were made during execution:

- Mobile number validation rules apply consistently to both login and registration flows.
- Country code handling is internal and restricted to Indian mobile numbers.
- OTP validity window is approximately 10 minutes based on observed behavior.
- Generating a new OTP invalidates the previously generated OTP.
- Session persistence is managed via browser-based authentication mechanisms.
- Product pricing and discounts reflect real-time production configurations.

---

## 4. Non-Functional Testing Exclusions

The following areas were intentionally excluded from scope:

- Performance and load testing  
- Security testing (e.g., penetration testing, vulnerability scanning)  
- API-level validation  
- Database integrity validation  
- Full cross-browser compatibility matrix  
- Cross-device mobile application testing  
- Accessibility compliance validation (WCAG)  

The primary focus remained on functional validation of the end-to-end purchase journey.

---

## 5. Payment & Order Processing Constraints

- Real payment gateway integrations could not be fully controlled or simulated.
- Payment timeout and retry scenarios were validated only from observable UI behavior.
- Duplicate order prevention was validated at UI level only.
- Email and SMS confirmation verification was limited to delivery confirmation observation, not backend message logs.

---

## 6. Residual Risk Acknowledgment

Due to the above limitations, the following residual risks remain:

- Backend validation inconsistencies not visible at UI level  
- API-level error handling gaps  
- Security vulnerabilities not detectable through functional UI testing  
- Data integrity issues requiring database-level validation  

These risks were acknowledged and accepted as outside the defined project scope.

---
