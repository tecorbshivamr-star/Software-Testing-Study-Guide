# Pytest HTML Reports

Generating rich, visual reports after test execution is a standard deliverable in any enterprise automation pipeline.

---

## 1. Installing the Plugin
Install the `pytest-html` plugin using pip:
```bash
pip install pytest-html
```

---

## 2. Generating a Report
To generate a clean HTML report during a test run, execute Pytest with the `--html` flag:
```bash
pytest --html=reports/sprint5_execution_report.html --self-contained-html
```

- `--html=reports/report.html`: Specifies the destination path for the HTML report.
- `--self-contained-html`: Packages all styling, CSS, and icons inside a single HTML file—perfect for sharing via email or Slack.

---

## 3. Customizing the Report (Optional)
You can customize the HTML title and metadata by adding configuration blocks to your `conftest.py` file:

```python
# conftest.py
def pytest_html_report_title(report):
    report.title = "QA Automation Execution - Sprint 5"

def pytest_configure(config):
    config._metadata['Project Name'] = 'E-Commerce Platform'
    config._metadata['Tester'] = 'Shivam Rai (Senior QA)'
```

---

## 📌 Key Takeaways
- Visual reports are crucial for stakeholder and manager reviews.
- Package reports as **Self-Contained** so they don't break when shared.
- Connect this command to your **CI/CD pipelines** (e.g., Jenkins, GitHub Actions) to generate reports automatically.
