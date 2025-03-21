# Monefy Android Test Automation

This framework automates end-to-end (E2E) tests for the Monefy Android app.

## The Setup
To prepare the environment for running the tests:
1. **Prerequisites**:
   - **Java 11**: Required for compiling and running the Java-based framework.
   - **Maven**: Used for dependency management and building the project.
   - **Appium Server**: For interacting with the Android emulator (install via `npm install -g appium` if not using Docker).
   - **Android SDK**: With an emulator (e.g., `emulator-5554`) configured.
   - **Monefy APK**: Must be installed on the emulator (download from Google Play or an APK source).

2. **Clone the Repository**:


3. **Install Dependencies**:
- Run the following command to download all required libraries (Appium, Cucumber, TestNG, etc.) specified in `pom.xml`:


4. **Start Appium Server** (if not using Docker):
- Launch Appium locally:


## How to Run Tests
To execute the automated tests:
1. **Start the Emulator**:
- Ensure the Android emulator is running with Monefy installed:


2. **Run the Tests**:
- From the `Task2` directory, execute:

- This triggers the Cucumber TestNG runner, executing all scenarios in the feature files (`SubscribeFlow.feature`, `ExpenseFlow.feature`, `BudgetFlow.feature`).

3. **View the Test Report**:
- After execution, find the HTML report at:

- Open it in a browser to review test results (e.g., pass/fail status for each flow).

## Approach and Why You Chose That Particular Tech Stack
### Approach
- **Focus**: The framework tests three critical E2E flows of the Monefy app:
- Subscription and autopay activation.
- Adding an expense with a category and verifying total balance.
- Setting a budget and tracking remaining balance.
- **Structure**:
- **Feature Files**: Define user flows in Gherkin (e.g., `PetCrud.feature`), ensuring readability and collaboration.
- **Page Objects**: `HomePage.java`, `SubscriptionPage.java`, and `BudgetPage.java` encapsulate UI interactions using the Page Object Model (POM).
- **Step Definitions**: `MonefySteps.java` implements Gherkin steps with Appium, leveraging parameterized steps for reusability.
- **Test Runner**: `TestRunner.java` integrates Cucumber with TestNG for execution and reporting.
- **Scalability**: POM separates UI logic from tests; parameterized steps (e.g., expense with category) allow easy addition of new scenarios via feature files.
- **Maintainability**: Reusable steps and modular design reduce duplication; Gherkin syntax simplifies updates.
- **Dockerization**: A `Dockerfile` is included to containerize Appium and test execution, ensuring consistency.

### Tech Stack Choice
- **Appium**: Chosen as the mobile automation standard, supporting Android and integrating seamlessly with Java for driving the Monefy app.
- **Cucumber**: Selected for BDD, providing Gherkin syntax that enhances test readability and supports parameterized, reusable steps, aligning with best practices.
- **Java**: A robust, widely-used language that integrates well with Appium, Cucumber, and Maven, leveraging my expertise from prior tasks.
- **Maven**: Used for dependency management and build automation, ensuring a standardized, scalable project structure.
- **TestNG**: Preferred for its robust execution and reporting capabilities, consistent with the framework’s needs and prior tasks.

## Docker Instructions (Bonus)
For a containerized execution:
1. **Build the Docker Image**:

2. **Run Tests in Container**:
- Ensure the emulator is running on the host and Appium can connect:

- The container starts Appium and runs `mvn test`, outputting results to `reports/test-report.html`.

## Test Execution Report
- Generated as `reports/test-report.html` via Cucumber’s HTML plugin, detailing the pass/fail status of each E2E scenario.