# BUG-003 : Wishlisted products not displayed on Wishlist page despite being added successfully 

## Bug Details
- **Bug ID:** BUG-003
- **Module:** Wishlist / Favorites
- **Project:** AJIO Web – E-commerce Purchase Flow 

## Description
When a logged-in user adds a product to the wishlist from the Product Detail Page (PDP), the product is correctly marked as wishlisted, and the wishlist state persists across navigation and re-login. However, when navigating to the Wishlist page via the heart icon, the page displays an empty state message instead of the wishlisted product.

## Environment
- Application: AJIO Web (https://www.ajio.com/)
- Browser: Chrome v121
- OS: Windows 10
- User Type: Logged-in user

## Preconditions
- User is logged in
- Product is available in stock
- Wishlist is initially empty

## Steps to Reproduce
1. Search for any product and open its Product Detail Page (PDP)
2. Click on **Save to Wishlist** and observe the confirmation message
3. Verify that the wishlist button changes to **Remove from Wishlist**
4. Click on the **Wishlist (heart) icon** in the header
5. Observe the Wishlist page content

## Expected Result
- The product added to the wishlist should be displayed on the Wishlist page
- Wishlist page should reflect the same wishlist state shown on PDP

## Actual Result
- Wishlist page displays the message **“Your Wishlist is empty!!”**
- Wishlisted product is not displayed, even though PDP shows **Remove from Wishlist**

## Severity
High

## Priority
High

## Impact
- User loses trust in the Wishlist feature
- Saved products appear lost
- Core e-commerce functionality is broken
- Blocks further actions such as removing items or adding products to the cart from the Wishlist

## Attachments
- 📹 Video Evidence (Google Drive): [View Video](https://drive.google.com/file/d/1ANM2A43rIOQdeg7o0nplRVN8cEKVheAq/view?usp=drive_link)
- 🖼️ PDP shows wishlisted state: [View Screenshot](../../07_Test-Evidence/BUG-003/BUG-003_PDP_Wishlisted_State.png)
- 🖼️ Wishlist page empty state: [View Screenshot](../../07_Test-Evidence/BUG-003/BUG-003_Wishlist_Empty_State.png)

