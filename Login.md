# Feature: <Feature Name>

---

# 1️⃣ User Story
As a customer,  
I want to log in to my account,  
So that I can use the store faster.

---

# 2️⃣ Acceptance Criteria (BDD)

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

---

# 3️⃣ Test Cases

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
2.  logout
3.  Click inside the email field
5.  Select the email suggested to you
6.  Observe both email and password fields
7.  Click on the login button

**Expected Result:**
-  both email and password fields are auto-filled
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
-  A validation error message appears notifying the user, "Wrong email format."
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
 many time wrong pass / spam click on login button / use space / copy paste data / login from two devices at the same time / using capital letters in email
| TC ID | Scenario | Expected Result |
|-------|----------|----------------|

---

## Security Testing

| TC ID | Attack Type | Expected Result |
|-------|------------|----------------|

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
