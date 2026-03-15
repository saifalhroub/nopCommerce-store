# Feature: Login

---

# 1️⃣ User Story

As a customer,  
I want to log in to my account,  
So that I can access my account and use the store faster.

---

# 2️⃣ Acceptance Criteria (BDD)

## AC1 – Navigation
Given the user is on the website  
When the user clicks on the Login button  
Then the user is redirected to the Login page  

---

## AC2 – Successful Login
Given the user is on the Login page  
When the user enters a valid registered email and password  
Then the system authenticates the user  
And a session/token is generated  
And the user is redirected to the landing page  

---

## AC3 – Validation
Given the user is on the Login page  
When the user submits invalid or missing data  
Then the login request is rejected  
And a proper validation message appears  
And no session/token is created  

---

## AC4 – Remember Me
Given the user is on the Login page  
When the user enters valid credentials  
And selects the "Remember Me" option  
And logs in successfully  
Then the system remembers the user session according to the defined persistence rules  

---

## AC5 – Login after session timeout
Given the user's previous session has timed out  
When the user logs in again  
Then the system authenticates the user  
And creates a new session  
And redirects the user to the landing page  

---

# 3️⃣ Test Cases

---

# Login – Navigation

| TC ID | Title | Priority | Pre-Conditions | Steps | Expected Results |
|------|------|------|------|------|------|
| **LoginNav-FUNCV-01** | Validate navigation to login page | High | User is on website homepage | 1. Click Login button | User is redirected to the login page successfully |

---

# Login – Successful Login

| TC ID | Title | Priority | Pre-Conditions | Steps | Expected Results |
|------|------|------|------|------|------|
| **Login-FUNCV-01** | Validate login with valid credentials | High | Registered account exists | 1. Enter valid email <br> 2. Enter correct password <br> 3. Click Login | User is authenticated successfully <br> Session is created <br> User is redirected to the landing page |
| **Session-FUNCV-02** | Validate login after session timeout | Medium | Previous session expired | 1. Enter valid credentials <br> 2. Click Login | System authenticates the user and creates a new session |

---

# Login – Remember Me

| TC ID | Title | Priority | Pre-Conditions | Steps | Expected Results |
|------|------|------|------|------|------|
| **RememberMe-FUNCV-01** | Validate Remember Me functionality | Medium | Registered account exists | 1. Enter credentials <br> 2. Enable Remember Me <br> 3. Login <br> 4. Logout <br> 5. Return to login page | System remembers the user according to persistence rules (email retained or session persisted based on business logic) |

---

# Login – Validation

| TC ID | Title | Priority | Pre-Conditions | Steps | Expected Results |
|------|------|------|------|------|------|
| **LoginValidation-FUNCINV-01** | Validate empty login fields | Medium | User on login page | 1. Leave fields empty <br> 2. Click Login | Validation messages appear for required fields |
| **LoginValidation-FUNCINV-02** | Validate login with wrong password | High | Registered email exists | 1. Enter valid email <br> 2. Enter wrong password <br> 3. Click Login | Login request is rejected and a generic error message appears |
| **LoginValidation-FUNCINV-03** | Validate invalid email format | High | User on login page | 1. Enter invalid email format <br> 2. Enter password <br> 3. Click Login | Email format validation message appears |

---

# Login – Edge Cases

| TC ID | Title | Priority | Pre-Conditions | Steps | Expected Results |
|------|------|------|------|------|------|
| **Login-EDGE-01** | Validate multiple failed login attempts handling | High | User on login page | 1. Enter wrong password repeatedly | System limits login attempts according to security policy |
| **Login-EDGE-02** | Validate concurrent login from different devices | Medium | Same account used | 1. Login from two different devices | System handles sessions according to defined session management rules |
| **Login-EDGE-03** | Validate direct access to protected URL | High | User not logged in | 1. Open protected URL directly | User is redirected to the login page |
| **Login-EDGE-04** | Validate login with leading and trailing spaces | Medium | Registered account exists | 1. Enter email/password with spaces before or after | System trims spaces and processes login correctly |
| **Login-EDGE-05** | Validate rapid multiple login requests | Medium | User on login page | 1. Click login button multiple times rapidly | System processes the request safely without duplicate sessions |

---

# Login – Security

| TC ID | Title | Priority | Pre-Conditions | Steps | Expected Results |
|------|------|------|------|------|------|
| **Login-SEC-01** | Validate SQL injection prevention in password field | High | User on login page | 1. Enter valid email <br> 2. Enter `' OR 1=1 --` <br> 3. Click Login | Login is rejected and no database error is exposed |
| **Login-SEC-02** | Validate SQL injection prevention in email field | High | User on login page | 1. Enter SQL payload in email <br> 2. Enter password <br> 3. Click Login | Login request is rejected |
| **Login-SEC-03** | Validate brute force login protection | High | User on login page | 1. Perform repeated login attempts | System detects and limits excessive login attempts |

---

# Login – Performance

| TC ID | Title | Priority | Pre-Conditions | Steps | Expected Results |
|------|------|------|------|------|------|
| **Login-PERF-01** | Validate login response time under normal load | Medium | System running normally | 1. Send login request | System responds within acceptable response time (≤ 3 seconds) |
| **Login-PERF-02** | Validate login under 3G throttled network | Medium | 3G throttling enabled | 1. Send login request | User logs in successfully and system responds without errors despite slow network |

---

# Login – UI

| TC ID | Title | Priority | Pre-Conditions | Steps | Expected Results |
|------|------|------|------|------|------|
| **Login-UI-01** | Validate error message placement | Medium | User on login page | 1. Trigger validation error | Error message appears clearly under the related field |
| **Login-UI-02** | Validate login button loading state | Medium | User on login page | 1. Click Login | Login button shows loading state while request is processed |
| **Login-UI-03** | Validate login link visibility | Medium | User not logged in | 1. Observe header | Login link is visible and accessible |
| **Login-UI-04** | Validate login form layout and alignment | Medium | Login page loaded | Observe form layout | All login form elements appear properly aligned with no overlapping |

---

# Login – Usability

| TC ID | Title | Priority | Pre-Conditions | Steps | Expected Results |
|------|------|------|------|------|------|
| **Login-USB-01** | Validate keyboard navigation | Medium | User on login page | 1. Press Tab to move forward <br> 2. Press Shift+Tab to move backward <br> 3. Press Enter to submit | Focus moves correctly between fields and login can be submitted |
| **Login-USB-02** | Validate clarity of error messages | Medium | User on login page | 1. Trigger invalid login | Error message is clear and understandable |
| **Login-USB-03** | Validate copy and paste in login fields | Low | User copied login data | 1. Paste email/password into fields | System accepts pasted data and displays it correctly |

---

# 4️⃣ Notes

- All authentication error messages must be **generic**
- No **stack traces** or internal errors should be exposed
- Authentication must follow **security best practices**
- Session management must follow **defined business rules**
