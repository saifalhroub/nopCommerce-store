# Feature: <Feature Name>

---

# 1️⃣ User Story
As a customer,  
I want to log in to my account,  
So that I can use the store faster.

---

#  Acceptance Criteria (BDD)

## AC1 – Happy Path
Given that the user navigates to the website 
When the user clicks on the login button 
Then the user will be redirected to the login page
And the user can log in using email and password

## AC2 – Validation
Given the user is on the login page
When the user uses invalid data 
Then the system must prevent the login request
And a proper validation message will appear according to the error made

## AC3 – System Behavior
Given  
When  
Then  

# 2️ As a user,
 I want to see a rigester option while I am on the login page,
 So I can create an account if I do not have one.
---

#  Test Cases

---

## Functional – Valid Scenarios

| TC ID | Title | Priority | Preconditions |
|-------|-------|----------|---------------|
| TC-FUNCV-1.0 | Validate logging in with valid data | High  | User is on registeration page |

**Steps:**
1.  Fill all mandatory fields with valid data
2.  Click on login

**Expected Result:**
-  Login request is accepted
-  A new session is created
-  Session Id created and stored in the database
-  user is redirected to the landing page

---

| TC-FUNCV-1.1 | Validate remember me checkbox functionality | High  | User is on registration page, and all fields are filled with valid data |

**Steps:**
1.  Check the Remember me checkbox
2.  Click on login
3.  logout
4.  Observe email & password fields
5.  Click on login


**Expected Result:**
-  both email and password fields are placed inside their fields
-  Login request is accepted
-  A new session is created
-  Session Id created and stored in the database
-  user is redirected to the landing page




---
## Functional – Invalid Scenarios

| TC ID | Title | Priority | Preconditions |
|-------|-------|----------|---------------|
| TC-FUNCINV-1.0 | Validate leaving all fields empty | Medium | User is on login page |

**Steps:**
1.  Leave all fields empty
2.  Click on the login button

**Expected Result:**
-  The login request is rejected
-  The user remains on the login page
-  A validation error for both email and password

---

## Functional – Invalid Scenarios

| TC ID | Title | Priority | Preconditions |
|-------|-------|----------|---------------|
| TC-FUNCINV-1.1 | Validate leaving the password field empty | High | User is on the login page, and the email field is filled |

**Steps:**
1.  Leave the password field empty
2.  Click on the login button

**Expected Result:**
-  The login request is rejected
-  The user remains on the login page
-  A password validation error appears  
  

---

## Functional – Invalid Scenarios

| TC ID | Title | Priority | Preconditions |
|-------|-------|----------|---------------|
| TC-FUNCINV-1.2 | Validate using an un-registered email | High | User is on the login page |

**Steps:**
1.  Fill the email field unregistered email and the right format email
2.  Fill in the password with a password that meets the restrictions

**Expected Result:**
-  Login request is rejected
-  The user remains on the login page
-  A validation error appears saying "no account exists."

---

## Boundary Value Testing

| Field | Min | Max | Tested Value | Expected |
|-------|-----|-----|-------------|----------|

---

## Functional – Invalid Scenarios

| TC ID | Title | Priority | Preconditions |
|-------|-------|----------|---------------|
| TC-FUNCINV-1.3 | Validate email format mistake | High | User is on the login page and has a registered account |

**Steps:**
1.  Fill in the email field with a wrong format "@@."
2.  Fill in the password field
3.  Click on the login button

**Expected Result:**
- The login request is rejected
- The user remains on the login page
- A validation error message appears notifying the user, "Wrong email format."
---

## Functional – Invalid Scenarios

| TC ID | Title | Priority | Preconditions |
|-------|-------|----------|---------------|
| TC-FUNCINV-1.4 | Validate a mistake in the password | High | User is on the login page |

**Steps:**
1.  Fill the email field with a valid registered email
2.  Fill the password field with a mistaken password
3.  Click on the login button

**Expected Result:**
- The login request is rejected
- The user remains on the login page
-  A validation error message appears notifying the user, "Wrong Password."

---
## Functional – Invalid Scenarios

| TC ID | Title | Priority | Preconditions |
|-------|-------|----------|---------------|
| TC-FUNCINV-1.5 | Validate no internet connection logging in | medium | User is on the login page |

**Steps:**
1.  Fill both the email and password fields with valid data
2.  Cut-off the internet connection
3.  Click on the login button

**Expected Result:**
- The user is redirected to no internet connection page
- The login request is rejected
- No session is recorded in the database
---
## Edge Cases
 
| TC ID | Scenario | Expected Result |
|-------|----------|----------------|

| TC-EDGE-1.0 | Multiple login failed attempts with wrong password | medium | User is on the login page |

**Steps:**
1.  Fill the email field with a valid registered email
2.  Fill the password field with an invalid password
3.  Click on the login button
4.  Repeat steps 2 & 3 multiple times

**Expected Result:**
- The login request is rejected
- User remains on the login page
- No crashes occur on the system
- User is asked to reset their password after too many failed attempts
---

| TC-EDGE-1.1 | Spam clicking on the login button | medium | User is on the login page |

**Steps:**
1.  Fill in the email and password fields
2.  Spam clicking on the login button

**Expected Result:**
- One request is accepted and recorded in the database if a valid email and password are used
  or
- Login requests are rejected, and the user is not allowed to log in and is asked to reset their password 
- No crash occurs in the system
---

| TC-EDGE-1.2 | Validate using space in the email| low | User is on the login page |
****** This Case depends on the BRD (down is assumptions)
**Steps:**
1.  Fill the email field with a valid registered email with a leading/ trailing space
2.  Fill the password field with a valid password
3.  Click on the login button

**Expected Result:**
- The system deals with the space properly by neglecting it
- The login request is accepted
- User is redirected to the landing page
- Session ID is created and stored in the database
  
---

| TC-EDGE-1.3 | Validate using space in the password | low | User is on the login page |
****** This Case depends on the BRD (down is assumptions)
**Steps:**
1.  Fill the email field with a valid registered email 
2.  Fill the password field with a valid password with a leading/ trailing space
3.  Click on the login button

**Expected Result:**
- The login request is rejected
- A validation error message to the password field appears
---

| TC-EDGE-1.4 | Validate copy and paste email & password | low | User is on a notes app|
****** This Case depends on the BRD (down is assumptions)
**Steps:**
1.  Type the email and password
2.  Copy the email 
3.  Navigate to the store
4.  Paste the email
5.  Navigate to the notes app
6.  Copy the password
7.  Navigate to the store
8.  Paste the password
10. Click on the login button

**Expected Result:**
- The login request is accepted
- The user is redirected to the landing page
- A session id is created and stored in the database
---

| TC-EDGE-1.5 | Validate Race condition login attempts | low | User is on the login page on different devices |
****** This Case depends on the BRD (down is assumptions)
**Steps:**
1.  Fill both email and password fields with valid data on both devices
2.  Click on the login button at the same time on both devices

**Expected Result:**
- (I can not Judge)
---

| TC-EDGE-1.6 | Validate using capital letters in the email field | low | User is on the login page |
****** This Case depends on the BRD (down is assumptions)
**Steps:**
1.  Fill the email field with a valid registered email using capital letters
2.  Fill the password field with a valid password 
3.  Click on the login button

**Expected Result:**
- The login request is accepted
- User is redirected to the landing page
- Session ID is created and stored in the database
---
## Security Testing

| TC ID | Attack Type | Expected Result |
|-------|------------|----------------|

| TC-SEC-1.0 | Validate using SQL injection in the password field | High | User is on the login page |
****** This Case depends on the BRD (down is assumptions)
**Steps:**
1.  Fill the email field 
2.  Fill the password field with a SQL injection (' OR 1=1 --)
3.  Click on the login button

**Expected Result:**
- The login request is rejected
- No sensitive and secured data is exposed

---

| TC-SEC-1.1 | Validate using SQL injection in the email field | High | User is on the login page |
****** This Case depends on the BRD (down is assumptions)
**Steps:**
1.  Fill the email field with a SQL injection (' OR 1=1 --)
2.  Fill the password field 
3.  Click on the login button

**Expected Result:**
- The login request is rejected
- No sensitive and secured data is exposed

---

| TC-SEC-1.2 | Validate session expired after a period of non using time | High | User is logged in |
****** This Case depends on the BRD (down is assumptions)
**Steps:**
1.  Do not use the store for a while
2.  Use the store
3.  Observe the store reaction

**Expected Result:**
- Session is expired
- User is redirected to the login page
- Email and password fields are empty if the user did not activate (Remember me option.
- Email and password fields are filled if the user did activate (Remember me option.


---
## UI Testing

- Layout validation  
- Field alignment  
- Button state  
- Error message placement  

---

## Usability Testing

- Keyboard navigation  
- Field focus behavior  
- Error clarity  
- Mandatory indicators  

---

## API Testing (If applicable)

### Valid Request
- Status Code:
- Response Body:
- Database Check:

### Invalid Request
- Status Code:
- Error Message:
- Data Integrity:
