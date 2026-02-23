# Order Information page

> As a user,
> I want an order information page
> So I can control and monitor my order status

---

## AC - Order information components
Given the user has submitted an order 
When the user is on the order information page
Then the user will see:
  - Print button
  - PDF Invoice button
  - Cancel order button
  - Order Number
  - Order Date
  - Order Status
  - Order total, subtotal, tax, shipping & gift wrapping price
  - Billing Address
  - Shipping Address
  - Payment informations
  - Shipping method and price
  - Products
  - Reorder button

---
    
## AC - Order Cancelation
Given the user has submitted an order
When the user clicks on cancel order
Then the order will be cancelled

---

## AC - Print informatiom
Given the user is on the order information page
When the user clicks on the Print button
Then a new tap will be opened 
And the print settings will show up
And the user can print the order information document

---

## AC - PDF Invoice
Given the user is on the order information page
When the user clicks on the PDF Invoice button
Then the order information will be downloaded as PDF

---

## AC - Reorder 
Given the user wants to reorder the same order
When the user is on the order information page
Then the user can use the reorder button 

---

# Functional Positive

| TC ID | Title | Priority | Preconditions | Steps | Expected Results |
| --- | --- | --- | --- | --- | --- |
| **TC-FUNV-01** | Validate redirecting to order information page | High | User checked out successfully, user is on the thank-you page | 1. Click on the order details link | User is redirected to the order information page |
| **TC-FUNV-02** | Validate Printing order informations | low | Order details page loaded | 1. Click on the print button | user is redirected to print settings tab |
| **TC-FUNV-03** | Validate Downloading order informations as PDF | low | Order details page loaded | 1. Click on the PDF Invoice button | A download will start |
| **TC-FUNV-04** | Validate Cancelling the order | High | Order details page loaded | 1. Click on the Cancel order button | 1. A confirmation message will appear confirming the deletion <br> 2. The cancel order button will disappear <br> 3. The order status will change to cancelled|
| **TC-FUNV-05** | Validate Reorder the same order | High | Order details page loaded | 1. Click on the Reorder button | 1. The user will be redirected to the checkout page <br> 2. The user is allowed to change the quantity |
