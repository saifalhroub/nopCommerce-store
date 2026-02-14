# Feature: Login

---------------------------------------------------------------------------------------

# 1️⃣ User Story

As a customer,  
I want to log in to my account,  
So that I can use the store faster.

----------------------------------------------------------------------------------------

# 2️⃣ Acceptance Criteria (BDD)

## AC1 – Navigation
Given the user is on the website  
When the user clicks on the Login button  
Then the user is redirected to the Login page  

## AC2 – Successful Login
Given the user is on the Login page  
When the user enters valid registered email and valid password  
Then the system authenticates the user  
And a session/token is created  
And the user is redirected to the landing page  

## AC3 – Validation
Given the user is on the Login page  
When the user submits invalid or missing data  
Then the login request is rejected  
And a proper validation message appears  
And no session is created  

## AC4 – Register Option Visibility
Given the user is on the Login page  
Then a visible Register option is available  
So the user can create a new account  

-----------------------------------------------------------------------------------

# 3️⃣ Test Cases


## Functional – Valid Scenarios

| TC ID | Title | Priority | Preconditions |
|-------|-------|----------|---------------|
| TC-FUNCV-1.0 | Login with valid credentials | High | User has a registered account |

**Steps:**
1. Enter valid registered email  
2. Enter correct password  
3. Click Login  

**Expected Result:**
- Authentication succeeds  
- Session/token is created  
- User is redirected to landing page  

---

| TC-FUNCV-1.1 | Validate Remember Me functionality | High | User has a registered account |

**Steps:**
1. Enter valid email and password  
2. Check "Remember Me."  
3. Click Login  
4. Logout  
5. Return to Login page  

**Expected Result:**
- Email field is retained (according to business rules)  
- User can log in again successfully  
- Session is created properly  

----------------------------------------------------------------------------------------



## Functional – Invalid Scenarios

| TC ID | Title | Priority | Preconditions |
|-------|-------|----------|---------------|
| TC-FUNCINV-1.0 | Login with empty fields | Medium | User on Login page |

**Steps:**
1. Leave email and password empty  
2. Click Login  

**Expected Result:**
- Login request is rejected  
- Validation messages appear for required fields  
- User remains on Login page  

---

| TC-FUNCINV-1.1 | Login with empty password | High | Email field filled |

**Steps:**
1. Leave password empty  
2. Click Login  

**Expected Result:**
- Login request is rejected  
- Password validation message appears  

---

| TC-FUNCINV-1.2 | Login with unregistered email | High | User on Login page |

**Steps:**
1. Enter unregistered but valid-format email  
2. Enter any password  
3. Click Login  

**Expected Result:**
- Login request is rejected  
- Generic error message appears (e.g., "Invalid credentials")  

---

| TC-FUNCINV-1.3 | Login with wrong password | High | Registered email exists |

**Steps:**
1. Enter valid registered email  
2. Enter incorrect password  
3. Click Login  

**Expected Result:**
- Login request is rejected  
- Generic error message appears  
- No sensitive information is exposed  

---

| TC-FUNCINV-1.4 | Login with invalid email format | High | User on Login page |

**Steps:**
1. Enter invalid email format (e.g., @@.)  
2. Enter password  
3. Click Login  

**Expected Result:**
- Login request is rejected  
- Email format validation message appears  

---

| TC-FUNCINV-1.5 | Login without internet connection | Medium | User on Login page |

**Steps:**
1. Enter valid credentials  
2. Disable internet connection  
3. Click Login  

**Expected Result:**
- Login request fails gracefully  
- User remains on Login page  
- No session is created  

----------------------------------------------------------------------------------------


## Edge Cases

| TC ID | Scenario | Priority |
|-------|----------|----------|
| TC-EDGE-1.0 | Multiple failed login attempts | High |
| TC-EDGE-1.1 | Spam clicking Login button | Medium |
| TC-EDGE-1.2 | Email with leading/trailing spaces | Medium |
| TC-EDGE-1.3 | Password with leading/trailing spaces | Medium |
| TC-EDGE-1.4 | Concurrent login attempts from different devices | Medium |
| TC-EDGE-1.5 | Login while already logged in | Medium |
| TC-EDGE-1.6 | Direct access to protected URL without login | High |

### Expected Behavior (General for Edge Cases):
- System handles concurrent or repeated requests safely  
- No crashes or duplicate sessions occur  
- Behavior follows defined business rules  
- No data corruption  

----------------------------------------------------------------------------------------

## Security Testing

| TC ID | Scenario | Priority |
|-------|----------|----------|
| TC-SEC-1.0 | SQL Injection in password field | High |
| TC-SEC-1.1 | SQL Injection in email field | High |
| TC-SEC-1.2 | Brute force attempt | High |
| TC-SEC-1.3 | Session expiration after inactivity | High |

### Expected Result:
- Login request is rejected  
- No sensitive data is exposed  
- Proper HTTP status codes returned  
- Account lockout/rate limiting applied (if defined)  
- Session expires according to defined timeout policy  

----------------------------------------------------------------------------------------

# 4️⃣ Notes

- All error messages should be generic (e.g., "Invalid credentials")  
- No technical stack traces should appear  
- Authentication must not expose internal system behavior  
- All responses must comply with defined business rules  


----------------------------------------------------------------------------------------
## Performance Testing

 Response login time < 3s 
  (The recommended and advised response time according to different resources)

----------------------------------------------------------------------------------------
## UI Testing

- Layout validation  
- Field alignment (All fields appear normally without overlapping)
- Button state (Login button has a special color & Login text has a different color) 
- Error message placement  (Error message appears under the field with the mistake only)

----------------------------------------------------------------------------------------


## Usability Testing

- Keyboard navigation  (Use Tab button to move to the next field, Use Tab + Shift to move to the previous field)
- Field focus behavior  (The field border color changes, and the typing cursor is placed inside the field)
- Error clarity (The error message is clear and describes the error according to the field with the error)
- Mandatory indicators  (All mandatory fields have a (*) sign).

----------------------------------------------------------------------------------------

## API Testing (If applicable)

### Valid Request
- Status Code: (200 for successful login)
- Response Body: (New session is created with an ID)
- Database Check:

### Invalid Request
- Status Code: (400 for an unregistered user)
- Error Message: (Empty if an invalid login is established / Bad request)
- Data Integrity:
