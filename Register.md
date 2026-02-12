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

 - Edge

    #### TC-Edge-US1.0-01 – Validate clicking on the register button multiple times
    - **Priority:** Medium
    - **Preconditions:** User on the register page & All mandatory fields are filled 
    - **Test Steps:**
     1. Spam click on the register button 
    - **Expected Result:**
      - The Register button should be disabled after the first click.
      - Only one registration request should be sent to the server.
      - The user account should be created only once.
      - No duplicate accounts should be created.
      - The system should remain responsive without errors or crashes.
    - **Actual Result:** ______

    #### TC-Edge-US1.0-02 – Validate creating two accounts with the same email at the same time
    - **Priority:** Medium
    - **Preconditions:** User on the register page in both devices/browsers/tabs & All mandatory fields are filled 
    - **Test Steps:**
     1. Click on create account at the same time for both requests
    - **Expected Result:**
      - Only one registration request should be sent to the server.
      - The user account should be created only once.
      - No duplicate accounts should be created.
      - The system should remain responsive without errors or crashes.
    - **Actual Result:** ______

    #### TC-Edge-US1.0-03 – Validate filling all fields and submit it after a long time
    - **Priority:** low
    - **Preconditions:** User on the register page & All mandatory fields are filled 
    - **Test Steps:**
     1. Wait for two hours
     2. Click on create account 
    - **Expected Result:**
      - Create account request is rejected
      - No account is created
      - All fields are empty
      - Validation error message must appear telling the user "session ended."
    - **Actual Result:** ______
  
 - UI

    #### TC-UI-US1.0-00 – Validate the register page layout and design 
    - **Priority:** high
    - **Preconditions:** User on the register page
    - **Test Steps:**
     1. Observe the page layout and design  
    - **Expected Result:**
      - All elements appear correctly without any overlapping
      - All text has the same language
      - All text has the right font size
    - **Actual Result:** ______
  
      #### TC-UI-US1.0-01 – Validate the register button layout and design
    - **Priority:** medium
    - **Preconditions:** User on the register page  
    - **Test Steps:**
     1. Observe the register button layout and design
    - **Expected Result:**
      - The register button has a different color compared to the register page
      - The "register" text color is different than the button color
    - **Actual Result:** ______
      
 - Usability Test

     #### TC-USE-US1.0-00 – Validate the cursor state when hovering on the register button
    - **Priority:** low
    - **Preconditions:** User on the register page  
    - **Test Steps:**
     1. Hover over the register button
    - **Expected Result:**
      - The register cursor state changes to pointer
    - **Actual Result:** ______

    #### TC-USE-US1.0-01 – Validate the page supports screen reader apps
    - **Priority:** high
    - **Preconditions:** User on the register page
    - **Test Steps:**
     1. Launch the screen reader app
     2. scroll through the page
    - **Expected Result:**
      - The user can hear the app describing the page
    - **Actual Result:** ______
  
    #### TC-USE-US1.0-02 – Validate the page clarity and it's easy to understand
    - **Priority:** high
    - **Preconditions:** User on the register page  
    - **Test Steps:**
     1. Observe the page design
    - **Expected Result:**
      - The page is easy to use and easy to self-explore
    - **Actual Result:** ______
  
     #### TC-USE-US1.0-03 – Validate navigating through page elements using keyboard navigation keys
    - **Priority:** low
    - **Preconditions:** User on the register page  
    - **Test Steps:**
     1. Press the tap to move to the next field
     2. Press Shift + tap to go back to the previous field
    - **Expected Result:**
      - The register cursor state changes to pointer
    - **Actual Result:** ______
  
    
 - Performance Test

     #### TC-PFM-US1.0-00 – Validate the registration response time  (Ignore this test case)
    - **Priority:** medium
    - **Preconditions:** User on the register page  
    - **Test Steps:**
     1. Fill all mandatory fields
     2. Click on the registration button
    - **Expected Result:**
      - response time is < 3s
    - **Actual Result:** ______
  
     #### TC-PFM-US1.0-01 – Validate the registration response time using 2.4G internet connection
    - **Priority:** high
    - **Preconditions:** User on the register page  
    - **Test Steps:**
     1. Fill all mandatory fields
     2. Click on the registration button
    - **Expected Result:**
      - response time is < 3s
    - **Actual Result:** ______
  
  
 - Compatibility Test

     #### TC-CMB-US1.0-00 – Validate opening the registration page using different devices
    - **Priority:** medium
    - **Preconditions:** User has access to the page from different devices (PC / Tablet / Mobile)
    - **Test Steps:**
     1. Navigate to the registration page 
    - **Expected Result:**
      - Page works normally on different devices
    - **Actual Result:** ______

    #### TC-CMB-US1.0-01 – Validate opening the registration page via different browsers
    - **Priority:** medium
    - **Preconditions:** User has access to the page from different browsers (Chrome / Edge / Firefox)
    - **Test Steps:**
     1. Navigate to the registration page via all browsers 
    - **Expected Result:**
      - Page works normally on different browsers
    - **Actual Result:** ______
  
    #### TC-CMB-US1.0-02 – Validate opening the registration page using different internet connections
    - **Priority:** medium
    - **Preconditions:** User has access to the page from different devices (Ethernet / Wifi / Mobile data)
    - **Test Steps:**
     1. Navigate to the registration page using an Ethernet connection
     2. Navigate to the registration page using wifi connection
     3. Navigate to the registration page using a mobile data connection
    - **Expected Result:**
      - Page works normally on different devices
    - **Actual Result:** ______
    
 - Security

    #### TC-SEC-US1.0-00 – Validate using SQL injection in the form's fields
    - **Priority:** medium
    - **Preconditions:** User has access to the page from different devices (Ethernet / Wifi / Mobile data)
    - **Test Steps:**
     1. Navigate to the registration page using an Ethernet connection
     2. Navigate to the registration page using wifi connection
     3. Navigate to the registration page using a mobile data connection
    - **Expected Result:**
      - Page works normally on different devices
    - **Actual Result:** ______
    
    - API

      #### TC-API-US1.0-00 – Validate the response code when registering
    - **Priority:** medium
    - **Preconditions:** 
    - **Test Steps:**
     1. Navigate to Postman
     2. Create a new post request
     3. fill all required fields
     4. Click on send
     5. Observe the response code
    - **Expected Result:**
      - Account is created successfully
      - Response code is 200
    - **Actual Result:** ______
  
     #### TC-API-US1.0-01 – Validate creating account through API
    - **Priority:** medium
    - **Preconditions:** User is on postman
    - **Test Steps:**
     1. Create a new post request
     2. fill all required fields
     3. Click on send
    - **Expected Result:**
      - Account is created successfully
      - Response code is 200
    - **Actual Result:** ______
  
     #### TC-API-US1.0-02 – Validate deleting account through API
    - **Priority:** medium
    - **Preconditions:** User is on postman
    - **Test Steps:**
     1. Create a new delete request
     2. Use the account id in the query params
     3. Click on send
    - **Expected Result:**
      - Account is deleted successfully
      - Response code is 400
    - **Actual Result:** ______
  
       #### TC-API-US1.0-02 – Validate deleting account response code via API
    - **Priority:** medium
    - **Preconditions:** User is on postman
    - **Test Steps:**
     1. Create a new delete request
     2. Use the account id in the query params
     3. Click on send
     4. Observe response code
    - **Expected Result:**
      - Account is deleted successfully
      - Response code is 400
    - **Actual Result:** ______

     #### TC-API-US1.0-02 – Validate get deleted account through API
    - **Priority:** medium
    - **Preconditions:** User is on postman
    - **Test Steps:**
     1. Create a new delete request
     2. Use the account id in the query params
     3. Click on send
     4. Create a new GET request
     5. Use the account id in the query params
     6. Fill all required fields
     7. Click on send
    - **Expected Result:**
      - Response body is empty
      - Response code is 404
    - **Actual Result:** ______
## User Story: Registration validation

### AC:
- Given the user is on the Register page  
- When the user submits the form with missing or invalid data

  -------
### TC:
 - Functional Test
  - Valid
  - Invalid

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
- Then validation error messages are displayed  
- And the account is not created
