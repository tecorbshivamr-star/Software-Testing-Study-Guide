# Selenium Locators Guide

Locators are the bread and butter of UI automation. They tell the automation script exactly which HTML elements to click, type into, or verify.

---

## The 8 Standard Selenium Locators

| Locator | Python Syntax | Performance | When to Use |
|---|---|---|---|
| **ID** | `(By.ID, "user-name")` | ⚡ Fastest | Best choice if IDs are unique and static. |
| **Name** | `(By.NAME, "email")` | Fast | Great for form input fields. |
| **Class Name** | `(By.CLASS_NAME, "btn-primary")` | Medium | Excellent for general styling validation. |
| **Tag Name** | `(By.TAG_NAME, "h1")` | Medium | Ideal for counting elements (e.g., links). |
| **Link Text** | `(By.LINK_TEXT, "Log Out")` | Slow | For anchors matching exact text. |
| **Partial Link Text** | `(By.PARTIAL_LINK_TEXT, "Log")` | Slow | For anchors matching partial text. |
| **CSS Selector** | `(By.CSS_SELECTOR, "div.login > button")` | ⚡ Fast | Second-best choice. Fast, flexible, and robust. |
| **XPath** | `(By.XPATH, "//button[@type='submit']")` | Slowest | Fallback for complex relative sibling search. |

---

## XPath vs CSS Selector

| Feature | CSS Selector | XPath |
|---|---|---|
| **Speed** | Extremely fast (Native browser engine) | Slower (Requires custom XML tree scanning) |
| **Complexity** | Simple, clean syntax | Verbose, complex |
| **Traversal** | Downward only (Parent → Child) | Bidirectional (Can traverse back up to Parent) |
| **Text Search** | Cannot select elements by text | Can select by text: `//button[text()='Login']` |

---

## Locating Strategy Best Practices

```
Is there a unique, static ID?
  ├── Yes ──→ Use By.ID
  └── No
       │
Is there a static Name attribute?
  ├── Yes ──→ Use By.NAME
  └── No ──→ Use CSS Selector (Preferred) or XPath (as absolute fallback)
```

### 🔴 Warning: Avoid Absolute XPaths!
- *Bad Absolute XPath:* `/html/body/div[2]/div[1]/form/div/button`
  - **Risk:** Any tiny change in UI structure instantly breaks the script.
- *Good Relative XPath:* `//form[@id='login']//button`

---

## 📌 Key Takeaways
- Prioritize **ID** locators above all else.
- Use **Relative XPaths/CSS selectors** rather than absolute pathways.
- Keep locators isolated as class constants (Page Object Model pattern).
