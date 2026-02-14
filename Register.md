# Feature: Register

---

## 1️⃣ User Story

As a user,  
I want to register an account,  
So that I can shop faster.

---

## 2️⃣ Acceptance Criteria (BDD)

### AC1 – Successful Registration
Given the user is on the Register page  
When the user enters valid data in all mandatory fields  
And clicks on the Register button  
Then the account is created successfully  
And a success message is displayed  
And the user is redirected to the homepage  
And the user record is stored  
And a user session is initiated  

### AC2 – Invalid Data Handling
Given the user is on the Register page  
When the user submits the form with missing or invalid data  
Then validation messages are displayed under corresponding fields  
And submission is prevented  
And no account is created  
And no user record is stored  

---

## 3️⃣ Test Cases

### Functional – Valid Scenarios

| TC ID          | Title                                      | Priority | Preconditions            |
|----------------|--------------------------------------------|----------|--------------------------|
| TC-FUNCV-1.0   | Register with valid data                   | High     | User is on Register page |

**Steps:**
1. Fill all mandatory fields with valid data  
2. Click Register  

**Expected Result:**
- Account is created successfully  
- Success message displayed  
- User redirected to homepage  
- User session is active  

---

| TC ID          | Title                                      | Priority | Preconditions            |
|----------------|--------------------------------------------|----------|--------------------------|
| TC-FUNCV-1.1   | Register with minimum allowed password length | Medium   | On Register page         |

**Steps:**
1. Enter password with minimum allowed length (e.g., 6 characters)  
2. Fill other fields correctly  
3. Click Register  

**Expected Result:**
- Registration succeeds  
- No validation errors appear  

---

| TC ID          | Title                                      | Priority | Preconditions            |
|----------------|--------------------------------------------|----------|--------------------------|
| TC-FUNCV-1.2   | Register with maximum allowed password length | Medium   | On Register page         |

**Steps:**
1. Enter password with maximum allowed length (e.g., 64 characters)  
2. Fill other fields correctly  
3. Click Register  

**Expected Result:**
- Registration succeeds  
- No system error occurs  

---

### Functional – Invalid Scenarios

| TC ID            | Title                                        | Priority | Preconditions                      |
|------------------|----------------------------------------------|----------|------------------------------------|
| TC-FUNCINV-1.0   | Submit with empty mandatory fields           | High     | On Register page                   |

**Steps:**
1. Leave mandatory fields empty  
2. Click Register  

**Expected Result:**
- Required field messages appear  
- Submission prevented  
- No account created  

---

| TC ID            | Title                                        | Priority | Preconditions                      |
|------------------|----------------------------------------------|----------|------------------------------------|
| TC-FUNCINV-1.1   | Password shorter than minimum length         | Medium   | On Register page                   |

**Steps:**
1. Enter password shorter than allowed minimum  
2. Fill other fields correctly  
3. Click Register  

**Expected Result:**
- Validation message displayed  
- Registration blocked  

---

| TC ID            | Title                                        | Priority | Preconditions                      |
|------------------|----------------------------------------------|----------|------------------------------------|
| TC-FUNCINV-1.2   | Password exceeds maximum length              | Medium   | On Register page                   |

**Steps:**
1. Enter password longer than allowed maximum  
2. Fill other fields correctly  
3. Click Register  

**Expected Result:**
- Validation message displayed  
- Registration blocked  

---

| TC ID            | Title                                        | Priority | Preconditions                      |
|------------------|----------------------------------------------|----------|------------------------------------|
| TC-FUNCINV-1.3   | Password and confirm password mismatch       | High     | On Register page                   |

**Steps:**
1. Enter different values in Password and Confirm Password  
2. Fill other fields correctly  
3. Click Register  

**Expected Result:**
- Validation message indicates mismatch  
- Registration blocked  

---

| TC ID            | Title                                        | Priority | Preconditions                      |
|------------------|----------------------------------------------|----------|------------------------------------|
| TC-FUNCINV-1.4   | Register with existing email                 | High     | Email already registered            |

**Steps:**
1. Enter already registered email  
2. Fill other fields correctly  
3. Click Register  

**Expected Result:**
- Proper validation message displayed (e.g., "Email is already registered")  
- No duplicate account created  

---

| TC ID            | Title                                        | Priority | Preconditions                      |
|------------------|----------------------------------------------|----------|------------------------------------|
| TC-FUNCINV-1.5   | Invalid email format                         | Medium   | On Register page                   |

**Steps:**
1. Enter invalid email format  
2. Fill other fields correctly  
3. Click Register  

**Expected Result:**
- Email format validation displayed  
- Registration blocked  

---

| TC ID            | Title                                        | Priority | Preconditions                      |
|------------------|----------------------------------------------|----------|------------------------------------|
| TC-FUNCINV-1.6   | Network interruption during submission       | Medium   | On Register page                   |

**Steps:**
1. Fill form with valid data  
2. Disable internet connection  
3. Click Register  

**Expected Result:**
- Network error message displayed  
- User remains on Register page  
- No account created  

---

| TC ID            | Title                                        | Priority | Preconditions                      |
|------------------|----------------------------------------------|----------|------------------------------------|
| TC-FUNCINV-1.7   | Extremely long input in text fields          | Low      | On Register page                   |

**Steps:**
1. Enter a very long string (e.g., 5000 characters) in First Name field  
2. Fill other fields correctly  
3. Click Register  

**Expected Result:**
- Validation message displayed (if limit enforced)  
- Or system truncates input safely  
- No crash or database error  

---

| TC ID            | Title                                        | Priority | Preconditions                      |
|------------------|----------------------------------------------|----------|------------------------------------|
| TC-FUNCINV-1.8   | Special characters and Unicode in fields     | Medium   | On Register page                   |

**Steps:**
1. Enter name with Unicode characters (e.g., 你好, ñ, é)  
2. Fill other fields correctly  
3. Click Register  

**Expected Result:**
- Registration succeeds (if supported)  
- Data stored correctly without corruption  

---

| TC ID            | Title                                        | Priority | Preconditions                      |
|------------------|----------------------------------------------|----------|------------------------------------|
| TC-FUNCINV-1.9   | Fields containing only whitespace            | Medium   | On Register page                   |

**Steps:**
1. Enter spaces only in mandatory fields  
2. Click Register  

**Expected Result:**
- Validation messages indicating fields are required  
- Submission prevented  

---

### Edge Cases

| TC ID        | Title                                          | Priority |
|--------------|------------------------------------------------|----------|
| TC-EDGE-1.0  | Multiple rapid clicks on Register              | Medium   |
| TC-EDGE-1.1  | Concurrent registration using same email       | Medium   |
| TC-EDGE-1.2  | Form submission after session expiration       | Low      |
| TC-EDGE-1.3  | Browser back button after successful registration | Low   |

**Expected Behavior:**
- Only one request processed  
- No duplicate records created (unique constraint on email prevents duplicate)  
- Proper validation or session message shown  
- After successful registration, clicking back should not allow resubmission or show stale page  

---

### Security Testing

| TC ID        | Title                                            | Priority |
|--------------|--------------------------------------------------|----------|
| TC-SEC-1.0   | SQL Injection attempt in email field             | High     |
| TC-SEC-1.1   | SQL Injection attempt in password field          | High     |
| TC-SEC-1.2   | No sensitive data exposure in validation messages| High     |
| TC-SEC-1.3   | XSS attempt in name fields                       | Medium   |
| TC-SEC-1.4   | Password strength enforcement                    | High     |
| TC-SEC-1.5   | CSRF protection on registration form             | High     |

**Example – SQL Injection**

**Steps:**
1. Enter `' OR 1=1 --` in email field  
2. Fill other fields correctly  
3. Click Register  

**Expected Result:**
- Input sanitized  
- No database error displayed  
- Registration fails safely  

**Example – XSS**

**Steps:**
1. Enter `<script>alert('XSS')</script>` in First Name field  
2. Fill other fields correctly  
3. Click Register  

**Expected Result:**
- Input escaped or sanitized  
- Script does not execute in browser  
- Data stored safely  

---

### Performance Testing

| TC ID        | Title                                                | Priority |
|--------------|------------------------------------------------------|----------|
| TC-PERF-1.0  | Registration response time under normal load         | Medium   |
| TC-PERF-1.1  | Concurrent user registrations (simulated load)       | High     |
| TC-PERF-1.2  | System behavior under peak load (stress test)        | Medium   |

**TC-PERF-1.1 – Concurrent Registrations**

**Steps:**
1. Simulate 100 users attempting to register simultaneously with unique valid data (using load testing tool)  
2. Monitor server response times and error rates  

**Expected Result:**
- Response times remain within SLA (e.g., ≤ 5 seconds)  
- No server crashes or database deadlocks  
- All requests are processed correctly (or rate-limiting applied)  

*Note: This test should be performed in a staging environment, not on production.*

---

### API Testing

| TC ID        | Title                                      | Priority |
|--------------|--------------------------------------------|----------|
| TC-API-1.0   | Register via API with valid data           | High     |
| TC-API-1.1   | Register via API with invalid data         | High     |
| TC-API-1.2   | API response does not contain password     | High     |
| TC-API-1.3   | Register via API with missing fields       | Medium   |

**TC-API-1.0**

**Steps:**
1. Send POST request to /register endpoint  
2. Provide valid registration data  

**Expected Result:**
- Status Code: 201 Created  
- Response body contains user ID and success message (password excluded)  
- User record stored in database  

**TC-API-1.1**

**Steps:**
1. Send POST request with invalid or empty data  

**Expected Result:**
- Status Code: 400 Bad Request  
- Validation error details in response  
- No user created  

---

### UI Testing

| TC ID        | Title                                      | Priority | Preconditions               |
|--------------|--------------------------------------------|----------|-----------------------------|
| TC-UI-1.0    | Validation message placement               | Medium   | On Register page            |
| TC-UI-1.1    | Register button state during submission    | Medium   | On Register page            |
| TC-UI-1.2    | Responsive layout                          | Medium   | On Register page            |
| TC-UI-1.3    | Field state after correction               | Medium   | Validation error triggered  |
| TC-UI-1.4    | Register link visibility (guest state)     | Medium   | User not logged in          |
| TC-UI-1.5    | Cross-browser compatibility                | Medium   | Chrome, Firefox, Safari, Edge |

**TC-UI-1.5 – Cross-browser Compatibility**

**Steps:**
1. Open Register page in latest Chrome  
2. Open Register page in latest Firefox  
3. Open Register page in latest Safari  
4. Open Register page in latest Edge  

**Expected Result:**
- Layout consistent across browsers  
- All functionalities work  
- No JavaScript errors  

---

### Usability Testing

| TC ID         | Title                                      | Priority |
|---------------|--------------------------------------------|----------|
| TC-USAB-1.0   | Keyboard navigation                        | Medium   |
| TC-USAB-1.1   | Form clarity and mandatory field indication| High     |
| TC-USAB-1.2   | Screen reader compatibility                | Medium   |
| TC-USAB-1.3   | Color contrast for error messages          | Medium   |

**TC-USAB-1.2 – Screen Reader Compatibility**

**Steps:**
1. Enable screen reader (e.g., NVDA, VoiceOver)  
2. Navigate through the registration form  

**Expected Result:**
- All fields are announced with their labels  
- Error messages are read when they appear  
- Focus management is logical  

**TC-USAB-1.3 – Color Contrast**

**Steps:**
1. Trigger validation errors  
2. Inspect error message colors using contrast analyzer  

**Expected Result:**
- Text meets WCAG AA contrast ratio (4.5:1 for normal text)  
- Error messages are distinguishable without relying solely on color  

---

### Integration Testing

| TC ID        | Title                                          | Priority |
|--------------|------------------------------------------------|----------|
| TC-INT-1.0   | Activation email sent after registration       | High     |
| TC-INT-1.1   | Activation link expiration                     | Medium   |
| TC-INT-1.2   | Email delivery failure handling                | Medium   |

**TC-INT-1.0 – Activation Email**

**Steps:**
1. Register with valid data  
2. Check email inbox of the registered address  

**Expected Result:**
- Activation email is received within a reasonable time  
- Email contains correct activation link  

**TC-INT-1.1 – Activation Link Expiration**

**Steps:**
1. Register and wait beyond the expiration time (e.g., 24 hours)  
2. Click activation link  

**Expected Result:**
- Link shows expired message  
- Option to request new activation email  

---

### Rollback & Recovery Testing

| TC ID        | Title                                          | Priority |
|--------------|------------------------------------------------|----------|
| TC-REC-1.0   | Database failure during registration           | Medium   |
| TC-REC-1.1   | Partial failure in transactional process       | Low      |

**TC-REC-1.0 – Database Failure**

**Steps:**
1. Simulate database unavailability at the moment of submission  
2. Fill form with valid data and click Register  

**Expected Result:**
- User-friendly error message displayed  
- No inconsistent state created (e.g., half-created user)  
- System logs the error appropriately  

---

### Logging & Monitoring

| TC ID        | Title                                          | Priority |
|--------------|------------------------------------------------|----------|
| TC-LOG-1.0   | Successful registration logged                  | Medium   |
| TC-LOG-1.1   | Failed registration attempts logged             | Medium   |
| TC-LOG-1.2   | No sensitive data in logs                       | High     |

**TC-LOG-1.0**

**Steps:**
1. Register successfully  
2. Check application logs  

**Expected Result:**
- Log entry with user ID, timestamp, and action type  
- Password not present in logs  

---

## 4️⃣ Notes

- All validation messages must be clear and generic, avoiding disclosure of system internals.  
- Password must never be stored or returned in plain text.  
- No internal system data (e.g., stack traces) should be exposed to the client.  
- Registration must comply with defined business rules (e.g., minimum age, terms acceptance).  
- For performance tests (especially concurrent user registrations), use a dedicated test environment that mirrors production but does not affect live data.  
- Ensure that email sending is mocked or tested in a sandbox to avoid spamming real users during testing.  
- All security tests should be conducted ethically and within the scope of the testing agreement.  
- Data used in tests should be either randomly generated or from a test dataset that is reset after each test run.  
- Consider automating regression tests for critical paths (e.g., successful registration, validation errors).  
- Remember to test with different user roles if applicable (e.g., guest, existing user).  
