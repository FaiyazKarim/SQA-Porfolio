# SQA-Porfolio
Portfolio for SQA

# Registration Module — End-to-End Software QA Testing Project

## 📌 Project Overview

This project demonstrates a complete **manual software testing process** for a user registration module.

The objective was to verify that users can successfully register by providing valid information and that the system correctly handles invalid, incomplete, and boundary-value inputs.

The project covers the complete QA workflow from **requirement analysis and test planning to test execution, defect reporting, retesting, regression testing, and test summary reporting**.

---

## 🎯 Testing Objective

The registration module requires users to provide:

* Valid username
* Valid email address
* Password with a minimum length of 8 characters
* Matching confirm password

After successful registration, the system should display a success message and redirect the user to the login page.

---

## 🧪 Testing Scope

### In Scope

* Username validation
* Email validation
* Password validation
* Confirm password validation
* Minimum-length boundary testing
* Successful registration
* Negative testing
* Regression testing
* Retesting after defect fixes

### Out of Scope

* Login functionality
* Login credential validation
* Successful login
* Forgot password/account recovery

---

## 🔍 Testing Techniques

The following testing techniques were applied:

* Functional Testing
* Positive Testing
* Negative Testing
* Equivalence Partitioning (EP)
* Boundary Value Analysis (BVA)
* Error Guessing
* Retesting
* Regression Testing

---

## 📊 Test Execution Summary

| Metric                     | Result |
| -------------------------- | -----: |
| Total Test Cases           |     12 |
| Initially Passed           |      9 |
| Initially Failed           |      3 |
| Initial Pass Rate          |    75% |
| Defects Identified         |      4 |
| Regression Test Cases      |      4 |
| Final Regression Pass Rate |   100% |

The initial execution identified three validation defects. During subsequent regression testing, an additional boundary-related defect was discovered in the username validation.

After the defects were fixed and retested, the affected functionality passed successfully.

---

## 🐞 Defects Identified

### BUG-001 — Incorrect Username Validation Message

When the username field was left blank, the application displayed a generic **"All fields are required"** message instead of a username-specific validation message.

* Severity: Low
* Priority: Medium
* Related Test Case: TC-001
* Status: Closed

### BUG-002 — Incorrect Password Validation Message

When the password field was left blank, the application displayed a generic validation message instead of a password-specific message.

* Severity: Low
* Priority: Medium
* Related Test Case: TC-002
* Status: Closed

### BUG-003 — Incorrect Email Validation Message

When the email field was left blank, the application displayed a generic validation message instead of an email-specific validation message.

* Severity: Low
* Priority: Medium
* Related Test Case: TC-003
* Status: Closed

### BUG-004 — Valid 8-Character Username Incorrectly Rejected

During regression testing, the valid **8-character username boundary value** was incorrectly rejected even though the requirement allowed usernames with 8 or more characters.

* Severity: Medium
* Priority: Medium
* Related Test Case: TC-008
* Testing Technique: Boundary Value Analysis
* Status: Closed

This defect demonstrated the importance of performing regression testing around previously tested boundary conditions after a release or code change.

---

## 🔄 Regression Testing

A focused regression suite was executed after a release/update.

| Test Case | Description                   | Result              |
| --------- | ----------------------------- | ------------------- |
| TC-006    | Invalid email format          | PASS                |
| TC-007    | Username below minimum length | PASS                |
| TC-008    | Username at minimum length    | FAIL → FIXED → PASS |
| TC-010    | Username above minimum length | PASS                |

### Final Regression Result

**4/4 test cases passed after BUG-004 was fixed.**

---

## 🔗 Requirements Traceability

The project includes a Requirements Traceability Matrix (RTM) linking requirements to test cases.

| Requirement                 | Covered By                             |
| --------------------------- | -------------------------------------- |
| Username validation         | TC-001, TC-007, TC-008, TC-009, TC-010 |
| Email validation            | TC-003, TC-006                         |
| Password validation         | TC-002, TC-011, TC-012                 |
| Confirm password validation | TC-004, TC-005                         |
| Successful registration     | TC-008, TC-012                         |

---

## 📁 Project Structure

```text
qa-registration-testing-project/
│
├── README.md
│
├── test-plan/
│   └── Test_Plan.md
│
├── test-cases/
│   └── Registration_Test_Cases.md
│
├── defect-reports/
│   └── Registration_Bug_Reports.md
│
├── regression-testing/
│   └── Regression_Test_Report.md
│
├── requirements-traceability/
│   └── RTM.md
│
└── test-summary/
    └── Test_Summary_Report.md
```

---

## 🛠️ Testing Environment

* Operating System: Windows
* Browser: Google Chrome
* Application Type: Web Application
* Testing Type: Manual Functional Testing

---

## 📦 QA Deliverables

This project contains:

* Test Plan
* Test Scenarios
* Functional Test Cases
* Defect Reports
* Retesting Results
* Regression Test Report
* Requirements Traceability Matrix
* Test Summary Report

---

## 💡 Key QA Skills Demonstrated

Through this project, I practiced:

* Requirement analysis
* Test scenario identification
* Test case design
* Positive and negative testing
* Equivalence Partitioning
* Boundary Value Analysis
* Defect identification
* Severity and priority classification
* Defect lifecycle management
* Retesting
* Regression testing
* Requirements traceability
* Test execution reporting
* QA documentation

---

## 🔄 QA Workflow Demonstrated

```text
Requirements
     ↓
Test Planning
     ↓
Test Scenario Design
     ↓
Test Case Design
     ↓
Test Execution
     ↓
Defect Identification
     ↓
Defect Reporting
     ↓
Developer Fix
     ↓
Retesting
     ↓
Regression Testing
     ↓
Test Summary
```

---

## 📌 Project Outcome

The project demonstrates an end-to-end manual QA workflow rather than isolated test-case writing.

The testing process identified **four defects**, including a boundary-value defect discovered during regression testing. The identified defects were subsequently retested after fixes, and the final regression cycle achieved **4/4 passed test cases**.

This project forms part of my transition toward **Software Quality Assurance and QA Automation**, with further work planned in API testing, Java, JUnit, Selenium, and test automation frameworks.

