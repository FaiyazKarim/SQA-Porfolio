# Registration Module — Functional Test Cases

## 1. Project Information

| Field | Details |
|---|---|
| Project | Registration Module QA Testing |
| Module | User Registration |
| Testing Type | Manual Functional Testing |
| Test Design Techniques | Equivalence Partitioning, Boundary Value Analysis, Negative Testing |
| Test Environment | Windows, Google Chrome |
| Test Cases | 12 |
| Initial Execution | 9 Passed, 3 Failed |
| Defects Identified | 4, including 1 found during regression |
| Final Regression Result | 4 Passed out of 4 |

## 2. Test Objective

The objective is to verify that the registration module correctly validates username, email, password, and confirm password fields and allows registration when all required inputs are valid.

### Requirements

- Username must contain at least 8 characters.
- A valid email address must be provided.
- Password must contain at least 8 characters.
- Confirm Password must match Password.
- Required fields must be validated.
- Successful registration should display a success message and redirect the user to the login page.

**Note:** These test cases are based on the registration requirements and observed behavior used in this project. The actual results below reflect the recorded test executions.

---

## TC-001 — Verify Registration with a Blank Username

**Test Case ID:** TC-001

**Priority:** High

**Test Type:** Negative Testing

**Test Technique:** Required-field validation

**Requirement:** Username is mandatory.

### Preconditions
- The registration page is accessible.
- The user is on the registration form.

### Test Data

| Field | Value |
|---|---|
| Username | Blank |
| Email | `testuser@example.com` |
| Password | `Faiyaz123` |
| Confirm Password | `Faiyaz123` |

### Test Steps
1. Open the registration page.
2. Leave the Username field blank.
3. Enter a valid email address.
4. Enter a valid password.
5. Enter the same value in Confirm Password.
6. Click the Register button.
7. Observe the validation message.

### Expected Result
The system should display a username-specific required-field validation message and prevent registration.

### Actual Result
The system displayed the generic message: "All fields are required."

### Initial Test Result
**FAIL**

### Defect Reference
- Defect ID: BUG-001
- Severity: Low
- Priority: Medium

### Retest Result
**PASS** — After the fix, the system displayed the appropriate username validation message.

---

## TC-002 — Verify Registration with a Blank Password

**Test Case ID:** TC-002

**Priority:** High

**Test Type:** Negative Testing

**Test Technique:** Required-field validation

**Requirement:** Password is mandatory.

### Preconditions
- The registration page is accessible.

### Test Data

| Field | Value |
|---|---|
| Username | `FaiyazKarim` |
| Email | `testuser@example.com` |
| Password | Blank |
| Confirm Password | `Faiyaz123` |

### Test Steps
1. Open the registration page.
2. Enter a valid username.
3. Enter a valid email address.
4. Leave the Password field blank.
5. Enter a value in Confirm Password.
6. Click Register.
7. Observe the validation message.

### Expected Result
The system should display a password-specific required-field validation message and prevent registration.

### Actual Result
The system displayed the generic message: "All fields are required."

### Initial Test Result
**FAIL**

### Defect Reference
- Defect ID: BUG-002
- Severity: Low
- Priority: Medium

### Retest Result
**PASS** — After the fix, the system displayed the appropriate password validation message.

---

## TC-003 — Verify Registration with a Blank Email

**Test Case ID:** TC-003

**Priority:** High

**Test Type:** Negative Testing

**Test Technique:** Required-field validation

**Requirement:** Email address is mandatory.

### Preconditions
- The registration page is accessible.

### Test Data

| Field | Value |
|---|---|
| Username | `FaiyazKarim` |
| Email | Blank |
| Password | `Faiyaz123` |
| Confirm Password | `Faiyaz123` |

### Test Steps
1. Open the registration page.
2. Enter a valid username.
3. Leave the Email field blank.
4. Enter a valid password.
5. Enter the matching confirm password.
6. Click Register.
7. Observe the validation message.

### Expected Result
The system should display an email-specific required-field validation message and prevent registration.

### Actual Result
The system displayed the generic message: "All fields are required."

### Initial Test Result
**FAIL**

### Defect Reference
- Defect ID: BUG-003
- Severity: Low
- Priority: Medium

### Retest Result
**PASS** — After the fix, the system displayed the appropriate email validation message.

---

## TC-004 — Verify Registration with a Blank Confirm Password

**Test Case ID:** TC-004

**Priority:** High

**Test Type:** Negative Testing

**Test Technique:** Required-field validation

**Requirement:** Confirm Password is mandatory.

### Preconditions
- The registration page is accessible.

### Test Data

| Field | Value |
|---|---|
| Username | `FaiyazKarim` |
| Email | `testuser@example.com` |
| Password | `Faiyaz123` |
| Confirm Password | Blank |

### Test Steps
1. Open the registration page.
2. Enter a valid username.
3. Enter a valid email address.
4. Enter a valid password.
5. Leave Confirm Password blank.
6. Click Register.
7. Observe the validation message.

### Expected Result
The system should display a Confirm Password validation message and prevent registration.

### Actual Result
The system displayed a Confirm Password validation message.

### Initial Test Result
**PASS**

### Defect Reference
None.

---

## TC-005 — Verify Registration with Mismatched Passwords

**Test Case ID:** TC-005

**Priority:** High

**Test Type:** Negative Testing

**Test Technique:** Input validation

**Requirement:** Password and Confirm Password must match.

### Preconditions
- The registration page is accessible.

### Test Data

| Field | Value |
|---|---|
| Username | `FaiyazKarim` |
| Email | `testuser@example.com` |
| Password | `Faiyaz123` |
| Confirm Password | `Faiyaz12` |

### Test Steps
1. Open the registration page.
2. Enter a valid username.
3. Enter a valid email address.
4. Enter `Faiyaz123` in Password.
5. Enter `Faiyaz12` in Confirm Password.
6. Click Register.
7. Observe the validation response.

### Expected Result
The system should display an error indicating that Password and Confirm Password do not match. Registration should not proceed.

### Actual Result
The system displayed a password-mismatch validation message.

### Initial Test Result
**PASS**

### Defect Reference
None.

---

## TC-006 — Verify Registration with an Invalid Email Format

**Test Case ID:** TC-006

**Priority:** High

**Test Type:** Negative Testing

**Test Technique:** Equivalence Partitioning

**Requirement:** A valid email address must be provided.

### Preconditions
- The registration page is accessible.

### Test Data

| Field | Value |
|---|---|
| Username | `FaiyazKarim` |
| Email | `faiyaz19karimgmail.com` |
| Password | `Faiyaz123` |
| Confirm Password | `Faiyaz123` |

### Test Steps
1. Open the registration page.
2. Enter a valid username.
3. Enter the email address without the `@` symbol.
4. Enter a valid password.
5. Enter the matching confirm password.
6. Click Register.
7. Observe the validation response.

### Expected Result
The system should identify the email format as invalid, display an appropriate validation message, and prevent registration.

### Actual Result
The system displayed an invalid-email validation message.

### Initial Test Result
**PASS**

### Regression Result
**PASS** — The invalid email format continued to be rejected during regression testing.

### Defect Reference
None.

---

## TC-007 — Verify Registration with a Username Below the Minimum Length

**Test Case ID:** TC-007

**Priority:** High

**Test Type:** Negative Testing

**Test Technique:** Boundary Value Analysis

**Requirement:** Username must contain at least 8 characters.

### Preconditions
- The registration page is accessible.

### Test Data

| Field | Value |
|---|---|
| Username | `Faiyaz` (6 characters) |
| Email | `testuser@example.com` |
| Password | `Faiyaz123` |
| Confirm Password | `Faiyaz123` |

### Test Steps
1. Open the registration page.
2. Enter `Faiyaz` as the username.
3. Enter a valid email address.
4. Enter a valid password.
5. Enter the matching confirm password.
6. Click Register.
7. Observe the username validation response.

### Expected Result
The system should reject the username because it contains fewer than 8 characters and display an appropriate validation message.

### Actual Result
The system displayed a username length validation message.

### Initial Test Result
**PASS**

### Regression Result
**PASS** — The system continued to reject the username below the minimum length.

### Defect Reference
None.

---

## TC-008 — Verify Registration with a Username Exactly at the Minimum Length

**Test Case ID:** TC-008

**Priority:** High

**Test Type:** Positive Testing

**Test Technique:** Boundary Value Analysis

**Requirement:** A username containing exactly 8 characters must be accepted.

### Preconditions
- The registration page is accessible.
- The test username is acceptable for registration and does not conflict with an existing account.

### Test Data

| Field | Value |
|---|---|
| Username | `FaiyazKa` (8 characters) |
| Email | `testuser@example.com` |
| Password | `Faiyaz123` |
| Confirm Password | `Faiyaz123` |

### Test Steps
1. Open the registration page.
2. Enter `FaiyazKa` as the username.
3. Enter a valid email address.
4. Enter a valid password.
5. Enter the matching confirm password.
6. Click Register.
7. Observe whether registration succeeds and the user is redirected to the login page.

### Expected Result
The system should accept the 8-character username, display a success message, and redirect the user to the login page.

### Initial Test Execution
**PASS** — The registration was accepted during the initial execution.

### Regression Test Execution
**FAIL** — Following release R1.1, the system incorrectly rejected the valid 8-character username.

### Defect Reference
- Defect ID: BUG-004
- Severity: Medium
- Priority: Medium

### Retest Result
**PASS** — After BUG-004 was fixed, the system accepted the 8-character username and registration completed successfully.

### QA Observation
This test demonstrates why a previously passing boundary test should be included in regression testing after a release or code change.

---

## TC-009 — Verify Registration with a Username One Character Below the Minimum

**Test Case ID:** TC-009

**Priority:** High

**Test Type:** Negative Testing

**Test Technique:** Boundary Value Analysis

**Requirement:** Username must contain at least 8 characters.

### Preconditions
- The registration page is accessible.

### Test Data

| Field | Value |
|---|---|
| Username | `FaiyazK` (7 characters) |
| Email | `testuser@example.com` |
| Password | `Faiyaz123` |
| Confirm Password | `Faiyaz123` |

### Test Steps
1. Open the registration page.
2. Enter `FaiyazK` as the username.
3. Enter a valid email address.
4. Enter a valid password.
5. Enter the matching confirm password.
6. Click Register.
7. Observe the username validation response.

### Expected Result
The system should reject the username because it contains 7 characters and display an appropriate minimum-length validation message.

### Actual Result
The system displayed the username length validation message.

### Initial Test Result
**PASS**

### Defect Reference
None.

---

## TC-010 — Verify Registration with a Username Above the Minimum Length

**Test Case ID:** TC-010

**Priority:** Medium

**Test Type:** Positive Testing

**Test Technique:** Boundary Value Analysis

**Requirement:** A username containing at least 8 characters must be accepted.

### Preconditions
- The registration page is accessible.
- The test username and email are acceptable for registration.

### Test Data

| Field | Value |
|---|---|
| Username | `FaiyazKar` (9 characters) |
| Email | `testuser@example.com` |
| Password | `Faiyaz123` |
| Confirm Password | `Faiyaz123` |

### Test Steps
1. Open the registration page.
2. Enter `FaiyazKar` as the username.
3. Enter a valid email address.
4. Enter a valid password.
5. Enter the matching confirm password.
6. Click Register.
7. Observe the registration result.

### Expected Result
The system should accept the username and proceed with successful registration.

### Actual Result
The system accepted the username and registration proceeded successfully.

### Initial Test Result
**PASS**

### Regression Result
**PASS** — The system continued to accept a username above the minimum length during regression testing.

### Defect Reference
None.

---

## TC-011 — Verify Registration with a Password Below the Minimum Length

**Test Case ID:** TC-011

**Priority:** High

**Test Type:** Negative Testing

**Test Technique:** Boundary Value Analysis

**Requirement:** Password must contain at least 8 characters.

### Preconditions
- The registration page is accessible.

### Test Data

| Field | Value |
|---|---|
| Username | `FaiyazKar` |
| Email | `testuser@example.com` |
| Password | `Faiyaz1` (7 characters) |
| Confirm Password | `Faiyaz1` |

### Test Steps
1. Open the registration page.
2. Enter a valid username.
3. Enter a valid email address.
4. Enter `Faiyaz1` in Password.
5. Enter the same value in Confirm Password.
6. Click Register.
7. Observe the password validation response.

### Expected Result
The system should reject the 7-character password and display a password length validation message. Registration should not proceed.

### Actual Result
The system displayed a password length validation message for the short password.

### Initial Test Result
**PASS**

### Defect Reference
None.

---

## TC-012 — Verify Registration with a Password Exactly at the Minimum Length

**Test Case ID:** TC-012

**Priority:** High

**Test Type:** Positive Testing

**Test Technique:** Boundary Value Analysis

**Requirement:** A password containing exactly 8 characters must be accepted.

### Preconditions
- The registration page is accessible.
- The username and email are acceptable for registration.

### Test Data

| Field | Value |
|---|---|
| Username | `FaiyazKar` |
| Email | `testuser@example.com` |
| Password | `Faiyaz12` (8 characters) |
| Confirm Password | `Faiyaz12` |

### Test Steps
1. Open the registration page.
2. Enter a valid username.
3. Enter a valid email address.
4. Enter `Faiyaz12` in Password.
5. Enter the same value in Confirm Password.
6. Click Register.
7. Verify the success message and redirection to the login page.

### Expected Result
The system should accept the 8-character password and proceed with successful registration.

### Actual Result
The system accepted the password and registration proceeded successfully.

### Initial Test Result
**PASS**

### Defect Reference
None.

---

## 3. Initial Test Execution Summary

The following table records the original execution before defect fixes and the later regression finding.

| Test Case | Initial Result | Defect | Subsequent Result |
|---|---|---|---|
| TC-001 | FAIL | BUG-001 | PASS after retest |
| TC-002 | FAIL | BUG-002 | PASS after retest |
| TC-003 | FAIL | BUG-003 | PASS after retest |
| TC-004 | PASS | None | PASS |
| TC-005 | PASS | None | PASS |
| TC-006 | PASS | None | PASS |
| TC-007 | PASS | None | PASS |
| TC-008 | PASS | BUG-004 found later | FAIL in regression; PASS after fix |
| TC-009 | PASS | None | PASS |
| TC-010 | PASS | None | PASS |
| TC-011 | PASS | None | PASS |
| TC-012 | PASS | None | PASS |

### Initial Execution Metrics

- Total test cases executed: 12
- Passed: 9
- Failed: 3
- Initial pass rate: 75%
- Initial defects identified: 3

**Initial pass rate calculation:** 9 / 12 × 100 = 75%
BUG-004 was discovered later when TC-008 was rerun during regression testing after release R1.1. It is therefore not included among the three defects from the initial execution.

4. Regression Testing Summary

The following focused regression tests were executed after the release/update:

Test Case

Description

Regression Result

TC-006

Invalid email format

PASS

TC-007

Username below minimum length

PASS

TC-008

Username exactly 8 characters

FAIL

TC-010

Username above minimum length

PASS

After BUG-004 Was Fixed

Test Case

Retest/Final Regression Result

TC-006

PASS

TC-007

PASS

TC-008

PASS

TC-010

PASS

Final regression result: 4/4 passed (100%).

The initial failure of TC-008 illustrates how a boundary-value defect can be introduced or exposed by a later change, even when the test previously passed.

5. Conclusion

The 12 test cases cover required-field validation, invalid email handling, password confirmation, minimum-length validation, successful registration, and boundary-value testing.

The initial execution identified three defects. A subsequent regression cycle exposed one additional defect affecting an 8-character username. After fixes and retesting, the affected tests passed, and the final focused regression suite achieved a 100% pass rate.

The project demonstrates practical QA skills in test design, manual execution, defect reporting, retesting, regression testing, and result documentation.

Scope limitation: These results apply only to the requirements, test data, environment, and test cases documented here. They do not establish that the entire application is defect-free.
