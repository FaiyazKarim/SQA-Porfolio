# Registration Module — Test Plan

## 1. Document Information

| Field | Details |
|---|---|
| Project Name | Registration Module QA Testing |
| Module | User Registration |
| Document Type | Test Plan |
| Testing Type | Manual Functional Testing |
| Test Design Techniques | Equivalence Partitioning, Boundary Value Analysis |
| Test Environment | Windows / Google Chrome |
| Prepared By | QA Tester |
| Document Status | Completed for documented test scope |

---

## 2. Introduction

### 2.1 Purpose

The purpose of this test plan is to define the scope, objectives, approach, environment, responsibilities, entry criteria, exit criteria, risks, and deliverables for testing the user registration module.

The plan provides a structured approach to verifying registration functionality and documenting defects found during testing.

### 2.2 Project Overview

The registration module allows users to create an account by providing a username, email address, password, and confirm password.

The application should validate user inputs, reject invalid or incomplete data, and allow registration when all required conditions are satisfied.

### 2.3 Testing Objectives

The primary objectives are to:

- Verify that required fields are validated correctly.
- Verify username and password minimum-length requirements.
- Verify email format validation.
- Verify that Password and Confirm Password match.
- Verify successful registration with valid inputs.
- Identify and document defects.
- Retest defects after fixes.
- Perform regression testing on related functionality.
- Maintain traceability between requirements and test cases.
- Provide an evidence-based summary of test results.

---

## 3. Scope of Testing

### 3.1 In Scope

The following functionality is included in this test cycle:

1. Username required-field validation.
2. Email required-field validation.
3. Email format validation.
4. Password required-field validation.
5. Password minimum-length validation.
6. Confirm Password required-field validation.
7. Password and Confirm Password matching.
8. Username minimum-length validation.
9. Successful registration with valid inputs.
10. Retesting after defect fixes.
11. Focused regression testing of related registration scenarios.

### 3.2 Out of Scope

The following functionality is excluded from this test cycle:

1. Login functionality.
2. Login credential validation.
3. Successful login.
4. Forgot password and account recovery.
5. Email delivery or email verification.
6. Security and penetration testing.
7. Performance and load testing.
8. Compatibility testing across multiple browsers and operating systems.

These areas would require separate test coverage.

---

## 4. Requirements Under Test

The following requirements form the basis of the documented test cases.

| Requirement ID | Requirement |
|---|---|
| R-001 | Username is mandatory and must contain at least 8 characters. |
| R-002 | Email is mandatory and must use a valid email format. |
| R-003 | Password is mandatory and must contain at least 8 characters. |
| R-004 | Confirm Password is mandatory and must match Password. |
| R-005 | Successful registration should display a success message and redirect the user to the login page. |

**Note:** These are the requirements used for this training project. In a professional project, requirements should be confirmed against approved specifications or acceptance criteria.

---

## 5. Test Approach and Strategy

### 5.1 Functional Testing

Verify that each registration field behaves according to its requirement and that valid inputs allow the registration process to proceed.

### 5.2 Positive Testing

Verify that valid data is accepted.

Examples:

- Username containing exactly 8 characters.
- Username containing more than 8 characters.
- Password containing exactly 8 characters.
- Valid email format.
- Matching Password and Confirm Password.

### 5.3 Negative Testing

Verify that invalid or incomplete inputs are rejected with appropriate validation messages.

Examples:

- Blank username.
- Blank password.
- Blank email.
- Blank Confirm Password.
- Mismatched passwords.
- Invalid email format.
- Username or password shorter than 8 characters.

### 5.4 Equivalence Partitioning

Divide input data into representative valid and invalid groups.

For example, email inputs can be grouped into:

- Valid email formats.
- Invalid email formats.
- Blank email values.

Representative values from these groups are used to reduce redundant testing.

### 5.5 Boundary Value Analysis

Test values around the minimum-length requirement.

| Field | Below Boundary | At Boundary | Above Boundary |
|---|---|---|---|
| Username | 7 characters | 8 characters | 9 characters |
| Password | 7 characters | 8 characters | 9 characters |

The documented test cases directly cover the username boundary values of 7, 8, and 9 characters, and password values of 7 and 8 characters.

### 5.6 Retesting

After a defect is fixed, rerun the failed test case using the relevant test data to verify the correction.

### 5.7 Regression Testing

Rerun selected existing test cases after a code change or release to check whether previously working functionality has been affected.

The focused regression suite in this project includes TC-006, TC-007, TC-008, and TC-010.

---

## 6. Test Environment

| Component | Configuration |
|---|---|
| Operating System | Windows |
| Browser | Google Chrome |
| Application Type | Web Application |
| Testing Method | Manual |
| Test Data | Valid, invalid, incomplete, and boundary-value inputs |

The exact browser version, application build, and test execution date should be recorded if available.

---

## 7. Test Data Strategy

Test data should cover valid and invalid registration inputs.

| Data Category | Example |
|---|---|
| Blank username | Empty value |
| Valid username at minimum boundary | `FaiyazKa` |
| Username below minimum boundary | `FaiyazK` |
| Username above minimum boundary | `FaiyazKar` |
| Blank email | Empty value |
| Invalid email format | `faiyaz19karimgmail.com` |
| Valid email format | `testuser@example.com` |
| Blank password | Empty value |
| Password below minimum length | `Faiyaz1` |
| Password at minimum length | `Faiyaz12` |
| Blank Confirm Password | Empty value |
| Mismatched passwords | Different Password and Confirm Password values |

The email address `testuser@example.com` is an example reserved for documentation. Use appropriate test accounts when executing against an actual application.

---

## 8. Entry Criteria

Testing can begin when:

- The registration module is accessible.
- The test environment is available.
- Relevant requirements are understood.
- Test scenarios and test cases have been prepared.
- Required test data is available.
- The registration form is sufficiently stable for testing.

If these conditions are not met, the tester should document the blocker and communicate it to the responsible team.

---

## 9. Exit Criteria

Testing for the documented scope can be considered complete when:

- All planned test cases have an execution result.
- Failed test cases have been documented.
- Identified defects have been reported and tracked.
- Fixes have been retested where available.
- The planned focused regression suite has been executed.
- Test results and outstanding risks have been documented.
- A test summary report has been prepared.

Passing these criteria does not prove that the entire application is defect-free.

---

## 10. Roles and Responsibilities

| Role | Responsibilities |
|---|---|
| QA Tester | Analyze requirements, design test cases, execute tests, document evidence, report defects, perform retesting and regression testing, and prepare test reports. |
| Developer | Investigate reported defects, identify root causes, implement fixes, and provide updated builds for verification. |
| Business Analyst / Product Owner | Clarify requirements, confirm expected behavior, and resolve requirement ambiguities. |

For this portfolio exercise, the QA activities are documented as the tester's responsibilities. Actual team assignments should be recorded only when known.

---

## 11. Defect Management Process

Defects are recorded with sufficient information for investigation and reproduction.

### Defect Report Fields

- Defect ID
- Defect title
- Related test case
- Preconditions
- Steps to reproduce
- Test data
- Expected result
- Actual result
- Severity
- Priority
- Environment
- Evidence
- Status
- Retest result

### Defect Workflow

`Open → Assigned → In Progress → Fixed → Ready for Retest → Retest → Closed`

If the defect still occurs during retesting, it should be reopened according to the project's defect workflow.

### Severity and Priority

- **Severity** describes the impact of the defect on the functionality or user experience.
- **Priority** describes how urgently the defect should be addressed.

The final severity and priority should be agreed with the responsible team using the project's classification guidelines.

---

## 12. Risks and Mitigation

| Risk | Potential Impact | Mitigation |
|---|---|---|
| Minimum-length boundaries are not tested | Valid or invalid inputs may be handled incorrectly | Include values below, at, and above the boundary. |
| Validation messages are inconsistent | Users may not understand how to correct input errors | Verify field-specific messages for invalid and missing values. |
| A code change affects existing functionality | Previously passing tests may fail | Execute focused regression tests after relevant changes. |
| Test data conflicts with existing accounts | A valid test may fail for an unrelated reason | Use controlled, unique test data where required. |
| Environment or build information is missing | Results may be difficult to reproduce | Record the browser version, application build, and execution date when available. |
| Requirements are ambiguous | Expected results may be incorrect or disputed | Confirm expected behavior with the product owner or approved specification. |

---

## 13. Test Deliverables

The following deliverables are included in the QA portfolio:

1. Test Plan.
2. Registration Functional Test Cases.
3. Defect Reports.
4. Retesting Results.
5. Regression Test Report.
6. Requirements Traceability Matrix (RTM).
7. Test Summary Report.

---

## 14. Execution and Reporting

The initial execution included 12 test cases.

| Metric | Recorded Result |
|---|---:|
| Total Test Cases | 12 |
| Initially Passed | 9 |
| Initially Failed | 3 |
| Initial Pass Rate | 75% |
| Initial Defects | 3 |
| Additional Defect Found During Regression | 1 |
| Total Recorded Defects | 4 |
| Final Focused Regression Result | 4/4 Passed |

The initial three failures related to generic required-field validation messages for Username, Password, and Email.

During subsequent regression testing, TC-008 exposed an additional defect affecting a valid 8-character username. After the fix, all four selected regression cases passed.

The initial execution and subsequent regression cycle are reported separately because they represent different test runs.

---

## 15. Acceptance and Limitations

This plan defines the scope for the documented manual registration tests. Its conclusions are limited to the stated requirements, test data, environment, and executed test cases.

The testing performed does not include security testing, performance testing, comprehensive browser compatibility testing, or validation of the excluded login and account-recovery functionality.

A broader release decision would require review of the complete test results, unresolved defects, risk acceptance, and any additional release criteria.

---

## 16. Conclusion

This test plan establishes a structured approach to validating the registration module through positive testing, negative testing, equivalence partitioning, boundary value analysis, retesting, and regression testing.

It supports traceable test execution and defect reporting while keeping the testing scope and limitations explicit.

The plan is intended to be read alongside the Registration Test Cases, Defect Reports, Regression Test Report, RTM, and Test Summary Report.
