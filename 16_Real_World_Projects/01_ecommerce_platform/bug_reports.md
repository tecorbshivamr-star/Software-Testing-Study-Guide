# E-Commerce Project: Bug Reports

These are examples of professional bug reports logged during the System Testing phase of the E-Commerce project.

---

## BUG-101: Cart subtotal is calculated incorrectly when promo code is applied
- **Status:** Open
- **Severity:** Major (S2)
- **Priority:** High (P1)
- **Module:** Cart / Checkout
- **Environment:** Staging (v1.4.2)
- **Browser:** Chrome v124 (Windows 11)

### Steps to Reproduce
1. Log in to the application.
2. Add "Samsung Galaxy S24" ($1000) to the cart.
3. Add "Phone Case" ($50) to the cart.
4. Total is displayed as $1050.
5. Apply promo code `WELCOME10` (Designed for 10% off total order).

### Expected Result
- The 10% discount ($105) should be applied to the total ($1050).
- Final Total should be **$945**.

### Actual Result
- The 10% discount is only being applied to the *first item* in the cart ($100 off the phone).
- The case remains full price.
- Final Total is displayed as **$950**.

### Attachments
- `cart_calculation_error.png`

---

## BUG-102: "Add to Cart" button overlaps with product image on mobile view
- **Status:** In Progress
- **Severity:** Minor (S3)
- **Priority:** Medium (P2)
- **Module:** Product Listing Page
- **Environment:** QA
- **Device:** iPhone 13 (Safari iOS 16)

### Steps to Reproduce
1. Open the application on an iPhone 13 (or simulate using Chrome DevTools).
2. Navigate to the "Electronics" category page.
3. Scroll down the list of products.

### Expected Result
- The "Add to Cart" button should be distinctly positioned below the product description text.

### Actual Result
- The CSS flexbox breaks, causing the "Add to Cart" button to float upwards and overlap the bottom half of the product image, making the text hard to read.

### Attachments
- `mobile_overlap_safari.mp4`
