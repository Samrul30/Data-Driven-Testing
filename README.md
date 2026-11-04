# Data-Driven Testing (DDT) Using Postman & Newman

## Project Overview

This project demonstrates Data-Driven Testing (DDT) using Postman and Newman to automate API testing of the [Restful-Booker API](https://restful-booker.herokuapp.com/).

The project uses an external CSV dataset containing multiple sets of booking information. Newman executes the same Postman collection with different input data in each iteration, allowing multiple test scenarios to be validated automatically.

The main objective is to reduce repetitive manual testing, improve test coverage, and verify the consistency of API responses using automated assertions.

## Technologies & Tools

- **Postman:** API request creation and test scripting.
- **Newman:** Command-line execution of Postman collections.
- **JavaScript:** Writing automated test assertions.
- **CSV:** External test data source.
- **Newman HTML Extra Reporter:** Generating detailed HTML execution reports.
- **Restful-Booker API:** API under test.

## Project Structure

```text
Data-Driven-Testing/
│
├── DDT_Testing.postman_collection.json
├── Dataset_For_DDT.csv
├── DDT_Report.html
├── README.md
└── .gitignore
```

Note: The Postman environment file is excluded from the public repository to avoid exposing sensitive variables.

## API Information

**Base URL:**
```text
https://restful-booker.herokuapp.com
```

**Endpoint:**
```http
POST /booking
```

**HTTP Method:** POST

**Purpose:** Create a new booking using different sets of input data.

## Dataset Information

The project uses `Dataset_For_DDT.csv` as the external test data source.

The dataset contains six different sets of booking information.

| Variable | Description |
|---|---|
| fName | Customer's first name |
| lName | Customer's last name |
| tprice | Total booking price |
| boole | Deposit payment status |
| checkIndata | Check-in date |
| checkOutdata | Check-out date |
| needs | Additional booking requirements |

Each CSV row represents one test iteration.

## Test Scenarios & Assertions

The Postman collection contains 10 automated assertions:

| No. | Test Scenario | Validation |
|---|---|---|
| 1 | Status Code | Verify HTTP status code is 200 |
| 2 | Response Time | Verify response time is within the expected limit |
| 3 | Response Size | Verify response size is within the expected limit |
| 4 | First Name | Verify returned first name matches input data |
| 5 | Last Name | Verify returned last name matches input data |
| 6 | Total Price | Verify returned price matches input data |
| 7 | Deposit Paid | Verify deposit status matches input data |
| 8 | Check-in Date | Verify check-in date matches input data |
| 9 | Check-out Date | Verify check-out date matches input data |
| 10 | Additional Needs | Verify additional needs match input data |

## How to Run the Project

### 1. Install Newman

```bash
npm install -g newman
```

### 2. Install HTML Extra Reporter

```bash
npm install -g newman-reporter-htmlextra
```

### 3. Clone the Repository

```bash
git clone https://github.com/Samrul30/Data-Driven-Testing.git
```

### 4. Navigate to the Project Folder

```bash
cd Data-Driven-Testing
```

### 5. Configure the Postman Environment

Import `DDT_Testing.postman_collection.json` into Postman and configure the required environment variables.

Export your environment as:

```text
DDT_Environment.postman_environment.json
```

Keep this file in your local project folder. Do not commit it if it contains credentials or tokens.

### 6. Execute Data-Driven Tests

```bash
newman run DDT_Testing.postman_collection.json -e DDT_Environment.postman_environment.json -d Dataset_For_DDT.csv
```

### 7. Generate HTML Execution Report

```bash
newman run DDT_Testing.postman_collection.json -e DDT_Environment.postman_environment.json -d Dataset_For_DDT.csv -r cli,htmlextra --reporter-htmlextra-export DDT_Report.html
```

After execution, open `DDT_Report.html` in any web browser to view the detailed test results.

## Test Execution Summary

The following results were obtained during the test execution:

| Metric | Result |
|---|---:|
| Total Iterations | 6 |
| Total Requests | 6 |
| Successful Requests | 6 |
| Failed Requests | 0 |
| Total Assertions | 60 |
| Passed Assertions | 60 |
| Failed Assertions | 0 |
| Average Response Time | 332 ms |
| Total Execution Time | 2.5 seconds |

**Overall Result: 100% of assertions passed.**

## Key Features

- Automated API testing using Newman.
- External CSV-based test data management.
- Multiple test iterations using a single collection.
- Dynamic request body values.
- Automated response validation using JavaScript assertions.
- HTML test report generation.
- Reduced repetitive manual testing efforts.

## Learning Outcomes

Through this project, I gained practical experience in:

- Implementing Data-Driven Testing.
- Integrating CSV datasets with Postman.
- Automating API testing with Newman.
- Writing JavaScript test assertions.
- Executing Postman collections through the command line.
- Generating and analyzing HTML test reports.
- Managing API testing projects using Git and GitHub.

## Author

**Samrul Islam**

Computer Science & Engineering  
BRAC University

GitHub: [@Samrul30](https://github.com/Samrul30)

---

*This project was developed as part of my Software Quality Assurance (SQA) learning and practical API testing activities.*# Data-Driven-Testing
