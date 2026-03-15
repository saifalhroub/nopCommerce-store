# Defect Reports

---

## Defect Template

---

**Defect ID:**  
**Application Name:* nopCommerce  
**Functionality:**  
**TC-ID:**  
**Defect Type:**  
**Severity:**  
**Priority:**  
**Status:** Open  
**Reporter:** Saifullah Abdullah Mohammad Alhroub  
**Reported Date:**  

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

> Login --> Session out --> User cannot log in again after session timeout and receives wrong email validation error

---



## Steps to Reproduce:

1. Navigate to the nopCommerce login page
2. Log in to a registered account
3. Wait till the session times out
4. Log in to the same account


---

## Expected Result:

- The system accepts the login request 
  
---

## Actual Result:

- The system prevents the user from logging in to the session-timed-out account
- The system redirects the user to the login page
- And a wrong email validation error message appears
  
---

## Environment:

- OS: Windows 10
- Browser: Chrome
- Device: Laptop HP
- Environment URL: https://demo.nopcommerce.com/login?returnUrl=%2F
- Build Version (if available): N/A

-------------------------------------------------------------------------

**Defect ID:** DF-02
**Application Name:* nopCommerce  
**Functionality:** My account - Adress
**TC-ID:** ADDRESS-FUNCV-03
**Defect Type:** UI, Functional
**Severity:**  low  
**Priority:**  low
**Status:** Open  
**Reporter:** Saifullah Abdullah Mohammad Alhroub  

---

## Defect Title:
 My account --> Address --> state/province --> The State/Province field is not marked as required but the system blocks address submission
 
---

## Steps to Reproduce:

1. Navigate to my account page
2. Select the address 
3. Click on the " Add New " button
4. Fill all mandatory fields with valid data
5. Select a country where the State/Province has options. (e.g., USA / Armenia )
6. Leave all optional fields empty

---

## Expected Result:

  - The system accepts the request and saves the address successfully
---

## Actual Result:

 - The system rejects the request to add the new address.
 - The user remains on the address page and a validation error message appears indicating:
--> “State/Province is required”.

---

## Environment:

- OS: Windows 10   
- Browser: Chrome
- Device: Laptop HP
- Environment URL: https://demo.nopcommerce.com/customer/addressadd
- Build Version (if available): N/A


-------------------------------------------------------------------------

**Defect ID:** DF-03
**Application Name:* nopCommerce  
**Functionality:** Checkout --> Billing Adress
**TC-ID:** BILL.SHPP-FUNC-03
**Defect Type:** UI, Functional
**Severity:**  low  
**Priority:**  low
**Status:** Open  
**Reporter:** Saifullah Abdullah Mohammad Alhroub  

---

## TC :

## Defect Title:
 Checkout --> Billing Address --> state/province --> The State/Province field is not marked as required, but the system blocks address submission
 
---

## Steps to Reproduce:

1. Navigate to the checkout page
2. Add a new billing address
3. Fill all mandatory fields with valid data
4. Select a country where the State/Province has options. (e.g., USA / Armenia )
5. Leave all optional fields empty

---

## Expected Result:

  - The system accepts the request and saves the address successfully
  - The user is redirected to the shipping address form
---

## Actual Result:

 - The system rejects the request to add the new address.
 - The user remains on the billing address form, and a validation error message appears indicating:
--> “State/Province is required”.

---

## Environment:

- OS: Windows 10   
- Browser: Chrome
- Device: Laptop HP
- Environment URL: https://demo.nopcommerce.com/customer/addressadd
- Build Version (if available): N/A


-------------------------------------------------------------------------

**Defect ID:** DF-04
**Application Name:* nopCommerce  
**Functionality:** Checkout --> Shipping Adress
**TC-ID:** BILL.SHPP-FUNC-03
**Defect Type:** UI, Functional
**Severity:**  low  
**Priority:**  low
**Status:** Open  
**Reporter:** Saifullah Abdullah Mohammad Alhroub  

---


## Defect Title:
 Checkout --> Shipping Address --> state/province --> The State/Province field is not marked as required but the system blocks address submission
 
---

## Steps to Reproduce:

1. Navigate to the checkout page
2. Add new shipping address
3. Fill all mandatory fields with valid data
4. Select a country where the State/Province has options. (e.g., USA / Armenia )
5. Leave all optional fields empty

---

## Expected Result:

  - The system accepts the request and saves the address successfully
  - The user is redirected to the shipping address form
---

## Actual Result:

 - The system rejects the request to add the new address.
 - The user remains on the billing address form and a validation error message appears indicating:
--> “State/Province is required”.

---

## Environment:

- OS: Windows 10   
- Browser: Chrome
- Device: Laptop HP
- Environment URL: https://demo.nopcommerce.com/customer/addressadd
- Build Version (if available): N/A

-------------------------------------------------------------------------



**Defect ID:**  DF-05
**Application Name:* nopCommerce  
**Functionality:** Login --> Forgot Password
**TC-ID:**  **Login-UI-04**
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
2. Observe the form's elements' alignment


---

## Expected Result:

   - All elements aligned correctly
   - No overlapping between the login elements
     
 ---

## Actual Result:

   - The forgot password link is not aligned correctly
     
---

## Environment:

- OS: Windows 10
- Browser: Chrome
- Device: Laptop HP 
- Environment URL: https://demo.nopcommerce.com/login?returnUrl=%2F
- Build Version (if available): 


--------------------------------------------------------
