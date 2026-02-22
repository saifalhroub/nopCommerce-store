# Checkout

## 1-
> As a user, 
> I want a checkout page,
> So I can use my personal information to confirm my purchase

---

### AC (Billing Address)

 Given that the user wants to confirm identity
 When the user is on the checkout page
 Then he has to provide his billing address informationsto confirm identity

---

### AC - (Shipping Address)

Given the user is on the checkout page
When the user completed the billing address step
Then he will be asked to provide a shipping destination

---

### AC (Shipping Method)

Given the user is on the checkout page
When the user completed the shipping address step
Then he will be asked to select a shipping method

---

### AC - (Payment Method)

Given the user is on the checkout page
When the user completed the shipping method step
Then two payment methods will appear:
 - Check / Money Order
 - Credit Card
And the user has to select a method

---

### AC - (Payment information)

 - **Check / Money Order**
   
Given the user selects "Check / Money Order" as a payment method  
When the user proceeds to the Payment Information step  
Then the system should display:
  - Company name
  - Full mailing address
  - Payment instructions text
  - Notice about check clearance delay
  - No Input Required

- Given the user selects Check / Money Order  
Then the system should not require additional payment input fields  
And the user can proceed directly by clicking Continue

- **Credit Card**

  Given the user selects Credit Card
  When the user proceeds to the payment information step
  Then the user will be asked to provide this
    - Select credit card
    - Cardholder name
    - Card number
    - Expiration date
    - Card code
 


---
### AC (Confirm order)

Given the user completed the payment information step
When the user is on the confirm order step
Then the system should display:
  - Billing Address
  - Shipping Address
  - Shipping Method
  - Payment Method
  - Payment Information
  - The subtotal, shipping, tax & total prices
  - The items added to the cart
  - Back button
  - Confirm button

---

### AC - Confirm button
Given that the user is on the confirm order step
When the user clicks on confirm button
Then the order will be placed
And the user will be redirected to the Thanking page

---

### AC – Navigation – (Back Button)

Given the user is on any of the checkout page steps  
When the user clicks on the Back button  
Then the user should be redirected to the previous checkout step

---

### AC – (Continue Button)

Given the user is on any of these checkout page steps
  - Billing Address
  - Shipping Address
  - Shipping Method
  - Payment Method
  - Payment Information
When the user clicks on the Continue button  
Then the system should proceed to the next checkout step


> As a user,
> I want an order confirmation screen
> So I know the order has been accepted

### AC - Confirmation message
Given the user finished the checkout process
Then the user will be redirected to thank-you page
And the user will see:
  - Thank you 
  - Your order has been successfully processed!
  - Order number

---

### AC - Order details
Given the user is on the thank-you page
When the user clicks on order details
Then the user will be redirected to the order information page

---

### AC - Continue button
Given the user is on the thank-you page
When the user clicks on the continue button
Then the user will be redirected to the landing page

---




