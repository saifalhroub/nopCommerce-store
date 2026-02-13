# Register Functionality – US, AC, TC

---

## User Story

**As a user, I want to register an account so that I can shop faster.**

---

## Acceptance Criteria (BDD)

### AC1 – Successful Registration
- Given the user is on the Register page  
- When the user enters valid data in all mandatory fields  
- And clicks on the Register button  
- Then the account is created successfully  
- And a success message is displayed  
- And the user is redirected to the homepage  
- And the user record is saved in the database  
- And a user session is initiated  

---

### AC2 – Invalid Data Handling
- Given the user is on the Register page  
- When the user submits the form with missing or invalid data  
- Then validation error messages are displayed below the corresponding fields  
- And the form submission is prevented  
- And no account is created  
- And no user record is stored in the database  

---

# Test Cases

---

## Functional Tests – Valid Scenarios

### TC-FUNCV-US1.0-01 – Register using valid data
- **Priority:** High  
- **Preconditions:** User is on the Register page  

**Test Steps:**
1. Fill all mandatory fields with valid data  
2. Click Register  

**Expected Result:**
- Account is created successfully.  
- Success confirmation message is displayed.  
- User is redirected to homepage.  
- User record exists in database.  
- User session is active.  

---

### TC-FUNCV-US1.0-02 – Register using minimum password length (6 characters)
- **Priority:** Medium  

**Test Steps:**
1. Enter password with exactly 6 characters  
2. Fill other fields with valid data  
3. Click Register  

**Expected Result:**
- Registration succeeds.  
- No validation errors appear.  
- Account is created successfully.  

---

### TC-FUNCV-US1.0-03 – Register using maximum password length (64 characters)
- **Priority:** Medium  

**Test Steps:**
1. Enter password with exactly 64 characters  
2. Fill other fields correctly  
3. Click Register  

**Expected Result:**
- Registration succeeds.  
- Password is accepted within defined limits.  
- No system error occurs.  

---

## Functional Tests – Invalid Scenarios

### TC-FUNCINV-US1.0-04 – Password shorter than minimum length
- **Priority:** Medium  

**Test Steps:**
1. Enter password with less than 6 characters  
2. Fill other fields correctly  
3. Click Register  

**Expected Result:**
- Validation message indicates minimum length requirement.  
- Registration is blocked.  
- No account is created.  

---

### TC-FUNCINV-US1.0-05 – Password exceeds maximum length (65 characters)
- **Priority:** Medium  

**Test Steps:**
1. Enter password longer than 64 characters  
2. Fill other fields correctly  
3. Click Register  

**Expected Result:**
- Validation message indicates maximum length exceeded.  
- Registration is blocked.  
- No account is created.  

---

### TC-FUNCINV-US1.0-06 – Submit with all fields empty
- **Priority:** High  

**Test Steps:**
1. Leave all mandatory fields empty  
2. Click Register  

**Expected Result:**
- Required validation messages appear for all mandatory fields.  
- Form submission is prevented.  
- No account is created.  

---

### TC-FUNCINV-US1.0-07 – Password mismatch
- **Priority:** High  

**Test Steps:**
1. Enter different values in Password and Confirm Password  
2. Fill other fields correctly  
3. Click Register  

**Expected Result:**
- Validation message indicates passwords do not match.  
- Registration is blocked.  
- No account is created.  

---

### TC-FUNCINV-US1.0-08 – No internet connection during submission
- **Priority:** Medium  

**Test Steps:**
1. Fill all required fields correctly  
2. Disable internet connection  
3. Click Register  

**Expected Result:**
- Network error message is displayed.  
- User remains on Register page.  
- No account is created.  

---

### TC-FUNCINV-US1.0-09 – Register with existing email
- **Priority:** High  

**Test Steps:**
1. Enter an already registered email  
2. Fill other fields correctly  
3. Click Register  

**Expected Result:**
- Validation message indicates email already exists.  
- Registration is blocked.  
- No duplicate account is created.  

---

### TC-FUNCINV-US1.0-10 – Invalid email format
- **Priority:** Medium  

**Test Steps:**
1. Enter invalid email format (e.g., user@@mail)  
2. Fill other fields correctly  
3. Click Register  

**Expected Result:**
- Validation message indicates invalid email format.  
- Registration is blocked.  
- No account is created.  

---

### TC-FUNCINV-US1.0-11 – Mandatory field left empty
- **Priority:** High  

**Test Steps:**
1. Leave one mandatory field empty  
2. Fill other fields correctly  
3. Click Register  

**Expected Result:**
- Required field message appears under respective field.  
- Field is highlighted.  
- Cursor focuses on invalid field.  
- No account is created.  

---

## Edge Cases

### TC-EDGE-US1.0-12 – Multiple rapid clicks
- **Priority:** Medium  

**Test Steps:**
1. Fill all fields correctly  
2. Rapidly click Register multiple times  

**Expected Result:**
- Button becomes disabled or shows loading state.  
- Only one request is processed.  
- Only one account is created.  

---

### TC-EDGE-US1.0-13 – Concurrent registration with same email
- **Priority:** Medium  

**Test Steps:**
1. Use same email on two devices  
2. Submit simultaneously  

**Expected Result:**
- Only one account is created.  
- Second request fails with a proper validation message.  
- No duplicate records exist in the database.  

---

### TC-EDGE-US1.0-14 – Submit after session expiration
- **Priority:** Low  

**Test Steps:**
1. Fill the form  
2. Wait until the session expires  
3. Click Register  

**Expected Result:**
- Session expiration message appears.  
- Submission is rejected.  
- No account is created.  
- User must refresh the page.  

---

## UI Tests

### TC-UI-US1.0-15 – Page layout validation
- **Priority:** High  

**Expected Result:**
- No overlapping elements.  
- Proper alignment and spacing.  
- Responsive layout.  

---

### TC-UI-US1.0-16 – Register button design
- **Priority:** Medium  

**Expected Result:**
- Button clearly visible.  
- Proper color contrast.  
- Consistent styling.  

---

### TC-UI-US1.0-17 – Validation message placement
- **Priority:** Medium  

**Expected Result:**
- Error appears below the corresponding field.  
- Message is clear and readable.  

---

### TC-UI-US1.0-18 – Field state after correction
- **Priority:** Medium  

**Expected Result:**
- Error message disappears once corrected.  
- Field returns to normal state.  

---

## Usability Tests

### TC-USE-US1.0-19 – Keyboard navigation
- **Priority:** Medium  

**Expected Result:**
- Tab navigation works sequentially.  
- Focus indicator visible.  
- Register button accessible via keyboard.  

---

### TC-USE-US1.0-20 – Form clarity
- **Priority:** High  

**Expected Result:**
- Mandatory fields clearly marked (*).  
- Labels descriptive.  
- Logical input order.  

---

## Performance Tests

### TC-PFM-US1.0-21 – Registration response time
- **Priority:** Medium  

**Expected Result:**
- Response time under 3 seconds under normal conditions.  
- No timeout occurs.  

---

## Compatibility Tests

### TC-COMP-US1.0-22 – Cross-device testing
- **Priority:** Medium  

**Expected Result:**
- Works correctly on desktop, tablet, and mobile.  

---

### TC-COMP-US1.0-23 – Cross-browser testing
- **Priority:** Medium  

**Expected Result:**
- Consistent functionality on Chrome, Edge, Firefox.  

---

## Security Tests

### TC-SEC-US1.0-24 – SQL Injection attempt
- **Priority:** Medium  

**Test Steps:**
1. Enter "' OR 1=1 --" in the email field  
2. Fill other fields correctly  
3. Click Register  

**Expected Result:**
- Input is sanitized.  
- No database error exposed.  
- Registration fails safely.  

---

### TC-SEC-US1.0-25 – No sensitive data exposure on duplicate email
- **Priority:** Medium  

**Expected Result:**
- Generic validation message displayed.  
- No account ID or internal system data revealed.  

---

## API Tests (Registration Endpoint Only)

### TC-API-US1.0-26 – Create account via API (Valid Data)
- **Priority:** Medium  

**Test Steps:**
1. Send a POST request with valid registration data  

**Expected Result:**
- Response code: 201 Created.  
- Response body contains user details (excluding password).  
- User stored in the database.  

---

### TC-API-US1.0-27 – Create account via API (Invalid Data)
- **Priority:** Medium  

**Test Steps:**
1. Send a POST request with invalid or empty data  

**Expected Result:**
- Response code: 400 Bad Request.  
- Error message returned in response body.  
- No user created.  

---
