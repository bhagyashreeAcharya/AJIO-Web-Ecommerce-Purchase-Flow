# BUG-002 : Thumbnail images Fail to load for newly added product accessed via “What’s New” sort

## Bug Details
- **Bug ID:** BUG-002
- **Module:** Product Detail Page (PDP)
- **Project:** AJIO Web – E-commerce Purchase Flow 

## Description
When a newly added product is accessed from the Product Listing Page using the **Sort > What's New** option, the Product Detail Page loads successfully and displays the main product image. However, the thumbnail images fail to load and are shown as blank placeholders, preventing users from viewing alternate product images.

## Environment
- Application: AJIO Web (https://www.ajio.com)
- Browser: Chrome v121
- OS: Windows 10
- User Type: Logged-in / Logged-out user

## Preconditions
- Application is launched and accessible
- User may be logged in or logged out
- Newly added products are available in the catalog

## Steps to Reproduce
1. Navigate to the Product Listing Page
2. Apply **Sort** option → **What's New**
3. Select a newly added product from the list
4. Observe the thumbnail images on the Product Detail Page

## Expected Result
- Product Detail Page should display correct product information
- Thumbnail images should load correctly
- Product images, brand name, title, price, discount, variations, and details should be displayed correctly

## Actual Result
- Product Detail Page opens successfully
- Thumbnail images do not load and appear as blank placeholders
- Alternate product images are not accessible via thumbnails

## Severity
Medium

## Priority
Medium

## Impact
- Users may be confused due to mismatched product visuals
- Reduces trust in product accuracy
- Can lead to incorrect purchase decisions or drop-off

## Attachments
- 🖼️ Thumbnail images not loading – view 1: [View Screenshot](../../07_Test-Evidence/BUG-002/BUG-002_PDP_Thumbnails_Not_Loading_1.png)
- 🖼️ Thumbnail images not loading – view 2: [View Screenshot](../../07_Test-Evidence/BUG-002/BUG-002_PDP_Thumbnails_Not_Loading_2.png)
- 🖼️ Thumbnail images not loading – view 3: [View Screenshot](../../07_Test-Evidence/BUG-002/BUG-002_PDP_Thumbnails_Not_Loading_3.png)
- 🖼️ Thumbnail images not loading – view 4: [View Screenshot](../../07_Test-Evidence/BUG-002/BUG-002_PDP_Thumbnails_Not_Loading_4.png)

