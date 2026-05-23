# REST Assured (Java API Testing)

## What is REST Assured?
**REST Assured** is a Java DSL (Domain Specific Language) designed to write clean, maintainable, BDD-style automated tests for RESTful web services.

---

## BDD Pattern: Given / When / Then

REST Assured utilizes fluent Gherkin syntax:
- **Given:** Request specifications (headers, query params, request body).
- **When:** HTTP method execution (GET, POST, etc.) on the endpoint.
- **Then:** Assertions on response payload and status codes.

---

## Simple REST Assured Java Test Case

```java
import static io.restassured.RestAssured.*;
import static org.hamcrest.Matchers.*;
import org.testng.annotations.Test;

public class UserApiTest {

    @Test
    public void testValidLoginReturnsToken() {
        // Base URI configuration
        baseURI = "https://qa.api.example.com";

        // JSON payload
        String loginPayload = "{\"email\": \"testuser@qa.com\", \"password\": \"Test@1234\"}";

        given()
            .header("Content-Type", "application/json")
            .body(loginPayload)
        .when()
            .post("/auth/login")
        .then()
            .statusCode(200)
            .time(lessThan(1000L))  // Response time < 1000ms
            .body("token", notNullValue())
            .body("user.email", equalTo("testuser@qa.com"));
    }
}
```

---

## Dependency Setup (Maven pom.xml)

```xml
<dependency>
    <groupId>io.rest-assured</groupId>
    <artifactId>rest-assured</artifactId>
    <version>5.4.0</version>
    <scope>test</scope>
</dependency>
```

---

## 📌 Key Takeaways
- Simple, readable BDD syntax for Java developers and testers.
- Integrates seamlessly with **TestNG** / **JUnit** frameworks.
- Has powerful built-in assertions using **Hamcrest Matchers** or **AssertJ**.
