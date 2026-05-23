# Selenium Grid

## What is Selenium Grid?
**Selenium Grid** is a tool that allows you to run test scripts **in parallel across different browsers, operating systems, and machines** simultaneously.

---

## Node & Hub Architecture

```
                                [ HUB ] (Coordinator)
                                   │
              ┌────────────────────┼───────────────────┐
              ▼                    ▼                   ▼
          [ Node 1 ]           [ Node 2 ]          [ Node 3 ]
       Windows 11 / Chrome   macOS 14 / Safari   Ubuntu / Firefox
```

- **Hub:** The central coordinator. It receives test execution requests from your script and routes them to the appropriate browser node based on your request specs.
- **Node:** The individual machine (or Docker container) hosting the actual browser instance.

---

## Running Distributed Tests in Python

To run tests on a Selenium Grid Hub, use `Remote` WebDriver and pass a **Capabilities** parameter:

```python
from selenium import webdriver
from selenium.webdriver.common.options import ArgOptions

# Configure target capability
options = webdriver.ChromeOptions()
options.set_capability("platformName", "Windows 11")
options.set_capability("browserVersion", "latest")

# Coordinate session request through Grid Hub
driver = webdriver.Remote(
    command_executor="http://localhost:4444/wd/hub",
    options=options
)

driver.get("https://www.google.com")
print(driver.title)
driver.quit()
```

---

## Modern Standard: Docker Selenium Grid
Instead of manually configuring physical machines, QA teams spin up entire virtualized grids in seconds using **Docker Compose**:

```yaml
# docker-compose.yml
version: "3"
services:
  selenium-hub:
    image: selenium/hub:4.18.0
    ports:
      - "4444:4444"

  chrome-node:
    image: selenium/node-chrome:4.18.0
    depends_on:
      - selenium-hub
    environment:
      - SE_EVENT_BUS_HOST=selenium-hub
      - SE_EVENT_BUS_PUBLISH_PORT=4442
      - SE_EVENT_BUS_SUBSCRIBE_PORT=4443
```

---

## 📌 Key Takeaways
- Enables **cross-browser** and **cross-platform** matrix verification.
- Cuts test suite execution times drastically via parallel runs.
- Highly scalable using Dockerized cloud networks.
