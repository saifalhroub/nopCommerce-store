# Feature: <shopping Cart Page>

---

# 1️⃣ User Story
As a user,  
I want to have a cart page,  
So that I can check/finalize/edit the cart

## AC (Navigation):
 Given the user is using the store
 When the user clicks on the add to cart link
 Then the user will be redirected tothe shopping cart 

## AC (Products selected)
 Given the user is on the shopping cart page
 Then all the products added should appear

## AC (Quantity)
 Given that the user changed the quantity
 Then the total price changes accordingly

## AC (Remove)
 Given that the user is on the shopping cart page
 When the user clicks on the X icon under the name of the removed
 Then all of the product copies will be removed

## AC (Continue Shopping)
Given that the user clicked on the continue shopping button
Then the user will be redirected to the products page

## AC (Estimate shipping)
Given the user is on the shipping cart page
When the user clicks on the Estimate Shipping button
Then the user will be asked to provide:
 - Region (Country)
 - Zip/Postal code
And the estimated shipping price will show up

## AC (Gift Rapping)
Given the useris on the shopping cart
When the user decides to gift the products
Then the user can order the product to be gift-wrapped
And +10$ will be added to the total price

As a user,
I want a bill to see the total price and apply promo codes,
so I can have a discount and see the total price

## AC (price details)
Given the user is using the store
When the user is on the shopping cart page
Then he will see the total price that includes:
 - Sub-Total
 - Shipping price
 - Tax price
 - Total price

## AC (Discount Code)
Given the user is using the store 
When the user fills in the discount code field with a valid code
Then the discount will be applied to the bill
And the total price will change accordingly

## AC (Checkout)
Given the user is on the shopping cart
When the user is finished finalizing his order 
Then the user has to accept the terms of services
And then the user can use the checkout to proceed


---


#  Test Cases

---

## Functional – Valid Scenarios

| TC ID | Title | Priority | Preconditions |
|-------|-------|----------|---------------|
| TC-FUNCV-01 | | | |

**Steps:**
1.  
2.  

**Expected Result:**
-  
-  

---

## Functional – Invalid Scenarios

| TC ID | Title | Priority | Preconditions |
|-------|-------|----------|---------------|
| TC-FUNCINV-01 | | | |

**Steps:**
1.  
2.  

**Expected Result:**
-  
-  

---

## Boundary Value Testing

| Field | Min | Max | Tested Value | Expected |
|-------|-----|-----|-------------|----------|

---

## Edge Cases

| TC ID | Scenario | Expected Result |
|-------|----------|----------------|

---

## Security Testing

| TC ID | Attack Type | Expected Result |
|-------|------------|----------------|

---

## UI Testing

- Layout validation  
- Field alignment  
- Button state  
- Error message placement  

---

## Usability Testing

- Keyboard navigation  
- Field focus behavior  
- Error clarity  
- Mandatory indicators  

---

## Compatibility Testing

- Keyboard navigation  
- Field focus behavior  
- Error clarity  
- Mandatory indicators  

---

## API Testing (If applicable)

### Valid Request
- Status Code:
- Response Body:
- Database Check:

### Invalid Request
- Status Code:
- Error Message:
- Data Integrity:
