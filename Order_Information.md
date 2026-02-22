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
