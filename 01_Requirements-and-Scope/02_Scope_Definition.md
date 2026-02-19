# Scope Definition

## Project Coverage Status

This project follows a phased implementation approach.
Core purchase flow modules are prioritised first, with extended modules planned in stages.

Current coverage status is clearly defined below.

---

## Fully Covered (Completed Till US17)

### EP1 – User Authentication & Account Access
- User Registration
- Mobile Number Login
- OTP Validation
- Resend OTP
- Login Completion Navigation
- Logout
- Authenticated Access to My Account

### EP2 – Product Browsing & Discovery
- Search (Keyword)
- Category Navigation
- Brand Navigation
- Filter Products
- Sort Products
- Product Listings
- Product Detail Navigation
- Product Detail Page
- Wishlist / Favorites
- Product Variation Selection

### EP3 – Product Purchase & Checkout (Partial)
- Add to Bag (US17)

---

## In Progress / Planned Coverage

### EP3 – Product Purchase & Checkout (Remaining)
- Cart Management
- Cart Page & Price Breakdown
- Coupons & Discounts
- Checkout Review
- Address Selection & Management
- Payment Method
- Payment Processing & Handling
- Order Confirmation

### EP4 – Order & Account Management (Light Coverage Planned)
- Account Overview
- Order Details (Read-Only)
- Wallet (Presence Check)
- Invite Friends / Referral
- View Rewards
- Manage Personal Information
- Manage Address Book
- View Saved Payment Methods

### EP5 – Customer Support & FAQs (Light Coverage Planned)
- FAQ Page Access
- Customer Care Navigation
- Support Channel Visibility

### EP6 – Offers & Discounts (Light Coverage Planned)
- Offer Banner Visibility
- Offer-Based Navigation

### EP7 – Social Media & External Links (Light Coverage Planned)
- Social Media Redirection
- Footer Navigation Links

---

## Out of Scope

- Admin panel functionality
- Backend database-level validation
- Real payment gateway integration
- Mobile application testing
- Security penetration testing
- Performance testing 

---

## Assumptions

- OTP validity is assumed to be 10 minutes.
- System uses server-side OTP validation.
- Payment flow is simulated up to logical confirmation.
