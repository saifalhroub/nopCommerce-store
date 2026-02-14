# Feature: Login

---------------------------------------------------------------------------------------

# 1️⃣ User Story

As a customer,  
I want to log in to my account,  
So that I can use the store faster.

---------------------------------------------------------------------------------------

# 2️⃣ Acceptance Criteria (BDD)

## AC1 – Navigation
Given the user is on the website  
When the user clicks on the Login button  
Then the user is redirected to the Login page  

## AC2 – Successful Login
Given the user is on the Login page  
When the user enters valid registered email and password  
Then the system authenticates the user  
And a session/token is generated  
And the user is redirected to the landing page  

## AC3 – Validation
Given the user is on the Login page  
When the user submits invalid or missing data  
Then the login request is rejected  
And a proper validation message appears  
And no session/token is created  

## AC4 – Register Visibility
Given the user is on the Login page  
Then a visible Register option is available  

---------------------------------------------------------------------------------------

# 3️⃣ Test Cases

## Functional – Valid

| TC ID | Title | Priority | Preconditions |
|-------|-------|----------|---------------|
| TC-FUNCV-1.0 | Login with valid credentials | High | User has registered account |

**Steps:**
1. Enter valid email  
2. Enter correct password  
3. Click Login  

**Expected Result:**
- Authentication succeeds  
- Session/token is created  
- User redirected to landing page  

---

| TC-FUNCV-1.1 | Remember Me functionality | High | Registered account exists |

**Steps:**
1. Enter valid credentials  
2. Enable "Remember Me"  
3. Click Login  
4. Logout  
5. Return to Login page  

**Expected Result:**
- Email field retained (as per business rules)  
- User can log in successfully again  

---------------------------------------------------------------------------------------

## Functional – Invalid

| TC ID | Title | Priority | Preconditions |
|-------|-------|----------|---------------|
| TC-FUNCINV-1.0 | Empty fields | Medium | On Login page |

**Steps:**
1. Leave fields empty  
2. Click Login  

**Expected Result:**
- Validation messages appear  
- Login rejected  
- No session created  

---

| TC-FUNCINV-1.1 | Wrong password | High | Registered email exists |

**Steps:**
1. Enter valid email  
2. Enter incorrect password  
3. Click Login  

**Expected Result:**
- Login rejected  
- Generic error message displayed ("Invalid credentials")  
- No sensitive info exposed  

---

| TC-FUNCINV-1.2 | Invalid email format | High | On Login page |

**Steps:**
1. Enter invalid email format  
2. Enter password  
3. Click Login  

**Expected Result:**
- Email format validation appears  
- Login rejected  

---------------------------------------------------------------------------------------

## Edge Cases

| TC ID | Title | Priority |
|-------|-------|----------|
| TC-EDGE-1.0 | Multiple failed login attempts | High |
| TC-EDGE-1.1 | Concurrent login from different devices | Medium |
| TC-EDGE-1.2 | Direct access to protected URL without login | High |

**Expected Behavior:**
- System handles repeated attempts safely  
- No crash or data corruption  
- Behavior follows defined business rules  

---------------------------------------------------------------------------------------

## Security Testing

| TC ID | Title | Priority |
|-------|-------|----------|
| TC-SEC-1.0 | SQL Injection in password field | High |
| TC-SEC-1.1 | SQL Injection in email field | High |
| TC-SEC-1.2 | Brute force attempt | High |

### Example – SQL Injection TC

**Steps:**
1. Enter valid email  
2. Enter `' OR 1=1 --` in password  
3. Click Login  

**Expected Result:**
- Login rejected  
- No SQL error displayed  
- No sensitive data exposed  

---------------------------------------------------------------------------------------

## Performance Testing

| TC ID | Title | Priority |
|-------|-------|----------|
| TC-PERF-1.0 | Login response time under normal load | Medium |

**Preconditions:**
- System running under normal operating conditions  

**Steps:**
1. Send login request with valid credentials  

**Expected Result:**
- Response time ≤ defined SLA (e.g., 3 seconds)  
- No noticeable delay in redirection  

---

| TC-PERF-1.1 | Login under concurrent users | Medium |

**Preconditions:**
- Multiple users attempting login simultaneously  

**Steps:**
1. Send multiple login requests concurrently  

**Expected Result:**
- System handles requests without crashing  
- No abnormal delay or failure  

---------------------------------------------------------------------------------------

## API Testing

| TC ID | Title | Priority |
|-------|-------|----------|
| TC-API-1.0 | Valid login API request | High |
| TC-API-1.1 | Invalid login API request | High |

### TC-API-1.0

**Steps:**
1. Send POST request to /login endpoint  
2. Provide valid email & password  

**Expected Result:**
- Status Code: 200 OK  
- Response contains authentication token/session data  
- No sensitive internal data exposed  

### TC-API-1.1

**Steps:**
1. Send POST request with invalid credentials  

**Expected Result:**
- Status Code: 401 Unauthorized  
- Generic error message returned  
- No token generated  

---------------------------------------------------------------------------------------

## UI Testing

| TC ID | Title | Priority |
|-------|-------|----------|
| TC-UI-1.0 | Error message placement | Medium |
| TC-UI-1.1 | Login button disabled state | Medium |

### TC-UI-1.0

**Steps:**
1. Trigger validation error  
2. Observe message location  

**Expected Result:**
- Error displayed under relevant field  
- No layout breaking occurs  

---

### TC-UI-1.1

**Steps:**
1. Click Login button  
2. Observe button behavior  

**Expected Result:**
- Button shows loading/disabled state  
- Prevents multiple submissions  

---------------------------------------------------------------------------------------

## Usability Testing

| TC ID | Title | Priority |
|-------|-------|----------|
| TC-USAB-1.0 | Keyboard navigation | Medium |
| TC-USAB-1.1 | Error message clarity | Medium |

### TC-USAB-1.0

**Steps:**
1. Use Tab to navigate fields  

**Expected Result:**
- Logical field navigation order  
- Focus visible on active field  

---

### TC-USAB-1.1

**Steps:**
1. Trigger invalid login  

**Expected Result:**
- Error message is clear and understandable  
- User knows how to fix the issue  

---------------------------------------------------------------------------------------

# 4️⃣ Notes

- All error messages must be generic  
- No stack traces exposed  
- Authentication must follow defined business rules  
- System must comply with security best practices  
