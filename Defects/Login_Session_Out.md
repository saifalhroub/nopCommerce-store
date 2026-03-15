**Defect ID:** DF-01  
**Application Name:** nopCommerce  
**Functionality:** Login  
**TC-ID:** RememberMe-FUNCV-03  
**Defect Type:** Functional  
**Severity:** High  
**Priority:** High  
**Status:** Open  
**Reporter:** Saifullah Abdullah Mohammad Alhroub  

---

## Defect Title:

Login → Session timeout → User cannot log in again after session timeout and receives incorrect email validation error

---

## Steps to Reproduce:

1. Navigate to the nopCommerce login page
2. Log in to a registered account
3. Wait until the session times out
4. Log in again using the same account

---

## Expected Result:

- The system accepts the login request successfully

---

## Actual Result:

- The system prevents the user from logging in after the session timeout
- The system redirects the user to the login page
- An incorrect email validation error message appears

---

## Environment:

- OS: Windows 10
- Browser: Chrome
- Device: Laptop HP
- Environment URL: https://demo.nopcommerce.com/login?returnUrl=%2F
- Build Version (if available): N/A
