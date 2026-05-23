# HTML CSS & XPath Locators Cheatsheet

Quick reference for finding UI elements in automation frameworks (Selenium, Playwright, Cypress).

---

## 1. CSS Selectors (Preferred for speed)

| Target | CSS Syntax | Example `<input id="email" class="form-input login-field" name="user_email">` |
|---|---|---|
| **ID** | `#id_value` | `#email` |
| **Class** | `.class_value` | `.form-input` or `.login-field` |
| **Multiple Classes** | `.class1.class2` | `.form-input.login-field` |
| **Tag Name** | `tagname` | `input` |
| **Attribute (Exact)** | `[attribute='value']` | `[name='user_email']` |
| **Attribute (Contains)** | `[attribute*='value']` | `[name*='email']` |
| **Attribute (Starts With)**| `[attribute^='value']` | `[name^='user']` |
| **Attribute (Ends With)** | `[attribute$='value']` | `[name$='mail']` |

**CSS Combinators (Relationships):**
- **Direct Child:** `div > button` (Selects buttons immediately inside a div).
- **Descendant:** `form input` (Selects all inputs anywhere inside a form).
- **Next Sibling:** `h1 + p` (Selects the paragraph immediately following an h1).

---

## 2. XPath Selectors (Powerful, Bidirectional)

**Basic Syntax:** `//tagname[@attribute='value']`

| Target | XPath Syntax | Example `<button type="submit" id="login-btn">Log In</button>` |
|---|---|---|
| **Absolute Path (Bad)** | `/html/body/div/button` | `/html/body/div/button` |
| **Relative Path (Good)**| `//tagname[@attr='value']` | `//button[@id='login-btn']` |
| **Any Tag** | `//*[@attr='value']` | `//*[@id='login-btn']` |
| **Text (Exact)** | `//tagname[text()='value']`| `//button[text()='Log In']` |
| **Text (Contains)** | `//tag[contains(text(),'val')]`| `//button[contains(text(),'Log')]` |
| **Attribute (Contains)**| `//tag[contains(@attr,'val')]`| `//button[contains(@id,'login')]` |
| **Multiple Attributes** | `//tag[@attr1='v1' and @attr2='v2']` | `//button[@type='submit' and @id='login-btn']` |

**XPath Axes (Navigating up/down the tree):**
- **Parent:** `//button[@id='login-btn']/parent::div`
- **Following Sibling:** `//label[text()='Email']/following-sibling::input`

---

## 3. Selenium Python Syntax Mapping

```python
# CSS Selector
driver.find_element(By.CSS_SELECTOR, "#email")
driver.find_element(By.CSS_SELECTOR, "div.container > button.submit")

# XPath
driver.find_element(By.XPATH, "//button[text()='Log In']")
driver.find_element(By.XPATH, "//input[@name='password']")
```

## 4. Playwright Python Syntax Mapping

```python
# Playwright automatically detects CSS or XPath based on the string format!
page.locator("#email")
page.locator("//button[text()='Log In']")

# Playwright specific text locator
page.locator("text=Log In") 
```

## 5. Cypress Syntax Mapping

```javascript
// Cypress exclusively uses CSS selectors (and jQuery extensions)
cy.get('#email')
cy.get('button:contains("Log In")') // jQuery extension for text
```
