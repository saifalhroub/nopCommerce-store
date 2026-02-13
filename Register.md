# Register Functionality – US, AC, TC

---

## User Story:

**As a user, I want to register an account so that I can shop faster**

---

## Acceptance Criteria (BDD)
1-
- Given the user is on the Register page  
- When the user enters valid data in all mandatory fields  
- And clicks on the Register button  
- Then the account is created successfully  
- And a success message is displayed  
- And the user is redirected to the homepage  
- And the user record is saved in the database  

2-
- Given the user is on the Register page
- When the user enters invalid data
- And clicks on the Register button
- Then no account is created
- And a validation error message appears depending on the field type
  
---

# Test Cases

----------------------------

## Functional Tests – Valid Scenarios

### TC-FUNCV-US1.0-01 – Register using valid data
- **Priority:** High  
- **Preconditions:** User is on the Register page  

**Test Steps:**
1. Fill all mandatory fields with valid data  
2. Click on the Register button  

**Expected Result:**
- The account is created successfully.  
- A success confirmation message is displayed.  
- The user is redirected to the homepage.  
- The new user record is stored in the database.  
- The user session is initiated.  

**Actual Result:** ______  

---

### TC-FUNCV-US1.0-02 – Register using minimum allowed password length (6 characters)
- **Priority:** Medium  
- **Preconditions:** User is on the Register page  

**Test Steps:**
1. Enter a password with exactly 6 characters  
2. Fill other mandatory fields with valid data  
3. Click Register  

**Expected Result:**
- Registration is successful.  
- No validation errors are displayed.  
- The account is created successfully.  

**Actual Result:** ______  

---

### TC-FUNCV-US1.0-03 – Register using maximum allowed password length (64 characters)
- **Priority:** Medium  
- **Preconditions:** User is on the Register page  

**Test Steps:**
1. Enter a password with 64 characters  
2. Fill other mandatory fields with valid data  
3. Click Register  

**Expected Result:**
- Registration is successful.  
- The password is accepted within allowed limits.  
- No truncation or system errors occur.  

**Actual Result:** ______  

---


---

## Acceptance Criteria (BDD)

- Given the user is on the Register page  
- When the user submits the form with missing or invalid data  
- Then validation error messages are displayed below the corresponding fields  
- And the form submission is prevented  
- And no account is created  
- And no user record is stored in the database  

---

# Test Cases

--------------------

##  Functional Tests – Invalid Scenarios

### TC-FUNCINV-US1.0-01 – Password shorter than minimum length
- **Priority:** Medium  
- **Preconditions:** User is on the Register page  

**Test Steps:**
1. Enter a password with less than 6 characters  
2. Fill other mandatory fields with valid data  
3. Click Register  

**Expected Result:**
- A validation message indicates password does not meet minimum length.  
- Registration is blocked.  
- No account is created.  

**Actual Result:** ______  

---

### TC-FUNCINV-US1.0-02 – Password exceeds maximum length (65 characters)
- **Priority:** Medium  

**Test Steps:**
1. Enter a password longer than 64 characters  
2. Fill other mandatory fields  
3. Click Register  

**Expected Result:**
- A validation message indicates password exceeds maximum length.  
- Registration is blocked.  
- No account is created.  

**Actual Result:** ______  

---

### TC-FUNCINV-US1.0-03 – Submit with all fields empty
- **Priority:** High  

**Test Steps:**
1. Leave all fields empty  
2. Click Register  

**Expected Result:**
- Required field validation messages are displayed for all mandatory fields.  
- The form is not submitted.  
- No account is created.  

**Actual Result:** ______  

---

### TC-FUNCINV-US1.0-04 – Password and Confirm Password mismatch
- **Priority:** High  

**Test Steps:**
1. Enter different values in Password and Confirm Password  
2. Fill other fields correctly  
3. Click Register  

**Expected Result:**
- A validation message indicates passwords do not match.  
- Registration is blocked.  
- No account is created.  

**Actual Result:** ______  

---

### TC-FUNCINV-US1.0-05 – No internet connection during submission
- **Priority:** Medium  

**Test Steps:**
1. Fill all required fields with valid data  
2. Disable internet connection  
3. Click Register  

**Expected Result:**
- Registration request fails.  
- User is shown a network error message.  
- No account is created.  
- User remains on the Register page.  

**Actual Result:** ______  

---

### TC-FUNCINV-US1.0-06 – Register with already registered email
- **Priority:** High  

**Test Steps:**
1. Enter an email that already exists in the system  
2. Fill other mandatory fields correctly  
3. Click Register  

**Expected Result:**
- A validation message indicates that the email already exists.  
- Registration is blocked.  
- No duplicate account is created.  

**Actual Result:** ______  

---

### TC-FUNCINV-US1.0-07 – Invalid email format
- **Priority:** Medium  

**Test Steps:**
1. Enter an email in incorrect format (e.g., user@@mail)  
2. Fill other fields correctly  
3. Click Register  

**Expected Result:**
- A validation message indicates invalid email format.  
- Registration is blocked.  
- No account is created.  

**Actual Result:** ______  

---

### TC-FUNCINV-US1.0-08 – Leave email field empty
- **Priority:** High  

**Test Steps:**
1. Leave Email field empty  
2. Fill other fields  
3. Click Register  

**Expected Result:**
- "Email is required" validation message appears.  
- Form submission is prevented.  
- No account is created.  

**Actual Result:** ______  

---

### TC-FUNCINV-US1.0-09 – Leave First Name empty
- **Priority:** Medium  

**Test Steps:**
1. Leave First Name empty  
2. Fill other fields  
3. Click Register  

**Expected Result:**
- Required field validation message is displayed for First Name.  
- Registration is blocked.  
- No account is created.  

**Actual Result:** ______  

---

### TC-FUNCINV-US1-0-10 – Leave Last Name empty
- **Priority:** Medium  

**Test Steps:**
1. Leave Last Name empty  
2. Fill other fields  
3. Click Register  

**Expected Result:**
- Required field validation message is displayed for Last Name.  
- Registration is blocked.  
- No account is created.  

**Actual Result:** ______  

-----------------------------------

## Edge Cases

### TC-EDGE-US1.0-01 – Multiple rapid clicks on Register button
- **Priority:** Medium  
- **Preconditions:** All mandatory fields are filled with valid data  

**Test Steps:**
1. Rapidly click the Register button multiple times  

**Expected Result:**
- The Register button becomes disabled after the first click OR shows a loading state.  
- Only one registration request is processed.  
- Only one user account is created.  
- No duplicate accounts exist in the database.  
- The system remains stable without crashes.  

**Actual Result:** ______  

---

### TC-EDGE-US1.0-02 – Concurrent registration with same email
- **Priority:** Medium  
- **Preconditions:** Same email used on two browsers/devices  

**Test Steps:**
1. Fill registration form with identical email on two devices  
2. Submit both forms simultaneously  

**Expected Result:**
- Only one account is successfully created.  
- The second request fails with a proper validation message (e.g., Email already exists).  
- No duplicate records are stored in the database.  

**Actual Result:** ______  

---

### TC-EDGE-US1.0-03 – Submit form after long inactivity
- **Priority:** Low  
- **Preconditions:** Form filled and left idle for extended period  

**Test Steps:**
1. Fill all required fields  
2. Wait for session expiration  
3. Click Register  

**Expected Result:**
- The system detects session expiration.  
- A session expired message is displayed.  
- Form submission is rejected.  
- No account is created.  
- User is required to refresh the page.  

**Actual Result:** ______  




-------------------------------

## UI Tests

### TC-UI-US1.0-01 – Validate page layout
- **Priority:** High  

**Test Steps:**
1. Observe the Register page layout  

**Expected Result:**
- No overlapping elements.  
- Text is properly aligned.  
- Font sizes are consistent.  
- Page is responsive on different screen sizes.  

**Actual Result:** ______  

---

### TC-UI-US1.0-02 – Validate Register button design
- **Priority:** Medium  

**Test Steps:**
1. Observe Register button  

**Expected Result:**
- Button is clearly visible.  
- Button color contrasts with background.  
- Button text is readable.  
- Button has consistent styling.  

**Actual Result:** ______  

### TC-UI-US1.0-03 – Correct validation error message when leaving a mandatory field
- **Priority:** Medium  

**Test Steps:**
1. Fill a mandatory field with invalid data
2. Click on register

**Expected Result:**
- Registration request is rejected
- No account is created
- Validation error message, content depends on the field 

**Actual Result:** ______  

-------

### TC-UI-US1.0-04 – Validate that focusing is appointed on the field with the wrong data
- **Priority:** Medium  

**Test Steps:**
1. Fill a mandatory field with invalid data
2. Fill the rest of the mandatory fields with valid data
3. Click on register

**Expected Result:**
- Registration request is rejected
- No account is created
- Focusing is appointed on the targeted field with invalid data

**Actual Result:** ______  

### TC-UI-US1.0-04 – Validate the state of a mandatory field with invalid data after correcting it
- **Priority:** Medium  

**Test Steps:**
1. Correct the mandatory field data
2. Observe the field's state

**Expected Result:**
- The focusing disappears from the field
- No Validation error appears

**Actual Result:** ______ 
-----------------------------------

## Usability Tests

### TC-USE-US1.0-01 – Hover state validation
- **Priority:** Low  

**Test Steps:**
1. Hover over Register button  

**Expected Result:**
- Cursor changes to pointer.  
- Hover state is visually distinguishable.  

**Actual Result:** ______  

---

### TC-USE-US1.0-02 – Form clarity validation
- **Priority:** High  

**Test Steps:**
1. Observe the form structure  

**Expected Result:**
- All mandatory fields are clearly marked (*).  
- Labels are descriptive and visible.  
- Error messages are clear and specific.  
- Input order is logical.  

**Actual Result:** ______  

---

### TC-USE-US1.0-03 – Keyboard navigation validation
- **Priority:** Medium  

**Test Steps:**
1. Use Tab key to navigate fields  
2. Use Shift + Tab to navigate backwards  

**Expected Result:**
- Focus moves sequentially between fields.  
- Focus indicator is visible.  
- Register button is accessible via keyboard.  

**Actual Result:** ______  

### TC-USE-US1.0-04 – Mandatory field state changes when leaving it empty / using invalid data
- **Priority:** Medium  

**Test Steps:**
1. Leave any mandatory field empty
2. Fill all other fields
3. Click on register
4. Repeat this for all mandatory fields  

**Expected Result:**
- Then register request is rejected
- No account has been created
- Validation error message 
- The field is highlighted
- The cursor is placed inside the field

**Actual Result:** ______  
----------------------------------

## Performance Tests

### TC-PFM-US1.0-01 – Registration response time
- **Priority:** Medium  

**Test Steps:**
1. Fill all mandatory fields  
2. Click Register  

**Expected Result:**
- Registration response time is less than 3 seconds under normal network conditions.  
- No timeout or performance degradation occurs.  

**Actual Result:** ______  

-----------------------------------

## Compatibility Tests

### TC-COMP-US1.0-01 – Different devices
- **Priority:** Medium  

**Test Steps:**
1. Open Register page on PC, Tablet, Mobile  

**Expected Result:**
- Page functions correctly on all devices.  
- Layout adapts properly.  

**Actual Result:** ______  

---

### TC-COMP-US1.0-02 – Different browsers
- **Priority:** Medium  

**Test Steps:**
1. Open Register page on Chrome, Edge, Firefox  

**Expected Result:**
- Page functions consistently across browsers.  
- No UI or functional differences observed.  

**Actual Result:** ______  

-----------------------------------

## Security Tests

### TC-SEC-US1.0-01 – SQL Injection attempt
- **Priority:** Medium  

**Test Steps:**
1. Enter "' OR 1=1 --" in email field  
2. Fill other required fields  
3. Click Register  

**Expected Result:**
- Input is sanitized.  
- No SQL error or stack trace is displayed.  
- Registration fails if input is invalid.  
- No database exposure occurs.  

**Actual Result:** ______  

### TC-SEC-US1.0-02 – No account Id reveal when registering with an already registered account
- **Priority:** Medium  

**Test Steps:**
1. Fill the email field with a registered email 
2. Fill in the other required fields  
3. Click Register  

**Expected Result:**
- Register request is rejected
- No account has been created
- Validation error message with context of "We detected a registered account linked to this email."
- No Id Account is revealed

**Actual Result:** ______  
-------------------------------------

## API Tests

### TC-API-US1.0-01 – Create account via API
- **Priority:** Medium  

**Test Steps:**
1. Send POST request with valid registration data  

**Expected Result:**
- Response code is 201 (Created).  
- Response body contains created user details.  
- User is stored in database.  

**Actual Result:** ______  

---

### TC-API-US1.0-02 – Delete account via API
- **Priority:** Medium  

**Test Steps:**
1. Send a DELETE request with a valid user ID  

**Expected Result:**
- Response code is 204 (No Content) or 200 (OK).  
- Account is deleted successfully.  

**Actual Result:** ______  

---

### TC-API-US1.0-03 – Get deleted account
- **Priority:** Medium  

**Test Steps:**
1. Send a GET request using the deleted account ID  

**Expected Result:**
- Response code is 404 (Not Found).  
- Response indicates user does not exist.  

**Actual Result:** ______  

---

### TC-API-US1.0-04 – response code when using invalid data (empty/wrong data)
- **Priority:** Medium  

**Test Steps:**
1. Send a post request using the with invalid data
**Expected Result:**
- Response code is 400 (bad request).  
- Response indicates no user has been created  

**Actual Result:** ______  

---

### TC-API-US1.0-04 – creating multiple invalid requests at the same time
- **Priority:** Medium  

**Test Steps:**
1. Send a post request using the with invalid data multiple times
**Expected Result:**
- Response code is 400 (bad request).  
- Response indicates no user has been created
- System does not crash 

**Actual Result:** ______  

 
