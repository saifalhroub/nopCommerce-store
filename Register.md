# Feature: Register

---

## Functional – Valid Scenarios

| TC ID | Title | Priority | Preconditions | Steps | Expected Results |
|------|------|------|------|------|------|
| TC-FUNCV-1.0 | Register with valid data | High | User is on Register page | 1. Fill all mandatory fields with valid data <br> 2. Click Register | 1. Account created successfully <br> 2. Success message displayed <br> 3. User redirected to homepage <br> 4. User session initiated |
| TC-FUNCV-1.1 | Register with minimum allowed password length | Medium | User is on Register page | 1. Enter password with minimum allowed length (e.g., 6 characters) <br> 2. Fill other fields correctly <br> 3. Click Register | 1. Registration succeeds <br> 2. No validation errors appear |
| TC-FUNCV-1.2 | Register with maximum allowed password length | Medium | User is on Register page | 1. Enter password with maximum allowed length (e.g., 64 characters) <br> 2. Fill other fields correctly <br> 3. Click Register | 1. Registration succeeds <br> 2. No system error occurs |

---

## Functional – Invalid Scenarios

| TC ID | Title | Priority | Preconditions | Steps | Expected Results |
|------|------|------|------|------|------|
| TC-FUNCINV-1.0 | Submit with empty mandatory fields | High | User is on Register page | 1. Leave mandatory fields empty <br> 2. Click Register | 1. Required field validation messages appear <br> 2. Submission prevented <br> 3. No account created |
| TC-FUNCINV-1.1 | Password shorter than minimum length | Medium | User is on Register page | 1. Enter password shorter than minimum length <br> 2. Fill other fields correctly <br> 3. Click Register | 1. Validation message displayed <br> 2. Registration blocked |
| TC-FUNCINV-1.2 | Password exceeds maximum length | Medium | User is on Register page | 1. Enter password longer than maximum allowed <br> 2. Fill other fields correctly <br> 3. Click Register | 1. Validation message displayed <br> 2. Registration blocked |
| TC-FUNCINV-1.3 | Password and confirm password mismatch | High | User is on Register page | 1. Enter different values in Password and Confirm Password <br> 2. Fill other fields correctly <br> 3. Click Register | 1. Validation message indicates mismatch <br> 2. Registration blocked |
| TC-FUNCINV-1.4 | Register with existing email | High | Email already exists in system | 1. Enter previously registered email <br> 2. Fill other fields correctly <br> 3. Click Register | 1. Validation message displayed (Email already registered) <br> 2. No duplicate account created |
| TC-FUNCINV-1.5 | Invalid email format | Medium | User is on Register page | 1. Enter invalid email format <br> 2. Fill other fields correctly <br> 3. Click Register | 1. Email validation message displayed <br> 2. Registration blocked |
| TC-FUNCINV-1.6 | Network interruption during registration | Medium | User is on Register page | 1. Fill form with valid data <br> 2. Disable internet connection <br> 3. Click Register | 1. Network error message displayed <br> 2. User remains on Register page <br> 3. No account created |
| TC-FUNCINV-1.7 | Extremely long input in text fields | Low | User is on Register page | 1. Enter a very long string (e.g., 5000 characters) in First Name field <br> 2. Fill other fields correctly <br> 3. Click Register | 1. Validation message displayed or input safely handled <br> 2. System does not crash |
| TC-FUNCINV-1.8 | Special characters or Unicode in fields | Medium | User is on Register page | 1. Enter Unicode characters in name field (e.g., ñ, é, 你好) <br> 2. Fill other fields correctly <br> 3. Click Register | 1. Registration succeeds if supported <br> 2. Data stored correctly |
| TC-FUNCINV-1.9 | Fields containing only whitespace | Medium | User is on Register page | 1. Enter spaces only in mandatory fields <br> 2. Click Register | 1. Validation messages displayed <br> 2. Submission prevented |

---

## Edge Cases

| TC ID | Title | Priority | Preconditions | Steps | Expected Results |
|------|------|------|------|------|------|
| TC-EDGE-1.0 | Multiple rapid clicks on Register button | Medium | User is on Register page | 1. Fill form with valid data <br> 2. Click Register multiple times rapidly | 1. Only one request processed <br> 2. No duplicate accounts created |
| TC-EDGE-1.1 | Concurrent registration using same email | Medium | Two users attempt registration simultaneously | 1. Two users submit registration using the same email at the same time | 1. Only one account created <br> 2. Second request rejected |
| TC-EDGE-1.2 | Form submission after session expiration | Low | Session expired | 1. Fill form <br> 2. Wait until session expires <br> 3. Click Register | 1. System prompts user to refresh session |
| TC-EDGE-1.3 | Browser back button after successful registration | Low | Registration completed | 1. Complete registration <br> 2. Click browser back button | 1. Form resubmission prevented |

---

## Security Testing

| TC ID | Title | Priority | Preconditions | Steps | Expected Results |
|------|------|------|------|------|------|
| TC-SEC-1.0 | SQL Injection attempt in email field | High | User is on Register page | 1. Enter `' OR 1=1 --` in email field <br> 2. Fill other fields correctly <br> 3. Click Register | 1. Input sanitized <br> 2. No database error shown <br> 3. Registration fails safely |
| TC-SEC-1.1 | XSS attempt in name field | Medium | User is on Register page | 1. Enter `<script>alert('XSS')</script>` in First Name field <br> 2. Fill other fields correctly <br> 3. Click Register | 1. Script not executed <br> 2. Input escaped or sanitized |
| TC-SEC-1.2 | Password strength enforcement | High | User is on Register page | 1. Enter weak password <br> 2. Fill other fields <br> 3. Click Register | 1. Password strength validation displayed |
| TC-SEC-1.3 | CSRF protection validation | High | Valid session exists | 1. Attempt registration request without valid CSRF token | 1. Request rejected |

---

## Performance Testing

| TC ID | Title | Priority | Preconditions | Steps | Expected Results |
|------|------|------|------|------|------|
| TC-PERF-1.0 | Registration response time under normal load | Medium | System operational | 1. Register using valid data | 1. Response time within acceptable limit (e.g., ≤5 seconds) |
| TC-PERF-1.1 | Concurrent user registrations | High | Load testing environment available | 1. Simulate 100 users registering simultaneously | 1. System processes requests without crashing |
| TC-PERF-1.2 | Peak load registration stress test | Medium | Load testing environment | 1. Simulate heavy load on registration endpoint | 1. System remains stable |

---

## UI Testing

| TC ID | Title | Priority | Preconditions | Steps | Expected Results |
|------|------|------|------|------|------|
| TC-UI-1.0 | Validation message placement | Medium | User is on Register page | 1. Submit form with invalid data | 1. Error messages appear under corresponding fields |
| TC-UI-1.1 | Register button state during submission | Medium | User is on Register page | 1. Fill form <br> 2. Click Register | 1. Button disabled during submission |
| TC-UI-1.2 | Responsive layout on different screen sizes | Medium | Register page open | 1. Open page on desktop, tablet, mobile | 1. Layout adapts correctly |
| TC-UI-1.3 | Cross-browser compatibility | Medium | Different browsers available | 1. Open Register page on Chrome, Firefox, Edge, Safari | 1. Page layout and functionality consistent |

---

---

## API Testing

| TC ID | Title | Priority | Preconditions | Steps | Expected Results |
|------|------|------|------|------|------|
| TC-API-1.0 | Register via API with valid data | High | API endpoint `/register` available | 1. Send POST request to /register <br> 2. Provide valid registration data | 1. Status code 201 Created <br> 2. Response contains user ID <br> 3. Password not returned <br> 4. User stored in database |
| TC-API-1.1 | Register via API with invalid data | High | API endpoint available | 1. Send POST request with invalid fields | 1. Status code 400 Bad Request <br> 2. Validation error returned <br> 3. No user created |
| TC-API-1.2 | Register via API with missing fields | Medium | API endpoint available | 1. Send POST request without mandatory fields | 1. Status code 400 returned <br> 2. Validation message indicates missing fields |
| TC-API-1.3 | API response does not expose password | High | API endpoint available | 1. Send valid registration request | 1. Response body excludes password field |

---

## Usability Testing

| TC ID | Title | Priority | Preconditions | Steps | Expected Results |
|------|------|------|------|------|------|
| TC-USAB-1.0 | Keyboard navigation through form | Medium | Register page open | 1. Navigate form using Tab key | 1. Logical field order <br> 2. Focus visible |
| TC-USAB-1.1 | Mandatory fields clearly indicated | High | Register page open | 1. Inspect form labels | 1. Required fields clearly marked |
| TC-USAB-1.2 | Screen reader compatibility | Medium | Screen reader enabled | 1. Navigate form with screen reader | 1. Fields announced correctly <br> 2. Error messages read aloud |
| TC-USAB-1.3 | Error message color contrast | Medium | Register page open | 1. Trigger validation errors | 1. Error messages meet WCAG contrast standards |

---

