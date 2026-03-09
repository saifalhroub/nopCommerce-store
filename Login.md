# Feature: Login

---

# 1️⃣ User Story

As a customer,  
I want to log in to my account,  
So that I can use the store faster.

---

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

## AC4 – Remember Me

Given the user is on the Login page  
When the user enters valid credentials  
And selects the "Remember Me" option  
And logs in successfully  
Then the system remembers the user session according to the defined persistence rules  
And the user remains authenticated or their email is retained on the next visit (based on business rules)



## AC5 – Login to session timeout account
Given that the user login session timed out  
When the user logs in again  
Then the system accepts the request  
And the user is redirected to the landing page  

---

# 3️⃣ Test Cases

---

# Login - Navigation


| TC ID | Title | Priority | Pre-Conditions | Steps | Expected Results |
|------|------|------|------|------|------|
| **LoginNav-FUNCV-01** | Validate navigation to login page | High | User is on website homepage | 1. Click Login button | User is redirected to login page |

---

# Login - Successful Login



| TC ID | Title | Priority | Pre-Conditions | Steps | Expected Results |
|------|------|------|------|------|------|
| **Login-FUNCV-01** | Login with valid credentials | High | Registered account exists | 1. Enter valid email <br> 2. Enter correct password <br> 3. Click Login | Authentication succeeds <br> Session created <br> User redirected to landing page |
| **RememberMe-FUNCV-02** | Validate Remember Me functionality | Medium | Registered account exists | 1. Enter credentials <br> 2. Enable Remember Me <br> 3. Login <br> 4. Logout <br> 5. Return to login page | Email remains stored according to business rules |
| **Session-FUNCV-03** | Login after session timeout | Medium | Previous session expired | 1. Login again | New session created and user redirected |

---

# Login - Validation


| TC ID | Title | Priority | Pre-Conditions | Steps | Expected Results |
|------|------|------|------|------|------|
| **LoginValidation-FUNCINV-01** | Validate empty fields | Medium | User on login page | 1. Leave fields empty <br> 2. Click Login | Validation messages appear |
| **LoginValidation-FUNCINV-02** | Validate wrong password | High | Registered email exists | 1. Enter valid email <br> 2. Enter wrong password <br> 3. Click Login | Login rejected and generic error displayed |
| **LoginValidation-FUNCINV-03** | Validate invalid email format | High | User on login page | 1. Enter invalid email <br> 2. Enter password <br> 3. Click Login | Email validation message appears |

---

# Login - Edge Cases

| TC ID | Title | Priority | Pre-Conditions | Steps | Expected Results |
|------|------|------|------|------|------|
| **Login-EDGE-01** | Multiple failed login attempts | High | User on login page | 1. Enter wrong password repeatedly | System handles attempts safely |
| **Login-EDGE-02** | Concurrent login from different devices | Medium | Same account used | 1. Login from two devices | System handles sessions according to rules |
| **Login-EDGE-03** | Direct access to protected URL | High | User not logged in | 1. Open protected URL | User redirected to login page |

---

# Login - Security

| TC ID | Title | Priority | Pre-Conditions | Steps | Expected Results |
|------|------|------|------|------|------|
| **Login-SEC-01** | SQL Injection in password field | High | User on login page | 1. Enter valid email <br> 2. Enter `' OR 1=1 --` <br> 3. Click Login | Login rejected and no SQL error shown |
| **Login-SEC-02** | SQL Injection in email field | High | User on login page | 1. Enter SQL payload in email <br> 2. Enter password <br> 3. Click Login | Login rejected |
| **Login-SEC-03** | Brute force login attempt | High | User on login page | 1. Send repeated login attempts | System limits attempts |

---

# Login - Performance

| TC ID | Title | Priority | Pre-Conditions | Steps | Expected Results |
|------|------|------|------|------|------|
| **Login-PERF-01** | Login response time under normal load | Medium | System running normally | 1. Send login request | Response ≤ 3 seconds |
| **Login-PERF-02** | Login under concurrent users | Medium | Multiple users login simultaneously | 1. Send concurrent requests | System handles load without crash |

---

# Login - UI

| TC ID | Title | Priority | Pre-Conditions | Steps | Expected Results |
|------|------|------|------|------|------|
| **Login-UI-01** | Error message placement | Medium | User on login page | 1. Trigger validation error | Error appears under field |
| **Login-UI-02** | Login button disabled state | Medium | User on login page | 1. Click Login | Button shows loading state |
| **Login-UI-03** | Login link state | Medium | User not logged in | 1. Observe header | Login link visible |

---

# Login - Usability

| TC ID | Title | Priority | Pre-Conditions | Steps | Expected Results |
|------|------|------|------|------|------|
| **Login-USB-01** | Keyboard navigation | Medium | User on login page | 1. Navigate with Tab | Focus moves correctly |
| **Login-USB-02** | Error message clarity | Medium | User on login page | 1. Trigger invalid login | Message understandable |

---

# 4️⃣ Notes

- All error messages must be generic  
- No stack traces exposed  
- Authentication must follow defined business rules  
- System must follow security best practices
