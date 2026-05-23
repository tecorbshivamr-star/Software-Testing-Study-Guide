# How to Write a Perfect Bug Report

A pristine bug report guarantees that developers can reproduce the bug immediately without asking endless follow-up questions.

---

## 7 Elements of a Solid Bug Report

### 1. Clear, Actionable Title
State exactly what happens and under what conditions.
- ❌ *Bad:* "Checkout is broken"
- ✅ *Good:* "React crash (White Screen of Death) when clicking checkout with an empty cart"

### 2. Environment Details
State exactly where the issue occurred:
- OS (e.g., macOS Sonoma)
- Browser/Version (e.g., Chrome 124.0)
- Environment (e.g., QA Staging Build #342)

### 3. Step-by-Step Reproduction
Write simple, numbered steps. Assume the reader has zero context.
1. Navigate to `/products`.
2. Add "Running Shoes" to the cart.
3. Open the checkout drawer.
4. Click **Checkout**.

### 4. Expected vs Actual Results
Be highly descriptive:
- **Expected:** Redirection to payment page `/checkout/payment`.
- **Actual:** Redirection fails, spinner spins infinitely, console shows `TypeError: Cannot read properties of undefined (reading 'price')`.

### 5. Proof / Attachments
Always provide visual proof:
- Screenshots (highlighting the error area)
- Screen recordings (Loom or WebM)
- Console/Network logs (`.har` or `.log` file)

### 6. Isolation Clues (If Any)
If you did additional checks, write them down:
- *Note:* "This issue only happens when using Safari; Chrome works perfectly."

---

## 📌 Key Takeaways
- If a developer cannot reproduce the bug, they will close it as **"Cannot Reproduce"**.
- Provide log traces—never just a screenshot of a broken page without console logs.
