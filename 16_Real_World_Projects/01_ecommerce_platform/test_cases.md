# E-Commerce Project: Test Cases

Below is a subset of critical test cases designed for the "QA Demo E-Commerce Platform."

---

## Module: Shopping Cart

### TC_CRT_01: Verify user can add a product to an empty cart
- **Priority:** Critical
- **Pre-conditions:** User is logged in. Cart is empty.
- **Steps:**
  1. Navigate to `/product/iphone-15`.
  2. Click "Add to Cart".
  3. Navigate to `/cart`.
- **Expected:**
  - A success toast message appears.
  - Cart counter icon updates to `1`.
  - `/cart` page displays the iPhone 15 with Quantity = 1 and correct subtotal.

### TC_CRT_02: Verify adding duplicate products increments quantity
- **Priority:** High
- **Pre-conditions:** User is logged in. Cart contains 1x "iPhone 15".
- **Steps:**
  1. Navigate to `/product/iphone-15`.
  2. Click "Add to Cart".
  3. Navigate to `/cart`.
- **Expected:**
  - Product does not appear as two separate line items.
  - Existing line item updates to Quantity = 2.
  - Subtotal correctly doubles.

### TC_CRT_03: Verify inventory limits
- **Priority:** Medium
- **Pre-conditions:** Product "AirPods" has only 3 units in backend stock.
- **Steps:**
  1. Navigate to `/product/airpods`.
  2. Attempt to add 4 units to the cart via the quantity dropdown.
- **Expected:**
  - Dropdown does not allow selecting numbers > 3.
  - If bypassed via API, the server returns `400 Bad Request` with message "Insufficient stock".

---

## Module: Checkout & Payment

### TC_CHK_01: Verify successful payment via Credit Card
- **Priority:** Critical
- **Pre-conditions:** Cart contains items.
- **Steps:**
  1. Navigate to `/checkout`.
  2. Fill in valid shipping address.
  3. Select "Credit Card" payment method.
  4. Enter valid test card details.
  5. Click "Pay Now".
- **Expected:**
  - Payment processes successfully.
  - User is redirected to `/order-success`.
  - Order is saved in the database with status `PAID`.
  - Confirmation email is triggered.

### TC_CHK_02: Verify checkout is blocked with empty shipping fields
- **Priority:** High
- **Steps:**
  1. Navigate to `/checkout`.
  2. Leave "Zip Code" blank.
  3. Click "Continue to Payment".
- **Expected:**
  - Navigation is blocked.
  - Zip Code field turns red with validation error "Zip Code is required."
