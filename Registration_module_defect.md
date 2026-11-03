# Registration Module — Defect Reports & Retesting Results

## 1. Project Information

| Field | Details |
|---|---|
| Project | Registration Module QA Testing |
| Module | User Registration |
| Testing Type | Manual Functional Testing |
| Defects Reported | 4 |
| Initial Defects | 3 |
| Additional Defect Found During Regression | 1 |
| Final Status | All four defects recorded as fixed and verified through retesting |

## 2. Defect Summary

| Defect ID | Defect Title | Severity | Priority | Related Test Case | Final Status |
|---|---|---|---|---|---|
| BUG-001 | Incorrect validation message displayed when Username field is blank | Low | Medium | TC-001 | Closed |
| BUG-002 | Incorrect validation message displayed when Password field is blank | Low | Medium | TC-002 | Closed |
| BUG-003 | Incorrect validation message displayed when Email field is blank | Low | Medium | TC-003 | Closed |
| BUG-004 | Valid 8-character username is incorrectly rejected during registration | Medium | Medium | TC-008 | Closed |

**Status note:** The records below reflect the project results established during testing. Release/build identifiers, timestamps, and screenshots should be added if you have the original evidence.

---

# BUG-001 — Incorrect Validation Message Displayed When Username Field Is Blank

## Defect Information

| Field | Details |
|---|---|
| Defect ID | BUG-001 |
| Title | Incorrect validation message displayed when Username field is blank |
| Module | User Registration |
| Related Test Case | TC-001 |
| Severity | Low |
| Priority | Medium |
| Environment | Windows / Google Chrome |
| Initial Status | Open |
| Final Status | Closed |
| Defect Type | Functional validation / Error message |

## Description

When a user submits the registration form without entering a username, the application displays a generic validation message instead of a message that specifically identifies the missing Username field.

Although the application prevents the form from proceeding, the message does not clearly identify which field requires attention.

## Preconditions

- The registration page is accessible.
- The user is on the registration form.

## Test Data

| Field | Value |
|---|---|
| Username | Blank |
| Email | `testuser@example.com` |
| Password | `Faiyaz123` |
| Confirm Password | `Faiyaz123` |

## Steps to Reproduce

1. Open the registration page.
2. Leave the Username field blank.
3. Enter a valid email address.
4. Enter a valid password.
5. Enter the same password in Confirm Password.
6. Click the Register button.
7. Observe the validation message.

## Expected Result

The application should display a username-specific validation message, such as "Username is required," and prevent registration.

## Actual Result

The application displayed the generic message:

`All fields are required.`

## Impact

The form prevents submission, but the user does not receive clear field-specific feedback. This can reduce usability and make it harder to correct the form.

## Severity and Priority Rationale

- **Severity: Low** — The required-field validation still prevents the form from proceeding; the issue concerns the specificity of the message.
- **Priority: Medium** — Clear validation messages are part of the registration experience and should be corrected, although the defect does not block registration entirely.

## Evidence

Recommended evidence to attach if available:

- Screenshot of the registration form with Username blank.
- Screenshot showing the generic validation message.

## Retesting

**Retest Result: PASS**

After the fix, the application displayed the appropriate username validation message when the Username field was left blank.

**Retest Comment:** The Username required-field validation message is now displayed correctly. BUG-001 is verified as fixed.

## Final Status

**Closed** — The defect was retested successfully.

---

# BUG-002 — Incorrect Validation Message Displayed When Password Field Is Blank

## Defect Information

| Field | Details |
|---|---|
| Defect ID | BUG-002 |
| Title | Incorrect validation message displayed when Password field is blank |
| Module | User Registration |
| Related Test Case | TC-002 |
| Severity | Low |
| Priority | Medium |
| Environment | Windows / Google Chrome |
| Initial Status | Open |
| Final Status | Closed |
| Defect Type | Functional validation / Error message |

## Description

When a user submits the registration form without entering a password, the application displays a generic required-field message instead of clearly identifying the missing Password field.

The validation response does not provide the specific feedback expected for this field.

## Preconditions

- The registration page is accessible.
- The user is on the registration form.

## Test Data

| Field | Value |
|---|---|
| Username | `FaiyazKarim` |
| Email | `testuser@example.com` |
| Password | Blank |
| Confirm Password | `Faiyaz123` |

## Steps to Reproduce

1. Open the registration page.
2. Enter a valid username.
3. Enter a valid email address.
4. Leave the Password field blank.
5. Enter a value in Confirm Password.
6. Click Register.
7. Observe the validation message.

## Expected Result

The application should display a password-specific validation message, such as "Password is required," and prevent registration.

## Actual Result

The application displayed the generic message:

`All fields are required.`

## Impact

The user receives insufficient feedback about the missing password. This can make it harder to identify the field that needs correction.

## Severity and Priority Rationale

- **Severity: Low** — Registration is prevented, so the required field is not bypassed.
- **Priority: Medium** — The validation message should be corrected to improve clarity and consistency across the form.

## Evidence

Recommended evidence to attach if available:

- Screenshot of the form with Password blank.
- Screenshot of the generic validation response.

## Retesting

**Retest Result: PASS**

After the fix, the application displayed the appropriate password validation message when the Password field was left blank.

**Retest Comment:** The Password required-field validation message is now displayed correctly. BUG-002 is verified as fixed.

## Final Status

**Closed** — The defect was retested successfully.

---

# BUG-003 — Incorrect Validation Message Displayed When Email Field Is Blank

## Defect Information

| Field | Details |
|---|---|
| Defect ID | BUG-003 |
| Title | Incorrect validation message displayed when Email field is blank |
| Module | User Registration |
| Related Test Case | TC-003 |
| Severity | Low |
| Priority | Medium |
| Environment | Windows / Google Chrome |
| Initial Status | Open |
| Final Status | Closed |
| Defect Type | Functional validation / Error message |

## Description

When a user submits the registration form without entering an email address, the application displays a generic required-field message instead of identifying the missing Email field.

This does not provide the specific feedback expected from email-field validation.

## Preconditions

- The registration page is accessible.
- The user is on the registration form.

## Test Data

| Field | Value |
|---|---|
| Username | `FaiyazKarim` |
| Email | Blank |
| Password | `Faiyaz123` |
| Confirm Password | `Faiyaz123` |

## Steps to Reproduce

1. Open the registration page.
2. Enter a valid username.
3. Leave the Email field blank.
4. Enter a valid password.
5. Enter the same value in Confirm Password.
6. Click Register.
7. Observe the validation message.

## Expected Result

The application should display an email-specific validation message, such as "Email is required," and prevent registration.

## Actual Result

The application displayed the generic message:

`All fields are required.`

## Impact

The user is not told explicitly that the email address is missing. This makes the form less clear and consistent.

## Severity and Priority Rationale

- **Severity: Low** — The application still prevents submission without the required email.
- **Priority: Medium** — Field-specific validation is important to the usability of the registration form.

## Evidence

Recommended evidence to attach if available:

- Screenshot showing the Email field left blank.
- Screenshot showing the generic validation message.

## Retesting

**Retest Result: PASS**

After the fix, the application displayed the appropriate email validation message when the Email field was left blank.

**Retest Comment:** The Email required-field validation message is now displayed correctly. BUG-003 is verified as fixed.

## Final Status

**Closed** — The defect was retested successfully.

---

# BUG-004 — Valid 8-Character Username Is Incorrectly Rejected During Registration

## Defect Information

| Field | Details |
|---|---|
| Defect ID | BUG-004 |
| Title | Valid 8-character username is incorrectly rejected during registration |
| Module | User Registration |
| Related Test Case | TC-008 |
| Severity | Medium |
| Priority | Medium |
| Environment | Windows / Google Chrome |
| Discovery Method | Regression Testing |
| Testing Technique | Boundary Value Analysis |
| Initial Status | Open |
| Final Status | Closed |
| Defect Type | Functional validation / Boundary condition |

## Description

During regression testing following release R1.1, the application incorrectly rejected a username containing exactly 8 characters.

According to the requirement, a username must contain **at least 8 characters**. Therefore, an 8-character username is a valid boundary value and should be accepted when the other registration fields are valid.

The same test case had passed during the initial execution but failed during regression testing.

## Preconditions

- The registration page is accessible.
- The application is running the build associated with the regression cycle.
- The username and email are acceptable for registration and do not conflict with existing accounts.

## Test Data

| Field | Value |
|---|---|
| Username | `FaiyazKa` (8 characters) |
| Email | `testuser@example.com` |
| Password | `Faiyaz123` |
| Confirm Password | `Faiyaz123` |

## Steps to Reproduce

1. Open the registration page.
2. Enter `FaiyazKa` as the username.
3. Enter a valid email address.
4. Enter a valid password.
5. Enter the matching confirm password.
6. Click Register.
7. Observe the validation response and check whether registration proceeds.

## Expected Result

The application should accept the 8-character username, display a success message, and redirect the user to the login page.

## Actual Result

The application rejected the username and displayed an error indicating that the username must be 8 characters.

The validation behavior incorrectly rejected a username that met the minimum-length requirement.

## Impact

Users with a valid 8-character username may be unable to register. This creates a functional failure at the minimum supported boundary.

The issue affects valid registration attempts and therefore has a greater functional impact than the validation-message defects.

## Severity and Priority Rationale

- **Severity: Medium** — A valid boundary input is rejected, preventing some users from completing registration.
- **Priority: Medium** — The defect should be corrected because it violates the documented minimum-length requirement, although longer valid usernames can still be accepted.

## Evidence

Recommended evidence to attach if available:

- Screenshot showing the 8-character username entered.
- Screenshot showing the incorrect validation error.
- Regression execution record showing TC-008 failed.
- Successful retest evidence after the fix.

## Retesting

**Retest Result: PASS**

After the fix, the application accepted the 8-character username and registration completed successfully.

**Retest Comment:** The 8-character username is now accepted and registration completes successfully. BUG-004 is verified as fixed.

## Regression Verification

The following related tests were checked after the fix:

| Test Case | Purpose | Final Result |
|---|---|---|
| TC-006 | Invalid email format remains rejected | PASS |
| TC-007 | Username below 8 characters remains rejected | PASS |
| TC-008 | Username exactly 8 characters is accepted | PASS |
| TC-010 | Username above 8 characters is accepted | PASS |

**Final regression result: 4/4 passed (100%).**

## Final Status

**Closed** — The defect was fixed and successfully verified through retesting and focused regression testing.

---

# 3. Defect Lifecycle Summary

| Defect | Initial State | Fix Verification | Final State |
|---|---|---|---|
| BUG-001 | Open | Retest passed | Closed |
| BUG-002 | Open | Retest passed | Closed |
| BUG-003 | Open | Retest passed | Closed |
| BUG-004 | Open | Retest and focused regression passed | Closed |

The defect lifecycle followed in this project was:

`Open → Fixed → Ready for Retest → Retest → Closed`

If a defect had remained after the fix, the expected workflow would be to record the failed retest and reopen the defect.

---

# 4. Overall Defect Analysis

## Defect Categories

| Category | Defects | Observation |
|---|---|---|
| Required-field validation messages | BUG-001, BUG-002, BUG-003 | Generic messages were displayed instead of field-specific messages. |
| Boundary-value validation | BUG-004 | The minimum valid username length was incorrectly rejected during regression. |

## Key QA Findings

1. Required-field validation should provide clear feedback identifying the field that needs attention.
2. Boundary values require explicit coverage because small changes in validation logic can cause valid inputs to fail.
3. Previously passing test cases should be included in regression suites where relevant.
4. A developer marking a defect as fixed does not replace QA retesting.
5. Expected results, actual results, test evidence, and defect references should remain traceable.

## Conclusion

The registration testing project recorded four defects: three related to required-field validation messages and one boundary-value defect discovered during regression testing.

All four defects were recorded as fixed and verified through retesting. The focused regression suite achieved a final result of 4/4 passed test cases.

These findings demonstrate practical experience in defect reporting, severity and priority classification, retesting, regression testing, and requirements-based validation.

**Scope limitation:** These conclusions apply to the tested registration functionality and documented test cases. They do not establish that the entire application is defect-free.
