s# Register Functionality US, AC, TC
------
## User Story: Register with valid data

### AC:
- Given the user is on the Register page  
- When the user enters valid registration data  
- And clicks on the Register button  
- Then the account is created successfully  
- And the user is redirected to the homepage / login page

  -------
### TC:
 - Functional Test
  - **Valid**
    
    #### TC-FUNCV-US1.0-01 – Validate register using valid data
    - **Priority:** High
    - **Preconditions:** User is on the register page
    - **Test Steps:**
     1. Fill all mandatory fields with valid data
     2. Click on the register button
    - **Expected Result:** Registeration is successful
    - **Actual Result:** ______

    #### TC-FUNCV-US1.0-02 – Validate using minimum allowed password length
    - **Priority:** Medium
    - **Preconditions:** User on the register page & All mandatory fields are filled except password
    - **Test Steps:**
     1. Fill the password with a minimum of 6 characters
     2. Click on the register button
    - **Expected Result:** Registeration is successful
    - **Actual Result:** ______

    #### TC-FUNCV-US1.0-03 – Validate using maximum allowed password length
    - **Priority:** Medium
    - **Preconditions:** User on the register page & All mandatory fields are filled except password
    - **Test Steps:**
     1. Fill the password with a maximum of 64 characters
     2. Click on the register button
    - **Expected Result:** Registeration is successful
    - **Actual Result:** ______
  
 - **Invalid**

   **Expected results**:
    - The system should display a required field validation message for the empty field.
    - The error message should be displayed below the corresponding input field.
    - The registration form should not be submitted.
    - The user account should not be created.    

   #### TC-FUNCIV-US1.0-01 – Validate using one-character password
    - **Priority:** Medium
    - **Preconditions:** User on the register page & All mandatory fields are filled except password
    - **Test Steps:**
     1. Fill the password with a minimum of 5 characters
     2. Click on the register button
    - **Actual Result:** ______

   #### TC-FUNCINV-US1.0-02 – Validate using 65-character password
    - **Priority:** Medium
    - **Preconditions:** User on the register page & All mandatory fields are filled except password
    - **Test Steps:**
     1. Fill the password with a maximum of 65 characters
     2. Click on the register button
    - **Actual Result:** ______

    #### TC-FUNCINV-US1.0-03 – Validate leaving all fields empty
    - **Priority:** Medium
    - **Preconditions:** User on the register page 
    - **Test Steps:**
     1. Leave all fields empty
     2. Click on the register button
    - **Actual Result:** ______

    #### TC-FUNCINV-US1.0-04 – Validate using non-symmetric passwords
    - **Priority:** Medium
    - **Preconditions:** User on the register page & All mandatory fields are filled except password
    - **Test Steps:**
     1. Fill the password fields with different password
     2. Click on the register button
    - **Actual Result:** ______
  
    #### TC-FUNCINV-US1.0-05 – Validate register while no internet connection established
    - **Priority:** Medium
    - **Preconditions:** User on the register page & All mandatory fields are filled
    - **Test Steps:**
     1. Cut off the internet connection
     2. Click on the register button
    - **Expected Result:** Unsuccessful registration, user is redirected to no internet connection 404 page
    - **Actual Result:** ______

    #### TC-FUNCINV-US1.0-06 – Validate using a registered email
    - **Priority:** Medium
    - **Preconditions:** User on the register page & All mandatory fields are filled except email
    - **Test Steps:**
     1. Fill the email fields with a registered email
     2. Click on the register button
    - **Actual Result:** ______

    #### TC-FUNCINV-US1.0-07 – Validate using a wrong format email
    - **Priority:** Medium
    - **Preconditions:** User on the register page & All mandatory fields are filled except email
    - **Test Steps:**
     1. Fill the email fields with an email in the wrong format 
     2. Click on the register button
    - **Actual Result:** ______
  
    #### TC-FUNCINV-US1.0-07 – Validate leaving email field empty
    - **Priority:** Medium
    - **Preconditions:** User on the register page & All mandatory fields are filled except email
    - **Test Steps:**
     1. Leave the email field empty
     2. Click on the register button
    - **Actual Result:** ______

    #### TC-FUNCINV-US1.0-08 – Validate leaving the first name field empty
    - **Priority:** Medium
    - **Preconditions:** User on the register page & All mandatory fields are filled except the first name
    - **Test Steps:**
     1. Leave the first name field empty
     2. Click on the register button
    - **Actual Result:** ______

    #### TC-FUNCINV-US1.0-09 – Validate leaving the last name field empty
    - **Priority:** Medium
    - **Preconditions:** User on the register page & All mandatory fields are filled except the last name
    - **Test Steps:**
     1. Leave the last name field empty
     2. Click on the register button
    - **Actual Result:** ______
    
 - Edge

 - UI / Usability Test
 - Performance Test
 - Compatibility Test
 - Security
 - API

## User Story: Registration validation

### AC:
- Given the user is on the Register page  
- When the user submits the form with missing or invalid data

  -------
### TC:
 - Functional Test
  - Valid
  - Invalid
  - Edge
 - UI / Usability Test
 - Performance Test
 - Compatibility Test
 - Security
 - API
- Then validation error messages are displayed  
- And the account is not created
