# Defect Reports

---

## Defect Template

---

**Defect ID:**  
**Application Name:** nopCommerce  
**Functionality:**  
**TC-ID:**  
**Defect Type:**  
**Severity:**  
**Priority:**  
**Status:** Open  
**Reporter:** Saifullah Abdullah Mohammad Alhroub  

---

## Defect Title:

---

## Steps to Reproduce:

1.
2.
3.

---

## Expected Result:

---

## Actual Result:

---

## Environment:

- OS:
- Browser:
- Device:
- Environment URL:
- Build Version (if available):


--------------------------------------------------------

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

-------------------------------------------------------------------------

**Defect ID:** DF-02  
**Application Name:** nopCommerce  
**Functionality:** My Account → Address  
**TC-ID:** ADDRESS-FUNCV-03  
**Defect Type:** UI, Functional  
**Severity:** Medium  
**Priority:** Medium  
**Status:** Open  
**Reporter:** Saifullah Abdullah Mohammad Alhroub  

---

## Defect Title:

My Account → Address → State/Province field is not marked as required but the system blocks address submission

---

## Steps to Reproduce:

1. Navigate to My Account page
2. Select the Address section
3. Click on the "Add New" button
4. Fill all mandatory fields with valid data
5. Select a country where the State/Province has options (e.g., USA / Armenia)
6. Leave all optional fields empty

---

## Expected Result:

- The system accepts the request and saves the address successfully

---

## Actual Result:

- The system rejects the request to add the new address
- The user remains on the address page and a validation error message appears indicating:
  “State/Province is required”

---

## Environment:

- OS: Windows 10
- Browser: Chrome
- Device: Laptop HP
- Environment URL: https://demo.nopcommerce.com/customer/addressadd
- Build Version (if available): N/A

-------------------------------------------------------------------------

**Defect ID:** DF-03  
**Application Name:** nopCommerce  
**Functionality:** Checkout → Billing Address  
**TC-ID:** BILL.SHPP-FUNC-03  
**Defect Type:** UI, Functional  
**Severity:** Medium  
**Priority:** Medium  
**Status:** Open  
**Reporter:** Saifullah Abdullah Mohammad Alhroub  

---

## Defect Title:

Checkout → Billing Address → State/Province field is not marked as required but the system blocks address submission

---

## Steps to Reproduce:

1. Navigate to the checkout page
2. Add a new billing address
3. Fill all mandatory fields with valid data
4. Select a country where the State/Province has options (e.g., USA / Armenia)
5. Leave all optional fields empty

---

## Expected Result:

- The system accepts the request and saves the address successfully
- The user is redirected to the shipping address form

---

## Actual Result:

- The system rejects the request to add the new address
- The user remains on the billing address form and a validation error message appears indicating:
  “State/Province is required”

---

## Environment:

- OS: Windows 10
- Browser: Chrome
- Device: Laptop HP
- Environment URL: https://demo.nopcommerce.com/customer/addressadd
- Build Version (if available): N/A

-------------------------------------------------------------------------

**Defect ID:** DF-04  
**Application Name:** nopCommerce  
**Functionality:** Checkout → Shipping Address  
**TC-ID:** BILL.SHPP-FUNC-03  
**Defect Type:** UI, Functional  
**Severity:** Medium  
**Priority:** Medium  
**Status:** Open  
**Reporter:** Saifullah Abdullah Mohammad Alhroub  

---

## Defect Title:

Checkout → Shipping Address → State/Province field is not marked as required but the system blocks address submission

---

## Steps to Reproduce:

1. Navigate to the checkout page
2. Add a new shipping address
3. Fill all mandatory fields with valid data
4. Select a country where the State/Province has options (e.g., USA / Armenia)
5. Leave all optional fields empty

---

## Expected Result:

- The system accepts the request and saves the address successfully
- The user is redirected to the shipping method step

---

## Actual Result:

- The system rejects the request to add the new address
- The user remains on the shipping address form and a validation error message appears indicating:
  “State/Province is required”

---

## Environment:

- OS: Windows 10
- Browser: Chrome
- Device: Laptop HP
- Environment URL: https://demo.nopcommerce.com/customer/addressadd
- Build Version (if available): N/A

-------------------------------------------------------------------------

**Defect ID:** DF-05  
**Application Name:** nopCommerce  
**Functionality:** Login → Forgot Password  
**TC-ID:** Login-UI-04  
**Defect Type:** UI  
**Severity:** Low  
**Priority:** Low  
**Status:** Open  
**Reporter:** Saifullah Abdullah Mohammad Alhroub  

---

## Defect Title:

Login Page – "Forgot password?" link is misaligned with other login elements

---

## Steps to Reproduce:

1. Navigate to https://demo.nopcommerce.com/login?returnUrl=%2F
2. Observe the alignment of the login form elements

---

## Expected Result:

- All elements are aligned correctly
- No visual inconsistency between login form elements

---

## Actual Result:

- The "Forgot password?" link is not aligned properly with the other login elements

---

## Environment:

- OS: Windows 10
- Browser: Chrome
- Device: Laptop HP
- Environment URL: https://demo.nopcommerce.com/login?returnUrl=%2F
- Build Version (if available): N/A

![Forgot_Password bug](../images/login-alignment.png)
--------------------------------------------------------

**Defect ID:** DF-06  
**Application Name:** nopCommerce  
**Functionality:** Checkout → Payment → Credit Card  
**TC-ID:** Payment.CC-UI-01  
**Defect Type:** UI  
**Severity:** Low  
**Priority:** Low  
**Status:** Open  
**Reporter:** Saifullah Abdullah Mohammad Alhroub  

---

## Defect Title:

Checkout → Payment (Credit Card) → Mandatory fields are not indicated with visual markers (e.g., *)

---

## Steps to Reproduce:

1. Navigate to the checkout page
2. Select "Credit Card" as the payment method
3. Observe the credit card form fields

---

## Expected Result:

- Mandatory fields should be clearly indicated to the user (e.g., using * symbol or another visual indicator)

---

## Actual Result:

- None of the credit card fields are marked as mandatory or optional

---

## Environment:

- OS: Windows 10
- Browser: Chrome
- Device: Laptop HP
- Environment URL: --
- Build Version (if available): N/A

--------------------------------------------------------
