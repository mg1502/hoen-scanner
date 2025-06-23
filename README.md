# Hoen Scanner 🐚

+## Getting Started
+
+1. Fork this repository on GitHub.
+2. Clone your fork:
+   ```bash
+   git clone https://github.com/<your-username>/hoen-scanner.git
+   cd hoen-scanner
+   ```
+3. (Optional) Open the project in IntelliJ and let it import the Maven project.
+
## Prerequisites

- Java 11 or higher
- Maven 3.x
- Git

## Building the Project

```bash
mvn clean package
```

## Running the Service

Kill any process on port 8080 (if needed):

```bash
lsof -ti TCP:8080 | xargs -r kill -9
```

Start the Dropwizard application:

```bash
java -jar target/hoen-scanner-1.0-SNAPSHOT.jar server config.yml
```

You should see a banner:

```
================================================================================
                           Welcome to Hoen Scanner!
================================================================================
```

## Testing the `/search` Endpoint

Use `curl` or Postman to send a POST request:

```bash
curl -X POST http://localhost:8080/search \
  -H "Content-Type: application/json" \
  -d '{"city":"petalborough"}'
```

Expected response: a JSON array of matching rental cars and hotels in the specified city.

---

Feel free to try other cities like `rustburg` or `shaleport` (lowercase) to verify functionality.