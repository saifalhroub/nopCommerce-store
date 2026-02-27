# Order Information page

> As a user,
> I want an order information page
> So I can check and manage my order 

---

## AC - Order information preview

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
When the user is on the order information page
Then the system will allow the user to cancel his order

---

## AC - Print informatiom

Given the user wants to have a hard copy of the order informations 
When the user is on the order information page
Then the store allow user to print the order informations

## AC - Print information flow

Given that the user is on the order information page
When the user clicks on the print button
Then the user will be redirected to a new tab
And the tab contains print settings

---

## AC - PDF Invoice
Given the user is on the order information page
When the user clicks on the PDF Invoice button
Then the order information will be downloaded as PDF

---

## AC - Reorder 
Given that the user is on the order information page
When the user clicks on the reorder button
Then the user will be redirected to the cart page
And the same products that have been in the order will appear

---

# Core functionalities

| TC ID | Title | Priority | Preconditions | Steps | Expected Results |
| --- | --- | --- | --- | --- | --- |
| **FUNC-Canncel-01** | Validate cancelling the order | High | Order Accepted, and the user is on the order information page | 1. Click on the cancel button <br> 2. Confirm the deletion process | 1. Order is cancelled <br> 2. System will send a message confirming the order cancellation <br> 3. The cancel button disappears <br> |
| **FUNC-Print-02** | Verify user can print the order information | Low | Order information page loaded | 1. Click on the print button <br> 2. Determine the print settings <br> 3. Confirm the print | 1. User is redirected to a print setting page <br> 2. The order information is printed |
| **FUNC-PDF-03** | Low | Verify user can have a soft copy of the order information | Order information page loaded | 1. Click on the PDF Invoice | 1. A download will start <br> 2. The pdf will be stored in the user's device |
| **Func-Reorder-04** | High | Validate reordering the same order | Order information page loaded | 1. Click on the reorder button | 1. The system redirects the user to the cart page <br> 2. The same products in the placed order appear with the right quantity <br> 3. The user is allowed to change the quantity of the product

---

# Edge & Robutness
| TC ID | Title | Priority | Preconditions | Steps | Expected Results |
| --- | --- | --- | --- | --- | --- |
| **EDGE-internet-01** | Validate the page response to no internet connection | Medium | Order information page loaded | 1. Turn off th wifi <br> 2. Send request a request for any functionality | 1. The system will redirect the user to no internet connection page <br> 2. The request will be processed after user connects the device to the internet |
| **ROBU-cancel-02** | Validate spame clicking on the cancel button | Medium | Order information page loaded | 1. Click for a consecutive times on the cancel button | 1. The page is disabled <br> 2. A confirm canceling message appears <br> 3. The system prevent the user from interacting with the page | 
| **ROBU-Print&PDF-03** | Validate spame clicking on the print button | Medium | Order information page loaded | 1. Click for a consecutive times on the print button | 1. The system responds to the first click only <br> 2. The user is redirected to only one new tab for print request <br> 3. Only one download will start for PDF Invoice  | 
