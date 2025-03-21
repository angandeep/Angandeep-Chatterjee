# Swagger Petstore API Test Automation

This framework automates CRUD tests for the Pet endpoints of the Swagger Petstore API.

## The Setup
To prepare the environment for running the tests:
1. **Prerequisites**:
   - **Java 11**: Required for compiling and running the Java-based framework.
   - **Maven**: Used for dependency management and building the project.
   - **Internet Access**: Necessary to interact with the live Swagger Petstore API at `https://petstore3.swagger.io`.
   - No local server setup is required, as tests target the hosted API instance.

2. **Clone the Repository**:


3. **Install Dependencies**:
- Run the following command to download all required libraries (RestAssured, Cucumber, TestNG, etc.) specified in `pom.xml`:


## How to Run Tests
To execute the automated tests:
1. **Run the Tests**:
- Ensure you’re in the `Task3` directory, then execute:

- This command triggers the Cucumber TestNG runner, executing all scenarios in `PetCrud.feature`.

2. **View the Test Report**:
- After execution, find the HTML report at:

- Open it in a browser to review test results (e.g., pass/fail status for CRUD operations).

## Approach and Why You Chose That Particular Tech Stack
### Approach
- **Focus**: The framework targets the **PET** domain of the Swagger Petstore API, automating CRUD operations (Create, Read, Update, Delete) on the `/pet` endpoint.
- **Structure**:
- **Feature File**: `PetCrud.feature` defines four scenarios in Gherkin, covering each CRUD operation.
- **API Client**: `PetApiClient.java` encapsulates REST calls, separating API logic from test steps for maintainability.
- **Step Definitions**: `PetSteps.java` implements the Gherkin steps using RestAssured, ensuring readability and reusability.
- **Test Runner**: `TestRunner.java` integrates Cucumber with TestNG for execution and reporting.
- **Scalability**: New endpoints (e.g., `/store`, `/user`) can be added by extending `PetApiClient` and creating additional feature files.
- **Maintainability**: Parameterized steps (e.g., pet ID, name) and a modular design reduce duplication and simplify updates.
- **Dockerization**: A `Dockerfile` is included to containerize the test execution, ensuring consistency across environments.

### Tech Stack Choice
- **RestAssured**: Chosen for its fluent, intuitive API testing syntax in Java, making it ideal for RESTful services. It simplifies HTTP requests and response validation compared to raw HTTP clients.
- **Cucumber**: Selected for BDD, providing Gherkin syntax that bridges technical and business stakeholders. It enhances test readability and supports reusable steps, consistent with Task 2’s approach.
- **Java**: A robust, widely-used language that integrates seamlessly with RestAssured, Cucumber, and Maven, leveraging my familiarity from Task 2.
- **Maven**: Used for dependency management and build automation, ensuring a standardized, scalable project structure.
- **TestNG**: Preferred over JUnit for its robust execution and reporting capabilities, aligning with the framework’s reporting needs and prior tasks.

## Docker Instructions (Bonus)
For a containerized execution:
1. **Build the Docker Image**:

2. **Run Tests in Container**:

- The container runs `mvn test` against the live API, outputting results to `reports/test-report.html`.

## Test Execution Report
- Generated as `reports/test-report.html` via Cucumber’s HTML plugin, detailing the pass/fail status of each CRUD scenario.