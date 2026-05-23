# Automation Testing Interview Q&A

> Covers core automation concepts, Selenium WebDriver, framework design, and coding challenges.

---

## 🔵 Section 1: Automation Fundamentals

**Q1. When should you automate a test?**
- When the test is repetitive (e.g., regression tests).
- When the test involves multiple data sets (Data-driven).
- When the test is complex or time-consuming manually.
- When it needs to be executed across multiple browsers/environments.

**Q2. What test cases should NOT be automated?**
- Exploratory tests.
- Usability or UX tests (visual appeal).
- Tests for features that are constantly changing (unstable UI).
- One-time executing scripts.

**Q3. What is the difference between an Automation Tool and an Automation Framework?**
- **Tool:** A specific software used to execute scripts (e.g., Selenium, Cypress).
- **Framework:** The structured architecture, rules, and best practices built *around* the tool (e.g., POM, Data-Driven, reporting, logging).

**Q4. Explain the Page Object Model (POM).**
POM is a design pattern where each web page has a corresponding class containing its locators and methods (actions).
*Benefits:* Reduces code duplication, improves maintenance (change locator in one place), makes test scripts highly readable.

---

## 🟡 Section 2: Selenium WebDriver

**Q5. Explain the architecture of Selenium WebDriver.**
Language Bindings (Java/Python) $\to$ JSON Wire Protocol (or W3C Protocol) $\to$ Browser Driver (ChromeDriver/GeckoDriver) $\to$ Real Browser.

**Q6. What are the different types of waits in Selenium?**
1. **Implicit Wait:** Global wait. Tells WebDriver to poll the DOM for a certain time before throwing `NoSuchElementException`.
2. **Explicit Wait:** Smart, condition-based wait (e.g., wait until element is clickable). Applies only to a specific element.
3. **Fluent Wait:** A type of explicit wait where you can define the polling frequency and ignore specific exceptions.

**Q7. Why shouldn't you mix Implicit and Explicit waits?**
Mixing them can cause unpredictable timeout durations. If implicit is 10s and explicit is 15s, a failure might take 25 seconds to throw an exception, drastically slowing down test runs.

**Q8. How do you handle dynamic web elements (elements whose IDs change on refresh)?**
- Use XPath `contains()`, `starts-with()`, or `ends-with()`.
- Traverse from a stable parent element down to the dynamic child element.
- Use CSS selectors with prefix/suffix matching (`^=`, `$=`).

**Q9. How do you handle multiple windows or tabs in Selenium?**
Use `driver.window_handles` to get a set of all open window IDs. Then loop through the set and use `driver.switch_to.window(handle)` to switch context.

**Q10. How do you handle iframes?**
You must switch the driver's focus to the iframe before interacting with elements inside it.
`driver.switch_to.frame("frame_id_or_name")`
To switch back: `driver.switch_to.default_content()`

**Q11. How do you scroll down a page in Selenium?**
Selenium doesn't have a direct scroll method, so use JavaScript Executor:
`driver.execute_script("window.scrollTo(0, document.body.scrollHeight);")`

---

## 🔴 Section 3: Framework & CI/CD

**Q12. What is Data-Driven Testing?**
Executing the same test script multiple times using different sets of input data stored in an external file (Excel, CSV, JSON, or DB). In Pytest, this is done using `@pytest.mark.parametrize`.

**Q13. How do you run tests in parallel?**
- Use **Selenium Grid** to distribute tests across multiple nodes.
- Use framework plugins like **pytest-xdist** (Python) or **TestNG parallel execution** (Java).

**Q14. How do you integrate automation with CI/CD?**
Configure a pipeline (Jenkins, GitHub Actions, GitLab CI). The pipeline checks out the code, installs dependencies, runs the test command (e.g., `pytest`), generates an HTML report, and fails the build if assertions fail.

---

*Related: [Manual Testing Q&A](./01_manual_testing_interview_qa.md) | [Selenium Setup Guide](../09_Automation_Testing/selenium/01_selenium_setup_guide.md)*
