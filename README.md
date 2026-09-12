# Guru99 Demo Banking - Manual Testing Project

**Tester:** Sohaila  
**Website:** [https://demo.guru99.com/V2/](https://demo.guru99.com/V2/)  
**Tool:** Excel (.xlsx)
**SRS Document:** The official Guru99 Banking Software Requirements Specification reviewed for this project is included in this repository as SRS_v2.docx .

## Overview

Manual testing project covering the core modules of the Guru99 demo banking application. The test suite includes functional testing, UI/UX validation, error message verification, and boundary value analysis across login/logout, customer management, account management, fund transfer, and other banking operations.

## Test Coverage

### Login & Logout (7 test cases)
- Mandatory field presence, blank field validation, credential matching, account lockout (3 failed attempts), successful login, reset button, and session termination on logout.

### New Customer Module (28 test cases)
- Field presence, customer name validation (max length, empty, numbers, special characters, leading spaces), gender options, DOB validation (empty, underage), address, city, state, PIN (format, length), mobile number (format, length), email (duplicate, format), password length, reset button, and successful customer creation.

### Additional Modules (covered in bug reports)
- **Delete Account:** Numeric validation, HTTP 500 errors, account ownership, balance checks
- **Fund Transfer:** Payer/payee validation, same-account transfer, insufficient balance, account ownership
- **Edit Customer:** Non-numeric ID, blank page on valid ID
- **Edit Account:** Valid/invalid account ID, UI alignment, reset functionality, tab highlighting
- **Customized Statement:** Date range validation, non-numeric transaction count, missing min transaction field
- **Change Password:** Password change with valid credentials
- **Delete Customer:** UI/UX alignment
- **New Account:** Successful submission redirection error
- **Logout:** Session termination vulnerability (critical)

## Bug Summary

| Severity | Count | Key Issues |
|----------|-------|------------|
| Critical | ~20 | Session not terminated on logout, age validation bypass, password validation, HTTP 500 errors, missing fields, incorrect error messages |
| Major | 2 | Non-numeric input accepted, blank page navigation |
| Minor | 5 | Wrong error messages, UI alignment, tab highlighting |

### Notable Open Bugs
- **Session termination** — Logout does not end the session; secured pages remain accessible via URL
- **Age validation** — System accepts customers under 18 years old
- **PIN & Mobile validation** — Wrong error messages ("Characters are not allowed" instead of "must be numeric")
- **Password field** — Missing from the New Customer form
- **HTTP 500 errors** — Delete Account, Edit Account, and New Account modules
- **Account lockout** — No lockout after 3 failed login attempts

## How to Use

1. Open `GuruProject_Sohaila.xlsx` in Excel or Google Sheets.
2. Navigate through the three sheets:
   - **login-logout feature** — Login and logout test cases
   - **New customer module** — New customer creation test cases
   - **bug report** — Detailed bug reports with severity, steps, and status

## Environment

- **Browser:** Google Chrome, Microsoft Edge
- **OS:** Cross-platform (web-based testing)
- **Application:** Guru99 Demo Banking (V2–V4)

