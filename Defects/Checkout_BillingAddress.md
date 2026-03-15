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
