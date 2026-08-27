# QA Testing – Autotronic Web

## Project Overview

This repository contains a Manual Quality Assurance (QA) testing project for **Autotronic Web**, a web-based system used for IoT card management, invoice processing, and M2M card ordering.

The testing activities focused on verifying core application functionality, validating user inputs, identifying unexpected behavior, and documenting defects found during testing.

---

## Tester

**Name:** Iskandar Zulkarnaen  
**Testing Type:** Manual Testing  
**Environment:** Development  
**Application Version:** 1.0.0

---

## Testing Summary

| Total Test Cases | Passed | Failed |
|---|---:|---:|
| 19 | 16 | 3 |

---

## Features Tested

The following application features were tested:

- Login
- Dashboard
- Invoice
- View Invoice
- Download Invoice PDF
- Resend Invoice
- Edit Invoice
- Expired Invoice
- Order Perdana M2M
- Recycle Bin
- Order History (Pesanan Anda)

---

## Testing Types Applied

- Functional Testing
- Negative Testing
- Input Validation Testing
- Edge Case Testing
- Manual Regression Testing

---

## Test Case Documentation

The test cases include:

- Test Scenario
- Test Case ID
- Test Summary
- Pre-Condition
- Action Steps
- Expected Result
- Actual Result
- Test Status
- Priority
- Severity
- Bug Comments
- Evidence

The test cases cover both positive and negative scenarios.

---

## Testing Results

During the testing process:

- **16 test cases passed**
- **3 test cases failed**

The failed test cases were related to input validation during the login and M2M card ordering process.

---

## Bugs Found

### 1. Login Without Password

**Test Case ID:** TC-LG-003

**Issue:**  
The system processes the login request even when the password field is empty. After loading, the user remains on the login page without receiving a validation message.

**Expected Result:**  
The system should display a validation message indicating that the password field must be filled.

**Severity:** Major  
**Priority:** Low

---

### 2. Order M2M With Empty Data

**Test Case ID:** TC-ORD-003

**Issue:**  
The system does not display the expected validation alert when the user submits the M2M order form without filling in the required data.

**Expected Result:**  
The system should display an alert indicating that the required data must be filled.

**Priority:** Low

---

### 3. Order M2M With Empty Quality Data

**Test Case ID:** TC-ORD-004

**Issue:**  
The system processes the order submission even when the Quality field is empty. The process continues and eventually displays a server error.

**Expected Result:**  
The system should prevent submission and display a validation message.

**Severity:** Critical  
**Priority:** High

---

## Bug Report

A detailed bug report was created for the critical issue found during testing.

The bug report includes:

- Bug ID
- Title
- Reporter
- Submission Date
- Summary
- URL
- Evidence
- Testing Environment
- Steps to Reproduce
- Expected Result
- Actual Result
- Severity
- Priority
- Status

---

## Repository Structure

qa-testing-iot-card-dashboard/
│
├── README.md
│
├── Bug Reports/
│   └── Bug Report - Website perpanjangan kartu IoT.csv
│
├── Documentation/
│   └── testing-summary.md
│
└── Test Cases/
    └── Project QA – Website Perpanjangan Kartu IoT.xlsx
