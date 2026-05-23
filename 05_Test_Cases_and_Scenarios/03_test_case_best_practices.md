# Test Case Writing Best Practices

Writing good test cases is an art. A poorly written test case leads to confusion, wasted execution time, and false-positive automation scripts.

---

## 1. Keep it Atomic (Single Responsibility)
A test case should test exactly **one** thing.
- ❌ *Bad:* "Login, add item to cart, checkout, and verify email receipt." (If this fails, you don't know which part broke).
- ✅ *Good:* "Verify user can login." $\to$ "Verify user can add item to cart." $\to$ "Verify user can complete checkout."

---

## 2. Be Specific with Test Data
Do not assume the person executing the test knows what "valid data" means. Provide the exact data to use.
- ❌ *Bad:* "Enter a valid email."
- ✅ *Good:* "Enter email: `qa_test_user@gmail.com`."

---

## 3. Clear and Concise Steps
Write steps as direct, imperative commands. Avoid flowery language or long paragraphs.
- ❌ *Bad:* "Now you need to take the mouse and click on the blue submit button at the bottom of the screen."
- ✅ *Good:* "Click the 'Submit' button."

---

## 4. Ensure Independence
Test cases should not depend on the execution of previous test cases. You should be able to run Test Case #50 without having to run #1 through #49 first.
- **How to fix dependencies:** Use the `Pre-conditions` section to establish the required state (e.g., "User is already registered and logged in").

---

## 5. Write the 'Expected Result' for EVERY Step
Don't just write an expected result at the very end of a 10-step test case. Every meaningful action should have a corresponding expected state.
- *Step:* "Click 'Add to Cart'."
- *Expected:* "Cart icon counter increments by 1. A success toast message appears."

---

## 6. Title Naming Conventions
A tester should know exactly what the test does just by reading the title.
- **Format:** `[Action] + [Condition] + [Expected Outcome]`
- ✅ *Good:* `Verify Login fails when password field is left blank.`

---

## 📌 Key Takeaways
- Write test cases assuming the person executing them has never seen the application before.
- **100% Independence** is the golden rule for both manual and automated test cases.
